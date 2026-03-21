
# Work Case №6

## 1. Встановлення командних інтерпретаторів

### Візьмемо 2 додаткових shell:
- `fish`
- `zsh`

```Bash
sudo pacman -S fish zsh
```

### Перевірка встановлених shell

```Bash
cat /etc/shells
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="474" height="573" src="https://github.com/user-attachments/assets/0e15b087-0b1f-4f99-a18f-c177cabfa01c"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Короткий опис

| bash | fish | zsh |
| :--- | :--- | :--- |
| Стандартний shell у Linux | Дуже зручний і сучасний shell | Розширена версія bash |
| Підтримка скриптів | Підсвітка синтаксису | Автодоповнення (smart completion) |
| Сумісність майже з усіма системами | Автопідказки прямо під час введення | Підтримка тем (oh-my-zsh) |
| Використовується адміністраторами | Не повністю сумісний з bash-скриптами | Зручний для розробників |

---

## 2. Створення користувачів і груп

### Створення груп

```Bash
sudo groupadd tech_support
sudo groupadd developers
sudo groupadd financiers
sudo groupadd founders
sudo groupadd guests
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="258" height="168" src="https://github.com/user-attachments/assets/6919dcd8-8f3c-4784-823a-9c09d4f72e1b"/></td>
      </tr>
    </table>
  </details>
</h3>

### Створення користувачів

#### Technical support (bash)

```Bash
sudo useradd -m -G tech_support -s /bin/bash tech1
sudo useradd -m -G tech_support -s /bin/bash tech2
```

#### Developers (fish)

```Bash
sudo useradd -m -G developers -s /bin/fish dev1
sudo useradd -m -G developers -s /bin/fish dev2
```

#### Financiers (без shell)

```Bash
sudo useradd -m -G financiers -s /usr/bin/nologin fin1
sudo useradd -m -G financiers -s /usr/bin/nologin fin2
```

#### Founders (zsh)

```Bash
sudo useradd -m -G founders -s /bin/zsh founder1
sudo useradd -m -G founders -s /bin/zsh founder2
```

#### Guests (без shell)

```Bash
sudo useradd -m -G guests -s /usr/bin/nologin guest1
sudo useradd -m -G guests -s /usr/bin/nologin guest2
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="455" height="340" src="https://github.com/user-attachments/assets/582dad32-e724-4bc2-b17e-4c5bb2255f9b"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 3. Таблиця призначення shell за замовчуванням

| Група | Shell |
| :--- | :--- |
| Technical support | `/bin/bash` |
| Developers | `/bin/fish` |
| Financiers | `/usr/bin/nologin` |
| Founders | `/bin/zsh` |
| Guests | `/usr/bin/nologin` |

### Перевірка створених груп та користувачів в них 

```Bash
cat /etc/group
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="274" height="276" src="https://github.com/user-attachments/assets/0ebf265f-b68d-4350-9a55-14293d3e45a7"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 4. Приклади роботи користувачів

### Перехід до користувача

```Bash
su - founder1
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="550" height="339" src="https://github.com/user-attachments/assets/44102ce3-3a84-4a44-84d4-1dd71e64b7ee"/></td>
      </tr>
    </table>
  </details>
</h3>

### Приклади команд з кожним командним інтерпретатором

#### Інформація про систему

```Bash
uname -a
```

#### Поточна дата

```Bash
date
```

#### Поточний каталог

```Bash
pwd
```

#### Вміст каталогу

```Bash
ls -la
```

#### Інформація про користувача

```Bash
whoami
```

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="783" height="289" src="https://github.com/user-attachments/assets/cbdfc9ed-7361-48a1-aced-cf39c2399407"/></td>
        <td><img width="783" height="449" src="https://github.com/user-attachments/assets/8228dbd4-29bb-47f8-9a8e-e571686bf19e"/></td>
        <td><img width="783" height="268" src="https://github.com/user-attachments/assets/38377f30-11c8-4a8e-8015-d4f3813da52a"/></td>
      </tr>
    </table>
  </details>
</h3>

### Перевірка заборони shell користувачам груп Financiers та Guests

```Bash
su - fin1
```

```Bash
su - guest1
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="329" height="186" src="https://github.com/user-attachments/assets/e9a90315-e834-40bc-9ce3-069e174a508e"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Словник (Vocabulary)

1. Account — record in the operating system that allows a user to log in and access system resources.

2. Bash (Bourne Again Shell) — widely used command-line interpreter in Linux systems that supports scripting and automation.

3. Default Shell — command interpreter that starts automatically when a user logs into the system.

4. Fish (Friendly Interactive Shell) — modern command-line shell known for user-friendly features like syntax highlighting and autosuggestions.

5. Zsh (Z Shell) — advanced shell that extends Bash with additional features like improved tab completion and customization.

6. Nologin — special shell (`/usr/bin/nologin`) that prevents users from logging into the system.

7. Permissions — rules that define how users can access files and system resources.

8. User — individual account that can log into and interact with the operating system.

9. User Group — set of users categorized together to simplify permission management.

10. Root User — administrative user with full access to all system resources and commands.

---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PashaGo2007](https://github.com/PashaGo2007)**: 
