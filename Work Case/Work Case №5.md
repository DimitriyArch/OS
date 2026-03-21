
# Work Case №5

## 1. Робота з периферійними пристроями в Linux

### 1.1 — Механізм роботи ОС Linux з пристроями на прикладі флешки та принтера

У Linux всі пристрої розглядаються як файли, які знаходяться в каталозі `/dev`.

#### Флешка (USB-накопичувач)

При підключенні:
- Ядро Linux визначає пристрій (наприклад `/dev/sdb1`)
- Система може автоматично змонтувати його (через `udev` + `automount`)
- Або користувач монтує вручну

#### Принтер

Для роботи з принтером використовується система друку CUPS (Common UNIX Printing System).

Її взаємодія:
- Керує чергою друку
- Взаємодіє з драйверами
- Приймає завдання друку

### 1.2 — Що таке монтування

Це процес підключення файлової системи пристрою до дерева каталогів Linux.

Використовується для доступу до файлів на пристрої та роботи з USB, дисками, ISO-образами.

#### Як працює

1. Створення точки монтування:

```Bash
sudo mkdir /mnt/usb
```

2. Монтування:

```Bash
sudo mount /dev/sdb1 /mnt/usb
```

3. Відмонтування:

```Bash
sudo umount /mnt/usb
```

### 1.3 — Різниця Linux та Windows

| Характеристика | Linux | Windows |
| :--- | :--- | :--- |
| Робота з пристроями | Через файли (`/dev`) | Через букви дисків (`C:`, `D:`) |
| Монтування | Явне або авто | Автоматичне |
| Гнучкість | Дуже висока | Менша |
| Драйвери | Часто вбудовані | Часто потрібно встановлювати |
| Контроль | Повний контроль через термінал | Переважно через GUI |

Linux дає більше контролю, але вимагає більше знань.

---

## 2. Практична частина

### 2.1 — Підключення флешки до VirtualBox

#### Через надання прямого доступу до USB пристроїв

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="885" height="616" src="https://github.com/user-attachments/assets/c44a8fac-bcab-4f5b-afea-77409a6254f2"/></td>
        <td><img width="854" height="613" src="https://github.com/user-attachments/assets/20c6db07-1e8d-4158-b8c8-61d8316e9994" /></td>
      </tr>
    </table>
  </details>
</h3>

Флешка з'явилася безпосредньо в файловому менеджері та відображається в дереві блокових пристроїв через `lsblk`.

### 2.2 — Копіювання файлу (GUI)

Відкривши файловий менеджер, обираємо флешку та копіюємо в бажане місце.

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="854" height="616" src="https://github.com/user-attachments/assets/e6f98d04-0a6a-48d2-8a06-1d669eb1a911"/></td>
      </tr>
    </table>
  </details>
</h3>

### 2.3 — Копіювання через термінал

```Bash
cp /mnt/file.txt ~/
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="853" height="615" src="https://github.com/user-attachments/assets/58b79774-0ebc-4d4f-890a-2fee291aaf2b"/></td>
      </tr>
    </table>
  </details>
</h3>

### 2.4 — Підключення принтера через CUPS

#### Встановлення та запуск CUPS 

```Bash
sudo apt install cups
```

```Bash
sudo systemctl start cups
```

**[http://localhost:631](http://localhost:631)**

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1535" height="622" src="https://github.com/user-attachments/assets/dd0b94e7-00b5-4c0a-9fc6-6300c1cf8d31"/></td>
      </tr>
    </table>
  </details>
</h3>


### 2.5 — Друк через GUI після налаштування CUPS

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="878" height="622" src="https://github.com/user-attachments/assets/57cb9e99-fc1f-4758-8094-afcdfea24cf5"/></td>
      </tr>
    </table>
  </details>
</h3>

### 2.6 — Друк через термінал

```Bash
lp filename
```

#### Або:

```Bash
lpr filename
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="878" height="621" src="https://github.com/user-attachments/assets/e56d8476-222d-4be4-a052-0cdfdab00a53"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Словник (Vocabulary)

1. Automount — mechanism that automatically mounts a storage device when it is connected to the system, without requiring manual user intervention.

2. Block Device — type of hardware device that stores data in fixed-size blocks (e.g., hard drives, USB flash drives) and is accessed via files in `/dev`.

3. CUPS (Common UNIX Printing System) — printing system used in Linux and Unix-like operating systems that manages print jobs, printers, and queues.

4. Driver — software that allows the operating system to communicate with hardware devices such as printers, USB drives, and other peripherals.

5. Mount Point — directory in the Linux file system where a storage device is attached and made accessible to the user.

6. Mounting — process of attaching a file system from a storage device to a specific directory (mount point) in the Linux file hierarchy.

7. Unmounting — process of safely detaching a mounted file system, ensuring that all data is written and no processes are using the device.

8. Print Queue — list of print jobs waiting to be processed by the printer, managed by the printing system (CUPS).

9. File System — method and data structure used by the operating system to organize and store files on a storage device (ext4, FAT32, exFAT).

10. Filesystem Hierarchy — structure of directories in Linux, starting from the root directory `/`, where all files and devices are organized.

---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the practical part.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**:
