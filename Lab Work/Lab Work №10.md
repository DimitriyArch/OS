
# Лабораторна робота №10
## Тема: Зміна власників і прав доступу до файлів в Linux. Спеціальні каталоги та файли в Linux

## **Мета роботи:**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими діями при зміні власників файлів, прав доступу до файлів.
3. Знайомство з спеціальними каталогами та файлами в Linux.

---

## Матеріальне забезпечення
* ЕОМ типу IBM PC.
* ОС сімейства Windows та віртуальна машина Virtual Box (Oracle).
* ОС GNU/Linux (Arch).
* Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux

---

## 1. Завдання для попередньої підготовки

### 1.1 — Словник (Dictionary)

| Term | Explanation |
| :--- | :--- |
| File ownership | The concept that every file has an owner (user) and a group. |
| User owner | The user who owns a file. |
| Group owner | The group associated with a file. |
| Permissions | Rules that define access to files (read, write, execute). |
| Read (r) | Permission to view file contents. |
| Write (w) | Permission to modify a file. |
| Execute (x) | Permission to run a file as a program. |
| Default permissions | Permissions assigned when a file is created. |
| Hidden file | File whose name starts with a dot (`.`). |
| Primary group | The main group assigned to a user. |
| Supplementary groups | Additional groups a user belongs to. |
| Binary file | Executable program file. |
| setuid | Special permission that runs a file as its owner. |
| setgid | Special permission that runs a file with group privileges. |
| Sticky bit | Permission that restricts file deletion in shared directories. |

### 1.2 — Відповіді на питання

#### 1.2.1 — Призначення команди id?

Використовується для відображення інформації про користувача:
- UID (ідентифікатор користувача)
- GID (ідентифікатор основної групи)
- список додаткових груп

#### 1.2.2 — Перегляд прав доступу які має власник файлу

Права доступу переглядаються за допомогою команди:

```Bash
ls -l
```

У виводі:

```Bash
-rwxr-xr--
```

Перші 3 символи (`rwx`) — це права власника файлу.

#### 1.2.3 — Зміна власника групи?

Для зміни групи файлу використовуються команди:

```Bash
chgrp groupname filename
```

Або:

```Bash
chown :groupname filename
```

#### 1.2.4 — Перегляд у терміналі який тип поточного файлу

Використовується команда:

```Bash
ls -l
```

Перший символ показує тип файлу:
- `-` — звичайний файл
- `d` — директорія
- `l` — символічне посилання

Приклад:

```Bash
drwxr-xr-x  -> directory
-rw-r--r--  -> regular file
lrwxrwxrwx  -> symlink
```

Також можна використати:

```Bash
file filename
```

#### 1.2.5 — Setuid та Setgid

- Setuid (Set User ID) — дозволяє запускати програму від імені власника файлу (часто root). Використовується, коли звичайному користувачу потрібен доступ до системних ресурсів.

Приклад: команда `passwd` (змінює пароль користувача).

- Setgid (Set Group ID)

Має 2 варіанти:
- Для файлів: програма виконується з правами групи власника.
- Для директорій: всі нові файли автоматично отримують групу директорії.

Використовується для спільної роботи користувачів.

#### 1.2.6 — Sticky Bit

Sticky Bit — це спеціальний дозвіл, який обмежує видалення файлів у спільних директоріях.

Якщо він встановлений:
* файл може видалити тільки:
  - власник файлу
  - власний директорії
  - root

Приклад:

Каталог: `/tmp` має права `drwxrwxrwt` — `t` означає наявність Sticky Bit, аби користувачі не могли видаляти файли інших.

## 2. Хід роботи 

### 2.1 — Приклади команд з NDG Lab 17 & 18

| Назва команди | Її призначення та функціональність |
| :--- | :--- |
| `chmod` | Зміна прав доступу до файлу. Аргументи: `a+x` — додає право виконання (x) для всіх (user, group, others), `g-w` — забирає право запису (w) у групи, `go+r` — додає право читання (r) для групи та інших, `o=rwx` — встановлює для інших користувачів повні права (rwx) |
| `chown` | Зміна власника та/або групи файлу. |
| `chgrp -R` | Зміна групи файлу або каталогу. Аргумент: `-R` — рекурсивно змінює групу для каталогу і всіх його файлів. |
| `ls -ladi` | Виведення детальної інформації про файли. Аргументи: `-l` — детальний формат (права, власник, розмір, дата), `-a` — показує приховані файли (`.` і `..`), `-d` — показує інформацію про каталог, а не його вміст, `-i` — показує inode (унікальний номер файлу)|
| `stat` | Показує детальну інформацію про файл або каталог. |
| `passwd` | Зміна пароля користувача. |
| `wall` | Надсилання повідомлення всім користувачам у системі. |
| `rm` | Видаляє файли і каталоги. |
| `ln -s` | Створення символічного (soft) посилання. |

### 2.2 — Робота в терміналі

#### 1. Створення 3 користувачів, групи та додавання до неї

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="256" height="309" src="https://github.com/user-attachments/assets/c20ef410-a91e-4fa0-b3c2-7c68ae4d4e35"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 2. Створення Shell-скрипта

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="184" height="137" src="https://github.com/user-attachments/assets/4cbdfd5c-4095-4539-9a47-9ae2697e1ef0"/></td>
        <td><img width="223" height="102" src="https://github.com/user-attachments/assets/475f98ce-4441-44de-9ba3-883e075792cb"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 3. Налаштування прав доступу

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="188" height="55" src="https://github.com/user-attachments/assets/53b5efa8-0006-4b07-b15a-bb14dccfc72d"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 4. Робота з директоріями

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="632" height="400" src="https://github.com/user-attachments/assets/3d6006cc-fc0a-42a5-ac87-ec026076ac88"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 5. Експеримент з chmod

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="179" height="189" src="https://github.com/user-attachments/assets/66c4a54a-a52b-46bb-b876-c2d0cd733ef3"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 6. Каталог з setgid + sticky bit

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="256" height="227" src="https://github.com/user-attachments/assets/1faf31d3-64c5-4059-822a-3a9355152cce"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 7. Файли і посилання (під кожним користувачем)

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="299" height="582" src="https://github.com/user-attachments/assets/d0ee53c9-116e-48c8-b1f0-662a48887e43"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 8. Перевірка доступу іншими користувачами

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="336" height="123" src="https://github.com/user-attachments/assets/b6372776-379d-447f-87fe-f3279861ae00"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 9. Спроба видалення

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="517" height="53" alt="Screenshot_20260319_175740" src="https://github.com/user-attachments/assets/52a71a13-8f1c-45e7-baac-c919532664d9"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Відповіді на контрольні запитання

### 1.



### 2.



### 3.



### 4.



### 5.



### 6.



### 7.



### 8.



### 9.



### 10.



### 11.



---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**: Completed tasks of preliminary preparation and answered the questions.
- **Member 3 — [Tingem](https://github.com/Tingem)**: Answered the control questions and did conclusion.
