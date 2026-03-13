
# Лабораторна робота №5
## Тема: Знайомство з командами навігації по файловій системі та керування файлами та каталогами

## **Мета роботи:**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими командами навігації по файловій системі.
3. Знайомство з базовими командами для керування файлами та каталогами.

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
| Directory | Directory (folder) that contains files or other directories |
| Root directory | The root directory `/`, the top level of the file system |
| Filesystem | File system, the structure used to organize files in an operating system |
| CLI | Command-line interface |
| Path | The path to a file or directory |
| Relative path | Relative path (from the current directory) |
| Absolute path | An absolute path (starts with `/`) |
| Glob | Pattern characters used to search for files |
| Wildcard | Substitution character |
| Recursive | Recursive action (including subdirectories) |
| Hidden files | Hidden files (start with `.`) |

### 1.2 — Відповіді на питання

#### 1.2.1 — Порівняння файлових структур Windows та Linux

Файлова структура Windows і Linux мають різний принцип організації.

У Windows структура починається з "My Computer / This PC", де кожен фізичний диск має власну букву (`C:`, `D:`, `E:`). Файли і каталоги розміщуються окремо на кожному диску.

У Linux використовується єдина ієрархічна файлова система, яка починається з кореневого каталогу `/`. Усі пристрої, диски та файлові системи підключаються до цієї структури як каталоги.

| Windows | Linux |
| :--- | :--- |
| Диски позначаються буквами (`C:`, `D:`) | Використовується єдиний корінь `/` |
| Файлові системи розділені | Єдина структура |
| Основні каталоги створює користувач | Багато системних каталогів стандартні |
| Пристрої відображаються як диски | Пристрої представлені файлами |

#### 1.2.2 — Поняття FHS

FHS (Filesystem Hierarchy Standard) — це стандарт, який визначає структуру каталогів у Linux.

Він описує:
* призначення системних каталогів
* де повинні зберігатися системні файли
* де розташовуються бібліотеки, програми та конфігураційні файли

| Каталог | Призначення |
| :--- | :--- |
| `/bin` | Основні системні програми |
| `/etc` | Конфігураційні файли |
| `/home` | Домашні каталоги користувачів |
| `/usr` | Програми користувача |
| `/var` | Змінні дані (логи, кеш) |
| `/tmp` | Тимчасові файли |

Завдяки стандарту FHS різні дистрибутиви Linux мають схожу структуру файлової системи, що полегшує адміністрування.

#### 1.2.3 — Основні команди для роботи з файлами та каталогами

| Команда | Призначення |
| :--- | :--- |
| `touch` | Створення порожнього файлу |
| `mkdir` | Створення каталогу |
| `mv` | Переміщення або перейменування файлів |
| `cp` | Копіювання файлів |
| `cp -r` | Копіюваггя каталогів |
| `rm` | Видалення файлів |
| `rm -r` | Видалення каталогу разом із вмістом |
| `rmdir` | Видалення порожнього каталогу |

---

## 2. Хід роботи 

### 2.1 — Приклади команд з NDG Lab 7 & 8

| Назва команди | Її призначення та функціональність |
| :--- | :--- |
| `pwd` | Визначає місце знаходження користувача у файловій системі, показує поточну робочу директорію (print working directory) |
| `cd Documents` | Команда `cd` здійснює перехід до каталогу, який у неї вказаний як аргумент. В даному випадку це каталог `Documents`
| `echo` | Виводить текст або значення змінних у термінал. Часто використовується для відображення повідомлень або результатів роботи скриптів |
| `ls` | Показує список файлів і каталогів у поточній директорії |
| `ls -a` | Показує всі файли і каталоги, включаючи приховані (ті, що починаються з крапки `.`) |
| `ls -l` | Виводить список файлів у детальному форматі: права доступу, власник, розмір, дата створення або зміни |
| `ls -R` | Рекурсивно показує вміст усіх підкаталогів поточного каталогу |
| `ls -d` | Показує сам каталог як об'єкт, а не його вміст (корисно при роботі з шаблонами) |
| `cp` | Копіює файл або каталог з одного місця у інше |
| `cp -v` або `--verbose` | Копіює файли та показує детальну інформацію про процес копіювання (які файли копіюються) |
| `rm` | Видаляє файли з файлової системи |
| `cp -p` | Копіює файл, зберігаючи його початкові атрибути (права доступу, час створення, власника) |
| `cp -R` | Копіює каталоги разом з усіма файлами і підкаталогами рекурсивно |
| `mkdir` | Створює новий каталог (директорію) |
| `rm -r` | Видаляє каталог разом з усім його вмістом рекурсивно |
| `rmdir` | Видаляє порожній каталог |
| `touch premove` | Створює новий порожній файл з назвою `premove` або оновлює дату його останньої зміни |
| `mv premove postmove` | Перейменовує файл `premove` у `postmove` або переміщує його в інше місце |
| `rm postmove` | Видаляє файл `postmove` з файлової системи |

### 2.2 — Робота в терміналі

---
<h3>
  <details>
    <summary>Скріншот 1</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/3dc8ceee-b9ed-4ac3-bb91-9e4d79d22fed"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 2</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/44e52e30-df12-4271-bb65-ebf855643958"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 3</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/9e5f5331-f4cb-4652-90c8-ddbb2274a27e"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 4</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/6764ec81-5369-4052-9377-006154405b1a"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 5</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/a0ffa014-d5fa-4c95-84cc-a48b975f7309"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 6</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/839c7088-c1a5-4e58-b7cc-0f4dfcf78257"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 7</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/09b7f72f-4a6f-4eaa-8821-d39ab6a027fa"></td>
      </tr>
    </table>
  </details>
  
  ---
  
  <details>
    <summary>Скріншот 8</summary>
    <table>
      <tr>
        <td><img width="" height="" src="https://github.com/user-attachments/assets/74b11998-09ab-466e-aa0e-9e66a5c7adb5"></td>
      </tr>
    </table>
  </details>
</h3> 

  ---
  
### 2.3 — Опис дій команд `cd`

| Команда | Дія |
| :--- | :--- |
| `cd /` | Перехід до кореневого каталогу |
| `cd /home` | Перехід до каталогу home |
| `cd ~` | Перехід до домашнього каталогу користувача |
| `cd` | Також переходить у домашній каталог |
| `cd ..` | Перехід на один рівень вище |
| `cd ../..` | Перехід на два рівні вище |
| `cd -` | Повернення до попереднього каталогу |

---

## Відповіді на контрольні запитання

### 1. Перегляд шляху до домашньої директорії через `echo`

Використовуючи аргументи `$HOME` та `~`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="166" height="195" src="https://github.com/user-attachments/assets/2a274db9-ac2c-4884-a35e-b325f9d025c9"/></td>
      </tr>
    </table>
  </details>
</h3>

### 2. Перегляд вміст кореневого каталогу, не переходячи до нього через `ls /`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="400" height="386" src="https://github.com/user-attachments/assets/e104cd62-1241-425d-884e-c1a6eb83c523"/></td>
      </tr>
    </table>
  </details>
</h3>

### 3. Створення і додавання інформації у порожній файл через `echo`

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="259" height="146" src="https://github.com/user-attachments/assets/1d702fba-c951-46fa-b236-fc31dac5a8c0"/></td>
        <td><img width="163" height="140" src="https://github.com/user-attachments/assets/3a481dd9-e53d-4aca-aba5-2173be2c1af5"/></td>
      </tr>
    </table>
  </details>
</h3>

### 4. Cтворення, копіювання та видалення каталогу командами `mkdir`, `cp -r`, `rmdir`, `rm -r`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="177" height="232" src="https://github.com/user-attachments/assets/6488a6cb-6294-4d83-aaa2-e9c201adc926"/></td>
      </tr>
    </table>
  </details>
</h3>

### 5. Аналіз команди `mv`

1. Переміщення файлу
2. Перейменування файлу
3. Переміщення та перейменування

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="591" height="188" src="https://github.com/user-attachments/assets/609e93c8-b715-46ab-9e10-03898c885add"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Висновок (Conclusion)

During the laboratory work, practical skills of working with the Bash command shell in the Linux operating system were obtained. The structure of the Linux file system and its differences from the Windows file system were examined. The FHS (Filesystem Hierarchy Standard) was also studied, which defines the structure and purpose of the main system directories.

During the work, the basic commands for navigating the file system (`pwd`, `cd`, `ls`) and commands for managing files and directories (`touch`, `mkdir`, `cp`, `mv`, `rm`, `rmdir`) were studied. Practical skills in creating, copying, moving, renaming, and deleting files and directories in the terminal were developed.

The acquired knowledge makes it possible to work effectively with the Linux file system through the command line and serves as a basis for further study of administration and the use of Linux-based operating systems.

---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**: Completed tasks of preliminary preparation and answered the questions.
