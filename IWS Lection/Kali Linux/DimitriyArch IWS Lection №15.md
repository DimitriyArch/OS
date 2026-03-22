
# IWS Lection №15

## 1. Встановлення Kali Linux

### Завантаження `vdi` образу для VirtualBox

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1918" height="841" src="https://github.com/user-attachments/assets/1a17874d-138c-47ff-ae23-0e55aa0826b7"/></td>
      </tr>
    </table>
  </details>
</h3>

### Монтування образу після розархівування застосувавши Open

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1145" height="786" src="https://github.com/user-attachments/assets/11ffd27f-0b77-478e-9942-613aa8d33ab5"/></td>
      </tr>
    </table>
  </details>
</h3>

### Запуск Kali Linux

#### Стандартним обліковим записом є `kali/kali`

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="908" height="613" src="https://github.com/user-attachments/assets/2ac222b1-47a2-4d59-a1cd-46724d358fc2"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 2. Інструмент збору інформації

### Nmap

#### Що робить:
- Сканує мережу
- Визначає відкриті порти
- Виявляє сервіси

Приклад на роутері:

```Bash
nmap -sV 192.168.10.1
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="851" height="532" src="https://github.com/user-attachments/assets/0176c4ff-8ef9-4144-b9a5-a8b39b1c55bc"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Результат:
- Відкриті порти: 53 (`DNS`), 80 (`HTTP`), 443 (`SSL/HTTP`)
- Версії сервісів

---

## 3. Інструмент аналізу вразливостей

### Nikto

#### Що робить:
- Шукає вразливості веб-серверів
- Перевіряє небезпечні налаштування

Приклад на роутері:

```Bash
nikto -h https://192.168.10.1
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="852" height="531" src="https://github.com/user-attachments/assets/48a2b624-0ff6-4c1e-ba6f-8c773901f2c7"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Результат:
- Виявлені вразливості
- Небезпечні файли/директорії

---

## 4. Інструмент тестування на проникнення

### Metasploit

#### Що робить:
- Використовує експлойти
- Дає доступ до системи (симуляція)

Приклад на роутері:

```Bash
msfconsole
```

```Bash
search vsftpd
```

```Bash
use exploit/unix/ftp/vsftpd_234_backdoor
```

```Bash
set RHOST 192.168.10.1
```

```Bash
run
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="852" height="531" src="https://github.com/user-attachments/assets/2823fd8b-4dda-40ad-b897-6e4f9713b09e"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Результат:
- Отримання shell (якщо вразливість є), але мій роутер з прошивкою OpenWRT миттєво відкидає запит :)

---

## 5. Інструмент експлуатації та звітності

### Armitage

#### Що робить:
- GUI для Metasploit
- Візуалізація атак
- Збір інформації та звіти

#### Створення бази:

```Bash
sudo msfdb init
```

#### Запуск:

```Bash
armitage
```

#### Можливості:
- Графічна карта мережі
- Автоматичний підбір атак
- Логи та звіти

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="851" height="532" src="https://github.com/user-attachments/assets/1f9d965d-b8cb-4a8b-9b44-28484ad4eaf5"/></td>
        <td><img width="851" height="532" src="https://github.com/user-attachments/assets/59e5dfb5-5322-47cd-ada6-012cd451b37a"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Сканування на роутері:

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="851" height="532" src="https://github.com/user-attachments/assets/feb091fc-ef78-4c45-aad5-ee955cf473fc"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Висновок (Conclusion)

In this work, the Kali Linux operating system was successfully installed and configured. The main stages of penetration testing were explored using specialized tools. Network reconnaissance was carried out with Nmap, which made it possible to identify active hosts, open ports, and running services. Vulnerability analysis was performed using Nikto, allowing the detection of potential security weaknesses in a web server.

As a result, practical skills in using cybersecurity tools were obtained, and a better understanding of the processes of information gathering, vulnerability analysis, and system exploitation was achieved. This work highlights the importance of system security and the need to protect information systems from potential threats.

---

## Contribution
- **[DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a Kali Linux.
