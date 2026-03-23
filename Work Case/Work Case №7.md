
# Work Case №7

## 1. Планування задач в ОС

### Основні функції планувальника задач

Планувальник задач (Task Scheduler / Job Scheduler) — це компонент ОС, який автоматизує виконання процесів.

#### Основні функції:
- Автоматичний запуск програм у заданий час
- Періодичне виконання задач (щоденно, щотижнево тощо)
- Запуск при подіях (вхід користувача, запуск системи)
- Керування ресурсами (пріоритети, черги)
- Логування виконання задач
- Обробка помилок і повторні спроби

### Порівняння: Windows та Linux

| Windows (Task Scheduler) | Linux (Cron) |
| :--- | :--- |
| Графічний інтерфейс (GUI) | Робота через CLI (без GUI) |
| Гнучкі тригери (події, час, стан системи) | Дуже гнучкий синтаксис |
| Підтримка умов (живлення, мережа) | Легка інтеграція зі скриптами |
| Інтеграція з системними службами | Простота для масових задач |

---

## 2. Cron в Linux

### Принцип роботи

Cron читає файл crontab, де описані задачі у форматі:

```
* * * * * команда
│ │ │ │ │
│ │ │ │ └── день тижня (0-7)
│ │ │ └──── місяць
│ │ └────── день місяця
│ └──────── година
└────────── хвилина
```

### Основні команди

#### Редагувати задачі

```Bash
crontab -e
```

#### Переглянути задачі

```Bash
crontab -l
```

#### Видалити задачі

```Bash
crontab -r
```

### Приклади налаштування

#### Виконання у визначений час (08:00)

```Bash
0 8 * * * /home/petryshaka/script.sh
```

#### Двічі на день (08:00 і 18:00)

```Bash
0 8,18 * * * /home/petryshaka/script.sh
```

#### Тільки у будні з 8 до 18 (щогодини)

```Bash
0 8-18 * * 1-5 /home/petryshaka/script.sh
```

#### Різні періоди

| Частота | Cron |
| :--- | :--- |
| Щогодини | `0 * * * *` |
| Щодня | `0 0 * * *` |
| Щомісяця | `0 0 1 * *` |
| Щороку | `0 0 1 1 *` |
| При запуску | `@reboot` |

### Приклади задач

#### Очистка каталогу

```Bash
0 3 * * * rm -rf /tmp/*
```

#### Очистка каталогу

```Bash
0 2 * * * tar -czf /backup/home.tar.gz /home/petryshaka
```

#### Очистка каталогу

```Bash
0 23 * * * shutdown now
```

### Альтернативи Cron

#### systemd timers

Можливості:
- Кращий контроль залежностей
- Логування через journalctl
- Гнучкі таймери

#### anacron

Можливості:
- Виконує задачі навіть якщо ПК був вимкнений
- Підходить для ноутбуків

#### at

Можливості:
- Разове виконання задач

---

## 3. Реалізація задач через Cron та systemd timer

### Cron

```Bash
crontab -e
```

#### Запуск Firefox о 08:00

```Bash
0 8 * * * firefox
```

#### Двічі в день чистка

```Bash
0 9,21 * * * rm -rf /home/petryshaka/tmp/*
```

#### Будні з 8 до 18

```Bash
0 8-18 * * 1-5 echo "Work hours"
```

#### Різні інтервали

```Bash
@reboot echo "System started" >> /home/petryshaka/log.txt
0 * * * * echo "Hourly task"
0 0 * * * echo "Daily task"
0 0 1 * * echo "Monthly task"
0 0 1 1 * echo "Yearly task"
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="526" height="269" src="https://github.com/user-attachments/assets/f1db5e3d-85c4-4c14-835b-77576b81ece6"/></td>
      </tr>
    </table>
  </details>
</h3>

### systemd timer

#### Створення сервісу

```Bash
sudo nano /etc/systemd/system/myscript.service
```

```INI
[Unit]
Description=My Script

[Service]
ExecStart=/home/petryshaka/systemd.sh
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="610" height="180" src="https://github.com/user-attachments/assets/597e1825-9a5e-404b-9487-dfafa074bd0e"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Створення таймера

```Bash
sudo nano /etc/systemd/system/myscript.timer
```

```INI
[Unit]
Description=Run my script daily

[Timer]
OnCalendar=daily

[Install]
WantedBy=timers.target
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="610" height="227" src="https://github.com/user-attachments/assets/5b0675d2-0efc-4e82-84dd-dd99cc4004fb"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Активація

```Bash
sudo systemctl daemon-reexec
```

```Bash
sudo systemctl enable myscript.timer
```

```Bash
sudo systemctl start myscript.timer
```

Але нажаль, чомусь скрипт не бажає стартувати :(

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="902" height="105" src="https://github.com/user-attachments/assets/959dcdf3-b408-40d6-9d8f-5946a5a02bd7"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Словник (Vocabulary)

1. Scheduler — system component that manages and executes tasks at specified times or events.

2. Task Scheduler — tool (especially in Windows) used to automate the execution of programs and scripts.

3. Event-based scheduling — running tasks in response to specific system events (system startup, user login).

4. Cron — time-based job scheduler in Unix/Linux systems used to execute commands automatically at specified intervals.

5. Systemd timer — unit in systemd used to schedule tasks as an alternative to Cron.

6. Anacron — Linux utility that executes scheduled tasks that were missed while the system was powered off.

7. Time-based scheduling — running tasks at predefined times or intervals.

8. Crontab — configuration file where users define scheduled tasks for Cron.

9. Cron daemon (crond) — background service that runs and executes scheduled Cron jobs.

10. Automation — use of systems to perform tasks automatically without human intervention.

---

## Висновок (Conclusion)

In this work, the concept of task scheduling in operating systems was explored, with particular attention to its role in automating routine processes and improving system efficiency. The main functions of task schedulers were analyzed, including executing commands at specified times, repeating tasks at defined intervals, and managing system operations without user intervention. A comparison between Windows and Linux showed that while both systems provide scheduling tools, Linux offers more flexibility and precision through utilities like Cron, whereas Windows emphasizes a more user-friendly graphical approach. The principles of working with Cron were studied, including its configuration and syntax, as well as possible alternatives that provide extended functionality or easier management. Practical implementation involved scheduling various tasks on a Linux virtual machine, such as automated execution at specific times, repeated daily operations, conditional execution based on weekdays or time ranges, and periodic tasks at different intervals. Additionally, an alternative scheduler was installed and used to perform similar operations, confirming that Linux provides multiple powerful tools for task automation and system management.

---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work with scripts.
- **Member 2 — [PashaGo2007](https://github.com/PashaGo2007)**: Did Conclusions, helped at DimitryArch`s work and writted Vocabulary.
