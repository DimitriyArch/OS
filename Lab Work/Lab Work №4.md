
# Лабораторна робота №4
## Тема: Команди Linux для управління процесами

## **Мета роботи:**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими командами для управління процесами.

---

## Матеріальне забезпечення
* ЕОМ типу IBM PC.
* ОС сімейства Windows та віртуальна машина Virtual Box (Oracle).
* ОС GNU/Linux (Arch).
* Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux

---

## 1. Відповіді на питання попередньої підготовки

### 1.1 — Команди моніторингу процесів
Найпоширенішою є команда `ps`, яка відображає список активних процесів, наприклад у форматі `ps aux` або `ps -ef`. Для перегляду процесів у режимі реального часу застосовується команда `top`, яка динамічно оновлює інформацію про використання процесора та пам’яті. Також існує більш зручна інтерактивна версія — `htop`, якщо вона встановлена в системі.
Для відображення ієрархії процесів у вигляді дерева використовується `pstree`, для пошуку процесу за ім’ям — `pgrep`, а для надсилання сигналів процесам (наприклад, завершення) — команда `kill`.

### 1.2 — Команда `ps` не відстежує стан процесів у реальному часі
Вона відображає знімок (snapshot) стану процесів на момент виконання команди. Для моніторингу процесів у реальному часі в використовують команди `top` або `htop`, які постійно оновлюють дані на екрані через певні інтервали часу.

### 1.3 — Сортування процесів в команді `top`
За замовчуванням `top` сортує процеси за відсотком використання CPU.

Переключення між параметрами сортування виконується безпосередньо під час роботи програми шляхом натискання відповідних клавіш:

* `P` — сортування за використанням CPU;

* `M` — за використанням пам’яті;

* `N` — за PID;

* `T` — за часом виконання процесу.

Також можна натиснути `f`, щоб зайти в меню керування полями, де можна вибрати інший стовпець для сортування, а клавіша `R` дозволяє змінити порядок сортування (за зростанням або спаданням).

### 1.4 — Команди завершення процесів

* `kill` — надсилання сигналу процесу за його PID (наприклад, kill 1234, за замовчуванням надсилається SIGTERM).

* `kill -9` — примусове завершення процесу сигналом SIGKILL (наприклад, kill -9 1234).

* `killall` — завершення всіх процесів із вказаним ім’ям (наприклад, killall firefox).

* `pkill` — завершення процесів за ім’ям або шаблоном (наприклад, pkill chrome).

---

## 2. Відповіді на питання

### 2.1 — Виведення вмісту директорії `/proc` командою `ls`.
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="400" height="661,157024792" src="https://github.com/user-attachments/assets/79503a97-e8af-40a6-9d8c-24d6a00288d1"</td>
      </tr>
    </table>
  </details>
</h3>

Директорія `/proc` знаходиться в кореневому каталозі файлової системи. 
Це віртуальна файловa система, яка створюється ядром Linux під час роботи системи. Її не існує фізично на диску.

#### Призначення:
* Отримання інформації про процеси.
* Отримання системної інформації.
* Перегляду параметрів ядра.

#### Характеристика вмісту:
* Каталоги з номерами (наприклад `/proc/1234`) — це процеси (PID).
* /proc/version — версія ядра
* /proc/uptime — час роботи системи

Переглядати текстові файли командою `cat`
```Bash
cat /proc/version
```

### 2.2 — Виведення інформації поточних сеансів користувачів командами `who` та `w`.
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="968" height="209" src="https://github.com/user-attachments/assets/f56f5fbc-a823-42f7-ad59-2ba73cb78119"</td>
      </tr>
    </table>
  </details>
</h3>

`who` — показує, хто увійшов у систему.

`w` — показує активних користувачів та що вони роблять.

### 2.3 — Комбінації клавіш у терміналі

| Комбінація | Дія |
| :--- | :--- |
| `Ctrl + C` | Завершити поточний процес |
| `Ctrl + D` | Вийти з оболонки / передати EOF |
| `Ctrl + Z` | Призупинити процес (перевести в background suspended) |

### 2.4 — Різниця фонового процесу від звичайного

| Звичайний (foreground) | Фоновий (background) | Використання |
| :--- | :--- | :--- |
| Виконується в поточному терміналі | Працює без блокування терміналу | Запуск довготривалих задач |
| Блокує введення команд | Дозволяє вводити інші команди | Сервери |

### 2.5 — Команди `jobs`, `bg`, `fg`

| `jobs` | `bg` | `fg` |
| :--- | :--- | :--- |
| Показує список фонових або призупинених задач поточної оболонки | Відновлює призупинений процес у фоновому режимі | Переводить процес на передній план |

### 2.6 — Перегляд всіх фонових процесів командою `top`
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="400" height="476,176470588" src="https://github.com/user-attachments/assets/55fb5647-a97f-49c2-9b93-8205c65b3435"</td>
      </tr>
    </table>
  </details>

### 2.7 — Призупинка, відновлення та перезапуск фонового процесу

#### Призупинити:
Якщо в foreground -> `Ctrl + Z`

#### Відновити:
У foreground -> `fg`
У background -> `bg`

#### Перезапустити:
Якщо завершений — запустити знову командою.

---

## 3. Виконані команди в терміналі

### 3.1 — Запуск `top`
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="400" height="476,176470588" src="https://github.com/user-attachments/assets/55fb5647-a97f-49c2-9b93-8205c65b3435"</td>
      </tr>
    </table>
  </details>
</h3>

#### Показує:
* PID
* USER
* %CPU
* %MEM
* TIME
* COMMAND

Найбільш активні процеси — ті, що мають найбільше значення %CPU.

### 3.2 — Призупинити `top`
Використовується комбінація `Ctrl + Z`.

### 3.3 — Виведення `ps`
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="376" height="184" src="https://github.com/user-attachments/assets/ec78ec72-d031-4f28-8752-0085598716ed"</td>
      </tr>
    </table>
  </details>
</h3>

### 3.4 — 5 прикладів використання `ps`:
* `ps aux` — всі процеси.
* `ps -ejH || axjf` — дерево процесів.
* `ps -U root -u root` — системні процеси.
* `ps -u username` — процеси користувача.
* `ps aux --sort=-%cpu` — сортування по використанню CPU.
<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="268" height="149,6228482" src="https://github.com/user-attachments/assets/0c4f4303-514d-4774-9346-273f0beb5740"/></td>
        <td><img width="268" height="535,330836455" src="https://github.com/user-attachments/assets/938af0ba-5c89-4b69-8561-7395ec4bccaa"/></td>
        <td><img width="268" height="428,8" src="https://github.com/user-attachments/assets/2b58528c-93dc-4bc3-93c8-6b641acd2ea2"/></td>
      </tr>
      <tr>
        <td><img width="268" height="597,21448468" src="https://github.com/user-attachments/assets/5ee00869-e9c0-495e-877d-95d8bda7880d"/></td>
        <td><img width="268" height="837,5" src="https://github.com/user-attachments/assets/fc087f3a-b55d-4897-aafb-7ae63f5e0143"/></td>
        <td><img width="268" height="428,8" src="https://github.com/user-attachments/assets/2865f635-e262-48b6-bbfd-2b3d8cf8fa6c"/></td>
      </tr>
    </table>
  </details>
</h3>

### 3.5 — Перевірка фонових процесів `jobs`
<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="376" height="184" src="https://github.com/user-attachments/assets/ec78ec72-d031-4f28-8752-0085598716ed"</td>
      </tr>
    </table>
  </details>
</h3>

### 3.6 — Відновити `top` у foreground, призупинка та відновлення у background
Використовується команда `fg %1`

Потім комбінація `Ctrl + Z`

Та команда `bg %1`

### 3.7 — Завершити фоновий процес
Використовується команда `kill %1` або `kill PID`

---

## Відповіді на контрольні запитання

1. The `/proc` directory in Linux is a virtual file system created and maintained by the kernel. It does not contain real files stored on disk. Instead, it provides a dynamic interface to kernel data structures and system information.
It stores information about running processes (each process has a directory named by its PID), system memory usage, CPU details, kernel version, uptime, mounted devices, and other runtime system parameters. It is mainly used for system monitoring, diagnostics, and kernel configuration.

2. To dynamically monitor memory usage, you can use the top command. It provides real-time information about running processes, including memory usage in percentage (%MEM).
You can identify the three processes by their names or PIDs and compare their %MEM values. The process with the highest percentage is using the most memory.
Another option is the `ps aux --sort=-%mem` command, which displays processes sorted by memory usage in descending order. The %MEM column shows the percentage of total RAM consumed by each process.

3. The process hierarchy can be displayed using the `pstree` command or `ps -ejH`.
In Linux, all processes form a tree structure. The root of this tree is usually the `systemd` process (PID 1). Every other process has a parent process, identified by PPID (Parent Process ID).
The hierarchy shows how processes are created. For example, systemd starts a login service, which starts a shell (bash), which can then start other programs such as top. This parent-child structure forms a process tree.

4. The `top` command provides a real-time, continuously updating view of system processes. It is interactive and allows sorting or filtering while running.
The `ps` command provides a static snapshot of processes at the exact moment the command is executed. It is not interactive and requires specific options to filter or format output.
In short, `top` is dynamic monitoring, while `ps` is a one-time process listing.

5. What additional features does `htop` provide compared to `top`?
The `htop` utility provides a more user-friendly and advanced interface compared to `top`. It includes colorized output, easier navigation, mouse support, scrolling capability, and a tree view of processes. It also allows users to select and manage processes more conveniently using function keys.

6. In a typical Android-based mobile operating system, process monitoring tools include the Task Manager, Running Services in Developer Options, memory usage statistics, and battery usage monitoring. These components allow users to view active applications, check RAM consumption, force stop apps, and analyze which applications consume system resources.

7. Android supports terminal-based process management through tools such as ADB (Android Debug Bridge) or terminal emulator applications. Using ADB, users can access the device shell and execute commands like `ps`, `top`, and `kill`. However, advanced process control may require root access.
In contrast, iOS does not normally allow terminal-based process management unless the device is jailbroken.

8. Yes, it is possible to install third-party applications for monitoring and managing processes. On Android devices, applications such as advanced task managers, system monitoring tools, and terminal emulators can provide detailed information about CPU usage, RAM consumption, and background processes. Some advanced tools require root access to provide full functionality.

---

## Висновок (Conclusion)

In this laboratory work, the principles of process management in a Linux operating system were studied and analyzed. The structure and purpose of the `/proc` virtual file system were examined, including the type of system and process information it provides. Methods for viewing active user sessions using commands such as `who` and `w` were explored.

Practical skills in managing processes were developed through the use of terminal key combinations (`Ctrl + C`, `Ctrl + D`, `Ctrl + Z`) and commands such as `jobs`, `bg`, `fg`, `ps`, and `top`. The difference between foreground and background processes was identified, and their practical applications were explained.

During the practical part, the `top` command was used to monitor system activity and identify the most resource-consuming processes. The process suspension, resumption (in both foreground and background modes), and termination procedures were successfully performed.

Overall, this work helped to better understand Linux process control mechanisms and improved practical skills in working with system monitoring and task management tools.

---

## Team Contributions
- **Member 1 ([DimitriyArch])**: Completed the work in a terminal and answered the questions.
- **Member 2 ([PashaGo2007])**: Formatted the Markdown file and completed tasks of preliminary preparation.
- **Member 3 ([Tingem])**: Answered the control questions and did conclusion.
