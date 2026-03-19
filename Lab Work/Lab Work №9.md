
# Лабораторна робота №9
## Тема: Захист системи та користувачів у Linux. Створення користувачів та груп

## **Мета роботи:**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими діями при створенні нових користувачів та нових груп користувачів.

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
| User account | Account that allows a person to log in and use the system. |
| Root user | The administrative user with full access to the system. |
| Privileges | Permissions that determine what actions a user can perform. |
| Group | Collection of users used to manage permissions collectively. |
| UID (User ID) | Unique numerical identifier assigned to each user. |
| GID (Group ID) | Unique numerical identifier assigned to each group. |
| System account | Account used by the system or services, not for human login. |
| Authentication | The process of verifying a user’s identity. |
| Authorization | The process of granting access rights to resources. |
| Primary group | The main group assigned to a user. |
| Secondary group | Additional groups a user belongs to. |

### 1.2 — Відповіді на питання

#### 1.2.1 — UPG (User Private Group)

Це підхід, при якому:
- для кожного нового користувача автоматично створюється окрема група
- назва групи збігається з ім’ям користувача
- тільки цей користувач є членом цієї групи

Приклад:

| Користувач | Група |
| :--- | :--- |
| petryshaka | petryshaka |

Доцільність використання UPG:

| Користь | Переваги |
| :--- | :--- |
| Ізоляція користувачів | Простіше керувати правами |
| Кожен користувач має власні файли | Безпечніше (менше ризику доступу до чужих файлів) |
| Важливо уникнути випадкового доступу інших користувачів | Добре працює з правами типу `rw-r-----` |

#### 1.2.2 — Команди для створення груп користувачів

Основна команда:

```Bash
groupadd groupname
```

#### Приклади:

Створити групу:

```Bash
sudo groupadd sics33
```

Створити групу з конкретним GID:

```Bash
sudo groupadd -g 2007 sics33
```

#### 1.2.3 — Команди для зміни груп користувачів

Основна команда:

```Bash
groupmod -argument groupname
```

#### Приклади:

Створити групу:

```Bash
sudo groupmod -n sics33 sics34
```

Змінити GID групи:

```Bash
sudo groupmod -g 2008 sics34
```

Додати користувача до групи:

```Bash
sudo usermod -aG sics34 pavlo
```

---

## 2. Хід роботи

### 2.1 — Приклади команд з NDG Lab 15 & 16

| Назва команди | Її призначення та функціональність |
| :--- | :--- |
| `su` | Перемикання на іншого користувача root. |
| `sudo` | Dиконання команди з правами адміністратора. |
| `id` | Показує інформацію про користувача. |
| `exit` | Вихід із поточної сесії або оболонки. |
| `head` | Виводить перші рядки файлу. |
| `grep` | Пошук тексту у файлах. |
| `getent` | Отримання даних із системних баз (користувачі, групи). |
| `who` | Показує користувачів, які зараз увійшли в систему. |
| `w` | Показує активних користувачів і їх дії в системі. |
| `last` | Показує історію входів у систему. |
| `groupadd` | Створення нової групи. Аргументи: `-r` — створити системну групу. `-n` — використовується для задання імені. `-g` — задати ідентифікатор групи. |
| `groupmod` | Зміна параметрів групи. Аргументи: `-n` — змінити назву групи. `-g` — змінити ідентифікатор групи. |
| `useradd` | Створення нового користувача. Аргументи: `-D` — показ/зміна стандартних налаштувань. `-k` — каталог шаблонів для home-директорії. `-f` — час блокування після неактивності. `-G` — додаткові групи. `-c` — опис користувача. `-m` — створити домашній каталог. |
| `passwd` | Зміна пароля користувача. |
| `usermod` | Зміна параметрів користувача. Аргументи: `-a` — додати до групи без видалення з інших. `-G` — список додаткових груп. `-L` — заблокувати обліковий запис. `-U` — розблокувати обліковий запис. |
| `groupdel` | Видалення групи. |
| `userdel` | Видалення користувача. Аргумент: `-r` — видалити користувача разом із домашнім каталогом. |
| `lastb` | Показує невдалі спроби входу в систему. |

### 2.2 — Робота в терміналі

#### 1. Інформація про поточного користувача

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1295" height="233" src="https://github.com/user-attachments/assets/0f9d550e-0500-4be5-ba21-6d8102622bce"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 2. Практика з командами `last`, `w`, `who`

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="614" height="222" src="https://github.com/user-attachments/assets/ab37b6e4-bc30-4cce-a664-3293d4644c99"/></td>
        <td><img width="605" height="110" src="https://github.com/user-attachments/assets/d274e16f-5f94-4025-b578-f7cc65f6def7"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 3. Створення груп з перевіркою

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="482" height="281" src="https://github.com/user-attachments/assets/589d4bfa-6d63-479b-b01f-29e09a060169"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 4. Створення користувачів

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="319" height="451" src="https://github.com/user-attachments/assets/ee36d603-8365-4317-9c00-537b0eb3f82e"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 5. Додавання користувачів у групи

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="528" height="447" src="https://github.com/user-attachments/assets/7fe2c7b4-afd6-44e6-a3b4-b03e32953c1d"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 6. Видалення користувачів та перевірка

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="528" height="332" src="https://github.com/user-attachments/assets/b7e2a74d-b9ad-4810-bcd9-f0bf5e3f136d"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 7. Перегляд усіх груп `getent group`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="238" height="874" src="https://github.com/user-attachments/assets/ee99cc0f-4aec-410b-b188-b1cf88237ad5"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 8. Видалення груп та перевірка

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="526" height="234" src="https://github.com/user-attachments/assets/d69e37b3-7288-4b3c-b48f-50ab978f2531"/></td>
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



---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**: Completed tasks of preliminary preparation and answered the questions.
- **Member 3 — [Tingem](https://github.com/Tingem)**: Answered the control questions and did conclusion.
