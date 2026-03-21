
# Work Case №3

## 1. Клонування віртуальної машини та експорт ОС

### Клонування віртуальної машини в VirtualBox

Дозволяє створити точну копію існуючої ОС разом з усіма її налаштуваннями, програмами та файлами.

#### Етапи клонування:
- Вибір ВМ
- ПКМ та обрати Clone
- Вказати ім'я нової ВМ
- Обрати тип клонування та режим
- Натиснути Finish

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="698" height="468" src="https://github.com/user-attachments/assets/ba7b3913-c37d-41f6-a768-da3ad47f20ef"/></td>
      </tr>
    </table>
  </details>
</h3>

Після завершення процесу у списку VirtualBox з’явиться нова віртуальна машина — копія оригінальної.

### Експорт віртуальної машини

Використовується для перенесення віртуальної машини в інше середовище віртуалізації.

#### Етапи експорту:
- Обрати Export
- Вибір ВМ
- Вказати місце збереження
- Натиснути Finish

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="689" height="470" src="https://github.com/user-attachments/assets/1fa8387b-d3e3-43dc-bab2-f33d493cadd6"/></td>
      </tr>
    </table>
  </details>
</h3>

Отриманий файл можна імпортувати в інший VirtualBox або іншу систему віртуалізації.

---

## 2. Типи мережевих з’єднань у віртуальних машинах

У середовищі віртуалізації підтримується декілька типів мережевих підключень.

#### NAT (Network Address Translation)

Дозволяє віртуальній машині отримувати доступ до Інтернету через мережу хост-комп’ютера.

Особливості:
- Віртуальна машина отримує приватну IP-адресу
- Має доступ до Інтернету
- Інші пристрої мережі не можуть напряму підключитися до цієї машини

#### Bridged Adapter (Мережевий міст)

Віртуальна машина підключається до фізичної мережі як окремий комп’ютер.

Особливості:
- Отримує IP-адресу з тієї ж мережі, що й хост
- Доступна іншим пристроям у мережі
- Працює як звичайний фізичний комп’ютер

#### Host-only Adapter

Створює окрему мережу між хостом та віртуальними машинами.

Особливості:
- оступ до Інтернету зазвичай відсутній
- заємодія можлива лише між хостом і віртуальними машинами
- икористовується для тестування та навчання

#### Internal Network

Створює внутрішню мережу тільки між віртуальними машинами.

Особливості:
- Хост-комп’ютер не має доступу до цієї мережі
- Обмін даними можливий лише між віртуальними машинами
- Використовується для ізольованих середовищ

---

## 3. Налаштування мережі між робочою ОС та її клоном

Для взаємодії двох віртуальних машин їх необхідно підключити до однієї мережі, наприклад Host-only Adapter або Internal Network.

Після запуску обох ОС можна перевірити мережеві параметри.

### Базові команди для налаштування мережі 

Перегляд мережевих інтерфейсів та параметрів

`ip a` — відображає всі мережеві інтерфейси та їх IP-адреси.

`ifconfig` за встановленого `net-tools` — показує IP-адресу, маску мережі та статистику роботи інтерфейсів.

Перевірка зв’язку між машинами

```Bash
ping -c4 192.168.10.102
```

```Bash
ping -c4 192.168.10.103
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1708" height="618" src="https://github.com/user-attachments/assets/ab80fcf1-7b49-4bfd-8701-066e944eb9fa"/></td>
      </tr>
    </table>
  </details>
</h3>

### Перевірка доступу до Інтернету

На обох машинах відкритий YouTube.

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1706" height="615" src="https://github.com/user-attachments/assets/97ce9c4c-4ed3-4daf-9b60-39eda0ceea75"/></td>
      </tr>
    </table>
  </details>
</h3>

### Обмін повідомленнями між двома ОС

Була використана утиліта `netcat`.

На першій машині прослуховування порту 1234:

```Bash
nc -l 1234
```

На другій машині підключення до першої порту 1234:

```Bash
nc 192.168.10.103 1234
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1707" height="618" src="https://github.com/user-attachments/assets/de8f20c2-1213-4319-9afc-6bf872043146"/></td>
      </tr>
    </table>
  </details>
</h3>

### Спільна мережева папка

Була використана `Samba` встановлена на першу машину

За адресою `smb://192.168.10.103/` на другій машині відтепер доступна спільна папка.

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1707" height="618" src="https://github.com/user-attachments/assets/8b74d4e2-3961-4a6d-a9e8-6155b46970e1"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 4. Обмін інформацією між основною ОС та віртуальними ОС

Обмін файлами між хост-системою та віртуальними машинами можна організувати кількома способами.

### Shared Folders (Спільні папки)

У VirtualBox можна створити папку, спільну для хоста та віртуальної машини.

#### Етапи:

- Додавання спільної папки в ВМ

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="874" height="624" src="https://github.com/user-attachments/assets/911ab9a7-bbb9-4334-9733-c7f533b643a8"/></td>
        <td><img width="912" height="625" src="https://github.com/user-attachments/assets/5a0bedf4-5804-4faa-bb9e-9a1cd618e252"/></td>
      </tr>
    </table>
  </details>
</h3>

- Встановлення `virtualbox-guest-utils` та додавання користувача до групи `vboxsf`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="876" height="625" src="https://github.com/user-attachments/assets/53c8cbaf-0be5-47ac-a8d3-a6f5a11cf9a4"/></td>
      </tr>
    </table>
  </details>
</h3>

- Після цього папка буде доступна у файловій системі віртуальної машини

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="876" height="625" src="https://github.com/user-attachments/assets/16cccbba-c665-4213-b69d-fe98388e89c2"/></td>
      </tr>
    </table>
  </details>
</h3>

### Копіювання файлів

Наприклад:

#### Копіювання з основної ОС на робочий стіл ВМ:

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1594" height="619" src="https://github.com/user-attachments/assets/f0086989-6768-48d0-bf31-ca8ececcc4ee"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Копіювання з ВМ на основну ОС:

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1594" height="619" src="https://github.com/user-attachments/assets/a5f029ea-ce21-4bf1-8720-8bd2431366df"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Словник (Vocabulary)

1. Virtual Machine (VM) — software-based emulation of a physical computer that runs an operating system and applications.

2. Virtualization — process of creating virtual versions of hardware platforms, storage devices, or network resources.

3. Clone (Virtual Machine Clone) — copy of an existing virtual machine, including its operating system, settings, and data.

4. Full Clone — completely independent copy of a virtual machine that does not rely on the original VM.

5. Linked Clone — virtual machine that shares virtual disk files with the original VM, saving storage space.

6. Export Appliance — process of packaging a virtual machine into a file (usually OVA) for transfer or backup.

7. Netcat (nc) — networking utility used for reading and writing data across network connections.

8. Shared Folder — directory that is accessible from both the host system and virtual machines.

9. OVA (Open Virtual Appliance) — file format used to distribute virtual machines, containing configuration and disk data.

10. Samba — software suite that enables file and print sharing between Linux and Windows systems.

11. Host OS (Host Operating System) — main operating system installed on the physical computer.

12. Guest OS (Guest Operating System) — operating system running inside a virtual machine.

---

## Висновок (Conclusion)

In this work-case, the tasks focused on cloning, networking, and data exchange between virtual machines. Cloning a VM creates an exact copy, either full or linked, and exporting it uses formats like OVF or OVA for use in other virtualization environments.

Virtual networking types were explored: NAT allows internet access via the host while isolating the VM, Bridged connects the VM directly to the physical network, Host-only limits communication to the host and VMs, and Internal Network allows VM-to-VM communication only. Network setup between the original VM and its clone included configuring IP addresses, testing connectivity, streaming content to confirm internet access, sending messages, and transferring files through a shared folder.

Data exchange between the host OS and VMs was achieved via shared folders or drag-and-drop, allowing files to move from the host to VMs and back, enabling efficient interaction between virtual and main operating systems.

---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a VirtualBox.
- **Member 2 — [PashaGo2007](https://github.com/PashaGo2007)**: Did Conclusions, helped with 4 item and writted Vocabulary.
