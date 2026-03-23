
# Work Case №8

## 1. Що можна робити в терміналі (заміна GUI)

### Файловий менеджер у терміналі
- `mc` (Midnight Commander) — найпопулярніший
- `ranger` — більш сучасний, з прев’ю

#### Встановлення

```Bash
sudo pacman -S mc ranger
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="424" height="232" src="https://github.com/user-attachments/assets/03a82996-9216-4dc5-9c7c-e4da4066fcd8"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
mc
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="929" height="958" src="https://github.com/user-attachments/assets/30fc677b-ab60-48d2-a8f9-96e74e9f1e8a"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Або

```Bash
ranger
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="929" height="958" src="https://github.com/user-attachments/assets/5af744b1-62a7-4e3b-8317-05f283738cde"/></td>
      </tr>
    </table>
  </details>
</h3>

### Веб-браузер у терміналі
- `lynx` (простий)
- `w3m` (підтримує картинки)
- `links`

#### Встановлення

```Bash
sudo pacman -S lynx w3m links
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="498" height="259" src="https://github.com/user-attachments/assets/bd0ba35a-eab3-4b56-9e80-9d9626c6b190"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
lynx youtube.com
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="930" height="962" src="https://github.com/user-attachments/assets/15f5c330-edd1-4139-89ff-e858d712df14"/></td>
      </tr>
    </table>
  </details>
</h3>

### Пошта в терміналі
- `mutt` (класика)
- `neomutt` (покращена версія)


#### Встановлення

```Bash
sudo pacman -S neomutt
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="610" height="296" src="https://github.com/user-attachments/assets/9a54be4d-ddcb-4a0c-9715-dbd69b8566a7"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
neomutt
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="928" height="176" src="https://github.com/user-attachments/assets/3c6c50c4-9a1f-438e-a7a7-3df4e044660e"/></td>
      </tr>
    </table>
  </details>
</h3>

Потрібно налаштувати SMTP/IMAP (наприклад Gmail)

### Музика в терміналі
- `ncmpcpp` + `mpd`(дуже популярна зв’язка)

#### Встановлення

```Bash
sudo pacman -S mpd ncmpcpp
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="562" height="352" src="https://github.com/user-attachments/assets/df63a06f-375b-4feb-90bd-719029bfa686"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
ncmpcpp
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="547" height="422" src="https://github.com/user-attachments/assets/8109599b-8a6c-48f3-8bc6-6bc9a7f43a70"/></td>
      </tr>
    </table>
  </details>
</h3>

### Торенти через термінал
- `transmission-cli`
- `rtorrent`


#### Встановлення

```Bash
sudo pacman -S transmission-cli rtorrent
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="516" height="255" src="https://github.com/user-attachments/assets/4cb5e432-b358-42f9-90d3-682ca6c0f632"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
transmission-cli blackarch-linux-2023.04.01.ova.torrent
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="839" height="302" src="https://github.com/user-attachments/assets/0b08b252-5637-45fb-bd9a-956c792400e7"/></td>
      </tr>
    </table>
  </details>
</h3>

### Календар і нагадування
- `calcurse` — простий і зручний


#### Встановлення

```Bash
sudo pacman -S calcurse
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="528" height="193" src="https://github.com/user-attachments/assets/9a7d669f-9036-4589-aded-484dd326087d"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
calcurse
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="612" height="448" src="https://github.com/user-attachments/assets/15e3fdbd-4a18-4b95-9e86-6286fcef887e"/></td>
      </tr>
    </table>
  </details>
</h3>

### Перегляд зображень у терміналі
- `feh` (потребує X, але легкий)
- `fim` (чистий tty)
- `viu` (ASCII/Unicode рендеринг)

#### Встановлення

```Bash
sudo pacman -S viu
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="487" height="195" src="https://github.com/user-attachments/assets/5a955a6e-cafa-4e4c-af5e-14c79e10280b"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
viu Screenshot_20260322_005601.png
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="395" height="353" src="https://github.com/user-attachments/assets/2ae3ff9c-b617-4e1d-b708-2afa4caab5d6"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 2. Класичні інструменти адміністратора

### Редактори тексту
- `nano` — простий
- `vim` — потужний
- `neovim` — сучасний vim

#### Встановлення

```Bash
sudo pacman -S nano vim neovim
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="607" height="322" src="https://github.com/user-attachments/assets/f2f0c3c9-bcc9-43e5-a5a0-a669a6cad2f6"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Приклад

```Bash
nano file.txt
vim file.txt
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="645" height="481" src="https://github.com/user-attachments/assets/762e5367-f815-4f8f-bb9b-d28992ec1a6c"/></td>
      </tr>
    </table>
  </details>
</h3>

### Моніторинг системи
- `htop` — найзручніший
- `btop` — красивий (новий)
- `top` — стандартний

#### Встановлення:

```Bash
sudo pacman -S htop btop
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="493" height="205" src="https://github.com/user-attachments/assets/8332355b-aa24-4efc-9ed2-2be22fd29362"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
htop
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1146" height="674" src="https://github.com/user-attachments/assets/bc84d61c-de52-4a18-b87c-f19504b84110"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## 3. Пасхалки

### Паровозик

#### Встановлення:

```Bash
sudo pacman -S sl
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="472" height="186" src="https://github.com/user-attachments/assets/b19b1f68-cae7-4185-92f0-a9ef3eb9ef85"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
sl
```

Якщо помилився і ввів `sl` замість `ls` — отримуєш поїзд

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1145" height="679" src="https://github.com/user-attachments/assets/cb99653e-cdb4-433f-a718-5bf1adbaf96b"/></td>
      </tr>
    </table>
  </details>
</h3>

### Star Wars у терміналі

#### Встановлення:

```Bash
sudo pacman -S inetutils
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="513" height="198" src="https://github.com/user-attachments/assets/3ac6e174-9bf4-4a46-9cea-957a15010af4"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
telnet towel.blinkenlights.nl
```

ASCII-версія Star Wars

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="801" height="498" src="https://github.com/user-attachments/assets/9068bf1d-1026-441e-b8b1-4db4e9df1299"/></td>
      </tr>
    </table>
  </details>
</h3>

### Розмова з коровою

#### Встановлення:

```Bash
sudo pacman -S cowsay
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="419" height="195" src="https://github.com/user-attachments/assets/51f38043-7c3d-409a-bebc-11613cb11b33"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
cowsay Hello
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="229" height="152" src="https://github.com/user-attachments/assets/82210f28-b66b-46fc-bdb1-ab869e5fe994"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Ще цікаві штуки

### Matrix-ефект

#### Встановлення:

```Bash
sudo pacman -S cmatrix
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="516" height="184" src="https://github.com/user-attachments/assets/22d8f564-5cf8-4835-8394-839db21b1d4d"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
cmatrix
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="1139" height="678" src="https://github.com/user-attachments/assets/583d7a62-cfc0-4907-bc60-03775519d4bd"/></td>
      </tr>
    </table>
  </details>
</h3>

### ASCII-art

#### Встановлення:

```Bash
sudo pacman -S figlet
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="509" height="200" src="https://github.com/user-attachments/assets/b79bbc50-f8dc-4ae2-9ed6-894e93d56c8f"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
figlet I used Arch btw :D
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="596" height="200" src="https://github.com/user-attachments/assets/0ba05c12-abac-42a3-b36d-4f0e87001e41"/></td>
      </tr>
    </table>
  </details>
</h3>

### Голос терміналу

#### Встановлення:

```Bash
sudo pacman -S espeak-ng
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="539" height="214" src="https://github.com/user-attachments/assets/d7e787be-136e-46a3-9074-c7b9c6b0e7ef"/></td>
      </tr>
    </table>
  </details>
</h3>

#### Запуск

```Bash
espeak "I'm Mr. Robot — Eliot"
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td><img width="259" height="30" src="https://github.com/user-attachments/assets/28fc97d2-d8fe-4a2f-80df-937d4d33cf08"/></td>
      </tr>
    </table>
  </details>
</h3>

---

## Словник (Vocabulary)

1. Terminal — text-based interface used to interact with the operating system by entering commands.

2. Command Line Interface (CLI) — method of interacting with a computer system using typed commands instead of a graphical interface.

3. File Manager (Terminal-based) — text-based application used to browse and manage files and directories (`Midnight Commander`, `ranger`).

4. Text-based Web Browser — browser that allows users to access websites within the terminal (`lynx`, `w3m`).

5. Email Client (CLI) — terminal-based program used to read, send, and manage emails (`mutt`, `neomutt`).

6. Media Player (CLI) — command-line application used to play audio files (`ncmpcpp`, `mpd`).

7. MPD (Music Player Daemon) — background service that manages music playback and is controlled by clients like ncmpcpp.

8. Torrent Client (CLI) — terminal-based application used to download files via the BitTorrent protocol (`transmission-cli`, `rtorrent`).

9. Calendar Application (CLI) — terminal-based program used for scheduling events and reminders (`calcurse`).

10. Image Viewer (CLI) — program that allows viewing images directly in the terminal (`fim`, `viu`).

---

## Висновок (Conclusion)

In this work, the capabilities of the Linux operating system without a graphical interface were explored, demonstrating that even complex and seemingly GUI-dependent tasks can be effectively performed through the terminal. Various tools and packages were used to manage files, browse the web, read email, play music, download torrents, view images, and organize schedules, proving that the command line environment is highly versatile and powerful. Additionally, common administrative tasks such as text editing and system monitoring were implemented using specialized terminal-based programs, highlighting their efficiency and flexibility compared to graphical counterparts. The work also showcased entertaining and interactive terminal features, emphasizing that the Linux environment is not only functional but also engaging. Overall, the results confirm that Linux provides a comprehensive and efficient command-line ecosystem capable of handling both professional and everyday tasks without the need for a graphical interface.

---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the work in a terminal.
- **Member 2 — [PashaGo2007](https://github.com/PashaGo2007)**: Did Conclusions, helped at DimitryArch`s work and writted Vocabulary.
