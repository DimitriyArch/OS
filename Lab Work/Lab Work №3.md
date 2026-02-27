
# Лабораторна робота №3
## Тема: Знайомство з базовими командами CLI-режиму в Linux

## **Мета роботи:**
1. Знайомство з базовими командами CLI-режиму в Linux.
2. Знайомство з базовими текстовими командами в термінальному режимі роботи в різних ОС.

---

## Матеріальне забезпечення
* ЕОМ типу IBM PC.
* ОС сімейства Windows та віртуальна машина Virtual Box (Oracle).
* ОС GNU/Linux (Arch).
* Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux

---

## 1. Таблиця команд (Command table)

| Command name | Purpose and functionality |
| :--- | :--- |
| `ls` | Displays information about directories and files. By default, without arguments, it shows information for the current directory. |
| `ls -l` | Using the `-l` option with the `ls` command displays information about files in the current working directory in long format, which provides more detailed additional information. |
| `ls -l /tmp` | Using the `/tmp` argument together with the `-l` option in the `ls` command displays detailed information about the files in the `/tmp` directory. |
 | `whoami` | Displays the username of the currently logged-in user. |
| `pwd` | Prints the current working directory (the full path to the directory you are in). |
| `history` | Shows a list of previously executed commands in the current shell session. |
| `echo Text` | Prints the specified text (in this case, “Text”) to the terminal. |
| `date` | Displays the current system date and time. |
| `man date` | Opens the manual (help documentation) page for the `date` command. |
| `man -k password` | Searches the manual page descriptions for the keyword “password”. |
| `sudo --help` | Displays help information and usage instructions for the `sudo` command. |
| `ls -al` | Lists all files and directories (including hidden ones) in long format, showing detailed information such as permissions, owner, size, and modification date. |
| `locate spotify` | Searches for files and directories on the system whose names contain the word “spotify” (using a prebuilt file index database). |

---

## 2. Робота в в терміналі

### 2.1 Робота зі змінними (Variables) та псевдонімами (Aliases) в терміналі:

<p align="center">
  <img src="https://github.com/user-attachments/assets/389ebeaa-1d82-4287-9e4b-e12cc5967314" width="775"/>
  <br>
  <b>Скріншот 1</b> — Створення змінних з ІП та їх виведення
  <br><br>
  <img src="https://github.com/user-attachments/assets/4d798419-a642-4e25-acb7-5cb55eac7a5b" width="832"/>
  <br>
  <b>Скріншот 2</b> — Створення псевдонів mycal та їх виведення
</p>

### 2.2. Робота з функціями (Functions) в терміналі

<p align="center">
  <img src="https://github.com/user-attachments/assets/debc535f-ef3b-4a8b-9bd8-ee59f72eedab" width="1290"/>
  <br>
  <b>Скріншот 3</b> — Створення функції students_report та її виведення
</p>

### 2.3. Робота з лапками (Quoting) в терміналі

<p align="center">
  <img src="https://github.com/user-attachments/assets/de495ffc-0d37-487f-9f65-74382c9d6431" width="2480"/>
  <br>
  <b>Скріншот 4</b> — Виведення тексту разом з застосуванням змінних
</p>

### 2.4. Робота з інструкціями керування (Control Statements) в терміналі

<p align="center">
  <img src="https://github.com/user-attachments/assets/4bf36e6a-5d11-4460-aaeb-59d6af334684" width="1309"/>
  <br>
  <b>Скріншот 5</b> — Використання циклу for для виконання 2.1 та 2.2
</p>

### 2.5. Робота з командами довідки (Man Pages) в терміналі

<p align="center">
  <img src="https://github.com/user-attachments/assets/7b31c043-db30-43f7-a2cf-cd5f350aa2b2" width="1171"/>
  <br>
  <b>Скріншот 6</b> — Отримання довідки та використання 5 різних параметрів
</p>

---

## Відповіді на контрольні запитання

### 1. Які типи команд існують в оболонці Bash?

В оболонці Bash існують вбудовані команди, зовнішні команди, функції оболонки, аліаси та скрипти, які виконуються в середовищі командного рядка.

### 2. Що таке змінні оточення? Які вони бувають. Як їх можна переглянути в терміналі?

Змінні оточення - це змінні, які зберігають інформацію про середовище роботи користувача та передаються дочірнім процесам; вони бувають локальні та глобальні (експортовані), а переглянути їх можна за допомогою команд env, printenv або echo $ІМʼЯ_ЗМІННОЇ.

### 3. Опишіть змінну $PS1. Як в терміналі переглянути її вміст?

Змінна $PS1 визначає вигляд рядка запрошення в Bash, тобто текст, який відображається перед введенням кожної команди, а переглянути її значення можна командою echo $PS1.

### 4. Як можна змінити значення змінної $PS1? Що при цьому відбудеться в рядку запрошенні в bash (рядок запрошення перед початком кожної команди). Як змінити значення цієї змінної не на поточний сеанс, а за замовчуванням?

мінити значення змінної $PS1 можна присвоївши їй нове значення командою PS1="текст", після чого зміниться вигляд рядка запрошення; щоб зміна діяла постійно, потрібно додати нове значення в файл ~/.bashrc.

### 5. Для чого використовують лапки в оболонці Bash?

Лапки в оболонці Bash використовують для керування обробкою тексту та змінних, де одинарні лапки повністю вимикають підстановку змінних, а подвійні дозволяють їх розгортання.

### 6. Для чого використовують інструкції керування, які їх види Ви знаєте?

Інструкції керування використовують для організації логіки виконання команд у скриптах, до них належать умовні оператори (if), оператор вибору (case), цикли (for, while, until) та логічні оператори (&&, ||).

### 7. В чому різниця якщо в кінці рядку запрошення bash стоїть символ $ чи #? Наприклад на екрані ми бачимо наступні записи
  <p align="center">
    <img src="https://github.com/user-attachments/assets/589ccf99-1de3-497a-9b82-6a62c6f43c10" width="472"/>
    <img src="https://github.com/user-attachments/assets/fe7ee984-15f0-4162-a845-02b105208d05" width="507"/>
  </p>

Різниця полягає в правах доступу користувача: якщо в кінці рядка запрошення Bash стоїть символ "$", як у записі [centos@localhost Desktop]$, це означає, що в системі працює звичайний користувач із обмеженими правами, а якщо в кінці стоїть символ "#", як у записі [root@localhost Desktop]#, це означає, що виконання відбувається від імені суперкористувача root, який має повні адміністративні права та може змінювати системні файли й налаштування.
  
### 8. Яке призначення команд whereis та locate? Яка між ними відмінність?

Команда whereis призначена для пошуку розташування виконуваних файлів, вихідного коду та man-сторінок у стандартних каталогах, тоді як locate здійснює швидкий пошук файлів у всій системі за допомогою попередньо створеної бази даних, тому locate знаходить більше результатів і працює швидше.

---

## Висновок (Conclusion)
During this lab work on the topic “Introduction to Basic CLI Commands in Linux”, the main objectives were successfully achieved.

First, we became familiar with the basic principles of working in the Command Line Interface (CLI) environment of a GNU/Linux operating system. We learned how to navigate the file system, identify the current user and directory, view command history, display system date and time, and search for files.

Second, we practiced using essential text-based commands such as whoami, pwd, history, echo, date, man, sudo, ls, and locate. This helped us understand how Linux commands are structured, how options (flags) modify command behavior, and how to access built-in documentation using manual pages.

Additionally, we gained experience working in a virtualized environment using Oracle VirtualBox and interacting with Linux alongside Windows OS. This improved our practical skills in configuring and using different operating systems within one hardware platform.


---

## Team Contributions
- **Member 1 ([DimitriyArch])**: Completed the work in a terminal and formatted the Markdown file.
- **Member 2 ([PashaGo2007])**: Added English command table and conclusions.
- **Member 3 ([Tingem])**: Answered the control questions.
