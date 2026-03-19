
# Лабораторна робота №7
## Тема: Створення скриптових сценаріїв та визначення апаратної конфігурації системи

## **Мета роботи:**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство знайомство з базовими діями при роботі зі скриптовими сценаріями.

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
| Shell | Command-line interface that allows the user to interact with the operating system by entering commands. |
| Shell Script | Text file containing a sequence of commands that are executed automatically by the shell. |
| Script | File that contains a series of commands executed automatically. |
| Bash | Bourne Again Shell, one of the most popular command-line shells used in Linux systems. |
| Parameter | Additional information passed to a command to modify its behavior. |
| Option | Special type of parameter, usually beginning with `-` or `--`, that changes how a command works. |
| Argument | Value provided to a command, such as a file name or directory name. |
| Shebang | The first line in a script (for example `#!/bin/bash`) that specifies which interpreter should execute the script. |
| Interpreter | Program that reads and executes commands written in a script or programming language. |
| chmod | Linux command used to change file permissions. |

### 1.2 — Відповіді на питання

#### 1.2.1 — Поняття скриптового сценарію у командній оболонці

Скриптовий сценарій (shell script) — це текстовий файл, який містить послідовність команд оболонки (Shell), що виконуються автоматично одна за одною.

Скрипти використовуються для:
- автоматизації повторюваних завдань
- виконання декількох команд одним запуском
- адміністрування системи
- обробки файлів і даних

Скрипти можуть містити:
- змінні (variables)
- умовні оператори (conditionals)
- цикли (loops)
- виклики інших програм

Найчастіше в Linux використовується оболонка `Bash`, тому багато скриптів називають `Bash scripts`.

#### 1.2.2 — Як створюються, редагуються та запускаються скрипти

#### Створення скрипта

```Bash
nano script.sh
```

Перший рядок зазвичай містить shebang, який вказує інтерпретатор:

```Bash
#!/bin/bash
```

Приклад простого скрипта:

```Bash
#!/bin/bash
echo "Hello, World!"
```

#### Редагування скрипта

Для редагування використовуються текстові редактори, такі як:
- nano
- vi / vim

Приклад:

```Bash
vi script.sh
```

#### Надання прав на виконання:

```Bash
chmod +x script.sh
```

#### Запуск скрипта двома способами:

```Bash
bash script.sh
```

```Bash
./script.sh
```

#### 1.2.3 — Основні компоненти материнської плати

Материнська плата — це основна плата комп'ютера, яка з'єднує всі апаратні компоненти.

Основні компоненти:
- Процесорний сокет
- Чіпсет
- Слоти оперативної пам'яті
- Слоти розширення
- Порти для накопичувачів
- BIOS / UEFI
- Роз'єми живлення

#### 1.2.4 — Для яких пристроїв використовуються MBR та GPT

MBR (Master Boot Record) і GPT (GUID Partition Table) — це типи таблиць розділів диска.

Вони використовуються для:
- жорстких дисків (HDD)
- твердотільних накопичувачів (SSD)
- USB-накопичувачів
- інших пристроїв зберігання даних

| MBR | GPT |
| :--- | :--- |
| Старіший | Новіший |
| Підтримує диски до 2 TB | Підтримує диски більше 2 TB |
| Максимум 4 первинні розділи | Може створювати до 128 розділів |
| Сумісний з Legacy і UEFI | Працює лише з UEFI |

#### 1.2.5 — Суть операції монтування

Монтування (mounting) — це процес підключення файлової системи пристрою до структури каталогів Linux.

У Linux всі файли знаходяться в єдиному дереві каталогів, тому новий пристрій потрібно прикріпити до певної папки.

Приклад:

```Bash
mount /dev/sdb1 /mnt/usb
```
- `/dev/sdb1` — пристрій
- `/mnt/usb` — точка монтування

#### Для чого потрібне монтування:

- отримати доступ до файлів на накопичувачі
- використовувати флешки, SSD, HDD водночас
- підключати мережеві файлові системи

Без монтування операційна система не може працювати з файловою системою пристрою.

## 2. Хід роботи

### 2.1 — Приклади команд з NDG Lab 11 & 12

| Назва команди | Її призначення та функціональність |
| :--- | :--- |
| `vi` | Потужний текстовий редактор для створення та редагування файлів у терміналі. |
| `nano` | Простий і зручний текстовий редактор для роботи у терміналі. |
| `gedit` | Графічний текстовий редактор для середовища робочого столу Linux. |
| `vi myfile.sh` | Відкриває файл `myfile.sh` у редакторі vi (або створює його, якщо він не існує). |
| `bash` | Командна оболонка, яка використовується для виконання команд і запуску скриптів. |
| `chmod a+x myfile.sh` | Надає всім користувачам право виконання файлу `myfile.sh`. |
| `./myfie.sh` | Запускає скрипт `myfie.sh` з поточного каталогу. |
| `cat myfile.sh` | Виводить вміст файлу `myfile.sh` у термінал. |
| `mkdir bin` | Створює новий каталог з назвою `bin`. |
| `mv myfie.sh bin` | Переміщує файл `myfie.sh` до каталогу `bin`. |
| `man test` | Відкриває довідкову сторінку (manual) для команди `test`. |
| `seq` | Генерує послідовність чисел. |
| `lscpu` | Виводить детальну інформацію про процесор (CPU). |
| `head -n 20 /proc/cpuinfo` | Виводить перші 20 рядків інформації про процесор із системного файлу. |
| `free` | Показує використання оперативної пам’яті, аргумент `-m` в мегабайтах або `-g` в гігабайтах.|
| `lspci -k` | Відображає всі PCI-пристрої, з аргументом `-k` драйвери, які вони використовують. |
| `lsusb` | Виводить список підключених USB-пристроїв. |
| `lsmod` | Показує список завантажених модулів ядра. |
| `fdisk -l` | Виводить інформацію про всі диски та їх розділи. |

### 2.2 — Робота в терміналі

#### 1. Shell-скрипт з виводом привітання, дати та системи

Для створення скриптів був використаний редактор nano.

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="251" height="165" src="https://github.com/user-attachments/assets/a285ad8b-26da-47a8-bbe6-cf47c3103ceb"/></td>
        <td><img width="311" height="298" src="https://github.com/user-attachments/assets/4324719a-6a04-4f32-88aa-81d5a3c72155"/></td>
        <td><img width="415" height="339" src="https://github.com/user-attachments/assets/219f8b0b-590a-4c88-9ba8-9eca03df2e18"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 2. Shell-скрипт для показу апаратної конфігурації

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="235" height="490" src="https://github.com/user-attachments/assets/eeface73-9ceb-4b78-b65b-01fe681843bf"/></td>
        <td><img width="854" height="984" src="https://github.com/user-attachments/assets/35c03a15-5a37-4a5f-bcfc-f52e2a302007"/></td>
      </tr>
    </table>
  </details>
</h3>

#### 3. Власний Shell-скрипт

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="286" height="393" src="https://github.com/user-attachments/assets/a16b0095-3bf5-4617-95e7-56e0a6a4c771"/></td>
        <td><<img width="645" height="634" src="https://github.com/user-attachments/assets/89fb8628-9949-4911-84c8-bfb9ba180887"/>/td>
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

---

## Висновок (Conclusion)

Practical application of scripting tools demonstrated the ability to create, modify, and execute scripts for performing routine operations and retrieving system information. Additionally, methods for determining hardware configuration were explored using standard system utilities, allowing for analysis of CPU, memory, storage devices, and connected hardware components.

Key concepts related to system architecture, including disk partitioning schemes (MBR and GPT) and the mounting process, were also considered as essential elements of system operation.

The results confirm that Bash scripting and built-in Linux utilities provide an effective approach to task automation and system analysis, forming a fundamental part of system administration practices.

---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**: Completed tasks of preliminary preparation and answered the questions.
- **Member 3 — [Tingem](https://github.com/Tingem)**: Answered the control questions and did conclusion.
