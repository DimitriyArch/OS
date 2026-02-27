
# Work-Case №2

## 1. Встановлення гіпервізора II типу
Для виконання даного ворк-кейсу було обрано гіпервізор Oracle VM VirtualBox.
### Причини вибору:
* Безкоштовний та кросплатформний.
* Простий у налаштуванні.
* Підтримка USB, NAT, Bridged Adapter.

---

### Процес встановлення:
<p align="center">
  <br>
  <img src="https://github.com/user-attachments/assets/f118745b-0d46-414b-b2a8-cb2523a72a55" width="482"/>
  <br>
  <b>Скріншот 1</b> — Початок встановлення Oracle Virtual Box
  <br><br>
  <img src="https://github.com/user-attachments/assets/9ce70603-9943-4f5b-9bf6-e46cd829bbc3"/>
  <br>
  <img src="https://github.com/user-attachments/assets/ff5ff35c-ebb0-47e5-bcd0-b5c09a3cdc4e"/>
  <br>
  <b>Скріншот 2, 3</b> — Процесс встановлення Oracle Virtual Box
  <br><br>
  <img src="https://github.com/user-attachments/assets/e911997e-52e4-4341-bd47-46fb6028d23e"/>
  <br>
  <b>Скріншот 4</b> — Завершення встановлення Oracle Virtual Box
  <br>
  </p>
  
---

## 2. Базові дії у гіпервізорі
### 2.1 — Створення нової віртуальної машини

<p align="center">
 <br><br>
 <img src="https://github.com/user-attachments/assets/4e62138f-9a61-4de5-9ec3-64ecd8fd838c"/>
 <br><br>
 <img src="https://github.com/user-attachments/assets/d833f2ce-abf9-4bd6-99cb-f3dae56209d6"/>
 <br><br>
 <img src="https://github.com/user-attachments/assets/bf1f1d6f-d6b0-41b6-ba9d-673c934efb80"/>
 <br><br>
</p>

### 2.2 — Вибір/додавання доступного для віртуальної машини обладнання

<p align="center">
 <br><br>
 <img src="https://github.com/user-attachments/assets/1490d61a-2d0c-496b-8306-fbb7d9a07595"/>
 <br><br>
 </p>
 
### 2.3 — Налаштування мережі та підключення до точок Wi-Fi

 <p align="center">
 <br><br>
 <img src="https://github.com/user-attachments/assets/7a234f8a-ab46-4ff4-ac6a-68f9a242e197"/>
 <br><br>
 </p>
 
### 2.4 — Можливість роботи з зовнішніми носіями

<p align="center">
 <br><br>
 <img src="https://github.com/user-attachments/assets/05527907-2169-467c-8b45-9f25fb5d8ef1"/>
 <br><br>
 </p>

---

## 3. Встановлення GNU/Linux з графічною оболонкою
Для першої віртуальної машини був обраний дистрибутив Ubuntu.
### Параметри:
* RAM — 4096 MB
* CPU — 2 Core
* Disk — 25 GB

<p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/e782a478-6d50-4553-9de5-79b8b90b5fda"/>
 <br><br>
 </p>

### Етапи встановлення:
1. Завантаження ISO.

<p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/a6a1e3c0-9d99-419a-a347-96f846320194"/>
 <br><br>
 </p>
 
3. Вибір "Install Ubuntu" -> "Interactive installation" -> "Standard installation"

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/422daea3-3799-41e1-982a-27f9311a10ff"/>
 <br><br>
 </p>
 
4. Створення користувача.

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/15dafa8d-7255-4601-9204-df0994f38aec"/>
 <br><br>
 </p>

5. Перезавантаження

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/369a3842-60be-4416-89a5-be98ed8ed1f9"/>
 <br><br>
 </p>

У підсумку маємо встановлений дистрибутив GNU/Linux Ubuntu з графічною оболонкою GNOME.

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/5013817f-a388-48c8-88e4-92f62743d64e"/>
 <br><br>
 </p>

---

## 4. Створення другої віртуальної машини
Для іншої віртуальної машини був обраний дистрибутив Ubuntu Server (без GUI).
### Параметри:
* RAM — 2048 MB
* CPU — 2 Core
* Disk — 30 GB

### 4.1 — Запуск Ubuntu Server та встановлення GNOME

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/eeab4c8f-39be-4899-afca-6c93bcbf1b77"/>
 <br><br>
 </p>

### 4.2 — Ubuntu Server з чистим GNOME

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/e143823e-f155-43d1-8156-d2cd405762c1"/>
 <br><br>
 </p>

### 4.3 — Встановлення додатково KDE Plasma

  <p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/ed186dae-1752-4e5f-aa39-c06207fd84cd"/>
 <br><br>
 </p>

### 4.4 — Ubuntu Server з KDE Plasma

<p align="center">
 <br>
 <img src="https://github.com/user-attachments/assets/ef497d9b-0c5d-408e-885b-7700938366d9"/>
  <br>
  <img src="https://github.com/user-attachments/assets/44dfb131-ee77-4399-a8eb-12e69397197c"/>
 <br><br>
 </p>

---

## 5. Порівняння GNOME та KDE Plasma

| **Критерій**              | **GNOME**                                          | **KDE Plasma**                                       |
| ------------------------- | -------------------------------------------------- | ---------------------------------------------------- |
| **Концепція дизайну**     | Мінімалістичний, фокус на простоті й послідовності | Гнучкий і настроюваний, багато опцій для користувача |
| **Інтерфейс користувача** | Панель зверху, Activities, робочі простори         | Традиційна панель, меню запуску, віджети             |
| **Настроювання**          | Обмежене (через розширення)                        | Дуже широкі можливості без додаткових інструментів   |
| **Споживання ресурсів**   | Середнє / вище середнього                          | Нижче або середнє, добре оптимізоване                |
| **Продуктивність**        | Плавний, але може споживати більше RAM             | Швидкий і ефективний                                 |
| **Оновлення**             | Стабільні релізи, менше експериментів              | Часті оновлення, активний розвиток                   |
| **Екосистема додатків**   | Стильні, уніфіковані GNOME Apps                    | Потужні та функціональні KDE Apps                    |
| **Робочий простір**       | Мінімалізм, без зайвих елементів                   | Багато панелей, віджетів і режимів                   |
| **Підтримка Wayland**     | Активна, добре реалізована                         | Також добре підтримується                            |
| **Цільова аудиторія**     | Користувачі, що цінують простоту                   | Користувачі, що люблять гнучке налаштування          |

---

## Англійський словник (English vocabulary)

Type 2 Hypervisor – Software that runs on a host operating system and allows you to create and manage virtual machines (for example VirtualBox or VMware Workstation)

VirtualBox / VMware Workstation / Hyper-V – Programs used to create and manage virtual machines

Create a Virtual Machine – The process of setting up a new virtual environment with its own operating system, CPU, RAM, and storage

Virtual Hardware – Simulated components such as virtual CPU, RAM, hard disk, and network adapter assigned to a virtual machine

Network Configuration – Setting how a virtual machine connects to the internet or local network (for example NAT or Bridged mode)

External Storage (USB Flash Drive) – A removable device used to store and transfer data, which can be connected to a virtual machine

GNU/Linux Distribution – A specific version of Linux that includes the kernel and additional software such as Ubuntu or Debian

CLI (Command Line Interface) – A text-based way to interact with the operating system using commands

GUI (Graphical User Interface) – A visual interface with windows, icons, and menus

GNOME – A popular Linux desktop environment that provides a graphical interface

Compare Features – To analyze differences in functionality, performance, and usability between systems

--- 

## Висновок (Conclusion)

Продемонстрували практичні можливості гіпервізора другого типу, створення та налаштування віртуальних машин із різними конфігураціями, а також встановлення Linux-систем у GUI та CLI варіантах. Порівняння GNOME і KDE Plasma показало відмінності в підходах до інтерфейсу та налаштування середовища. Отриманий результат підтверджує ефективність використання віртуалізації для тестування, адміністрування та аналізу операційних систем.

---

## Team Contributions
- **Member 1 ([DimitriyArch])**: Completed the work with install GUI and formatted the Markdown file.
- **Member 2 ([PashaGo2007])**: Completed the work installted Ubuntu and added English conclusions.
- **Member 3 ([Tingem])**: Completed the comparison table and wrote a conclusion.
