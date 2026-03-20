
# Work Case №4

## 1. Основні поняття та огляд менеджерів пакетів

### Що таке пакет

Пакет — це спеціально підготовлений файл, який містить:
- Програму або бібліотеку
- Службову інформацію (версія, залежності)
- Скрипти для встановлення та видалення

Простіше кажучи, пакет — це готова до встановлення програма у форматі, зрозумілому для системи (наприклад `.deb`, `.rpm`).

### Що таке репозиторій

Репозиторій — це сервер або сховище в інтернеті, де зберігаються пакети.

Він містить:
- Тисячі програм
- Інформацію пр версії
- Залежності між пакетами

Менеджер пакетів автоматично:
- Знаходить потрібну програму
- Завантажує її
- Встановлює разом із залежностями

### Огляд менеджерів пакетів у Linux

#### 1. Pacman — Arch-based

Можливості:
- Дуже швидкий
- Простий синтаксис
- Повний контроль над пакетами

#### 2. APT (Advanced Package Tool) — Debian-based

Можливості:
- Автоматична установка залежностей 
- Оновлення системи
- Пошук пакетів
- Простий синтаксис

#### 3. Yum & DNF (Dandified Yum) — Fedora-based

Yum — старіший менеджер, зараз замінений на DNF.

Можливості:
- Швидша робота ніж `yum`
- Покращене управління залежностями
- Підтримка репозиторіїв

#### 4. pkgtools — Slackware-based

Можливості:
- Дуже проста структура пакетів (.tgz, .txz)
- Відсутнє автоматичне вирішення залежностей
- Користувач сам контролює встановлення бібліотек

#### 5. Portage — Gentoo-based

Можливості:
- Тонке налаштування функціоналу програм
- Можливість виключати непотрібні компоненти
- Повний контроль над залежностями

#### 6. Zypper — openSUSE-based

Можливості:
- Автоматичне вирішення залежностей
- Інтеграція з графічним інструментом YaST
- Підтримка репозиторіїв та оновлень у реальному часі

#### 7. apk — Alpine Linux-based

Можливості:
- Дуже легкий і швидкий
- Орієнтований на безпеку
- Часто використовується в Docker-контейнерах

#### 8. Nix — NixOS

Можливості:
- Відкат системи (rollback)
- Відтворювані збірки
- Повна ізоляція залежностей

#### 9. Snap — Universal

Можливості:
- Працює у різних дистрибутивах
- Ізольовані додатки
- Автоматичні оновлення

#### 10. Flatpak — Universal

Можливості:
- Безпечна ізоляція
- Підтримка графічних додатків
- Керування дозволами

---

## 2. Менеджер пакетів у системі — Pacman

Потужний інструмент для управління пакетами в Arch-based системах. Він дозволяє:
- встановлювати програми
- оновлювати систему
- видаляти пакети
- працювати з репозиторіями
- автоматично керувати залежностями

### Основні команди Pacman

#### Оновлення бази пакетів

```Bash
sudo pacman -Sy
```

#### Повне оновлення системи

```Bash
sudo pacman -Syu
```

#### Пошук пакета

```Bash
pacman -Ss vlc
```

#### Інформація про пакет

```Bash
pacman -Si vlc
```

#### Встановлення пакета

```Bash
sudo pacman -S vlc
```

#### Перегляд встановлених пакетів

```Bash
pacman -Q
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="283" height="877" src="https://github.com/user-attachments/assets/c751749a-8de9-4963-9cb2-bb10810bc60a"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Пошук серед встановлених

```Bash
pacman -Qs vlc
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="786" height="851" src="https://github.com/user-attachments/assets/38c82364-c0c7-4939-953e-5eddb2155588"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Видалення пакета

```Bash
sudo pacman -R vlc
```

#### Видалення з залежностями

```Bash
sudo pacman -Rs vlc
```

#### Повне очищення (залежності + конфіги)

```Bash
sudo pacman -Rns vlc
```

#### Очищення кешу

```Bash
sudo pacman -Sc
```

#### Робота з репозиторіями

У Pacman репозиторії налаштовуються у файлі:

```Bash
/etc/pacman.conf
```

Стандартні репозиторії:
- core
- extra
- community

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="795" height="881" src="https://github.com/user-attachments/assets/b0830b62-dc76-421f-ad02-674a00be622c"/></td>
      </tr>
    </table>
  </details>
</h3>

#### AUR (Arch User Repository)

Це додатковий репозиторій, де користувачі публікують пакети.

Для роботи з AUR використовують помічники, наприклад:
- `yay`
- `paru`

Встановлення через yay:

```Bash
yay -S vlc
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="726" height="354" src="https://github.com/user-attachments/assets/cfcc1357-fec6-4880-bef1-fb420691a9a1"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 3. Встановлення програм

### Відео/аудіо плеєр

```Bash
sudo pacman -S vlc
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="728" height="367" src="https://github.com/user-attachments/assets/3c948da1-b678-48cc-ab7d-a7d65e6f2457"/></td>
      </tr>
    </table>
  </details>
</h3>

### Середовище програмування C++

```Bash
sudo pacman -S vscodium
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="880" height="264" src="https://github.com/user-attachments/assets/ed92c1b3-c194-459e-bcc8-ccce0369e46a"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 4. Встановлення через графічний інтерфейс

Використав Flathub (`flatpak`) для встановлення Easy Effects.

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="1912" height="1035" src="https://github.com/user-attachments/assets/c0349ae4-f48a-4def-839b-53184d3f0674"/></td>
      </tr>
      <tr>
        <td><img width="1912" height="1035" src="https://github.com/user-attachments/assets/5ddfb7b2-ff98-41d6-8b06-0bec14db7edd"/></td>
      </tr>
      <tr>
        <td><img width="1912" height="1074" src="https://github.com/user-attachments/assets/1821c5a5-c19c-49c3-9d19-729ae5b78d53"/></td>
      </tr>
    </table>
  </details>
</h3>

Якщо не вдається встановити через Flathub, є також можливість зробити це через термінал.

```Bash
flatpak install flathub com.github.wwmm.easyeffects
```

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td><img width="1912" height="1030" src="https://github.com/user-attachments/assets/c76ce193-0ac3-4d86-864d-d5f8ccc515f6"/></td>
      </tr>
      <tr>
        <td><img width="867" height="341" src="https://github.com/user-attachments/assets/e562c48d-0aa9-43e5-8e10-8a8e801b0e97"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a VirtualBox.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**:
