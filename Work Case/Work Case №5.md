
# Work Case 5

## 1. Робота з периферійними пристроями в Linux

### 1.1 — Механізм роботи ОС Linux з пристроями на прикладі флешки та принтера

### 1.2 — Що таке монтування

### 1.3 — Різниця Linux та Windows

| Характеристика | Linux | Windows |
| :--- | :--- | :--- |
|||
|||
|||
|||
|||

---

## 2. Практична частина

### 2.1 — Підключення флешки до VirtualBox

```Bash
lsblk
```

<h3>
  <details>
    <summary>Скріншоти</summary>
    <table>
      <tr>
        <td></td>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

### 2.2 — Копіювання файлу (GUI)

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

### 2.3 — Копіювання через термінал

```Bash
lsblk
```

```Bash
cp /mnt/file.txt ~/
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

### 2.4 — Підключення принтера через CUPS

```Bash
sudo pacman -S cups
```

```Bash
sudo systemctl start cups
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

```Bash
http://localhost:631
```

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

### 2.5 — Друк через GUI

<h3>
  <details>
    <summary>Скріншот</summary>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </details>
</h3>

### 2.6 — Друк через термінал

```Bash
lp file.txt
```

```Bash
lpr file.txt
```

---

## Висновок (Conclusion)



---

## Team Contributions
- **Member 1 — [DimitriyArch](https://github.com/DimitriyArch)**: Formatted the Markdown file and сompleted the practical part.
- **Member 2 — [PavloGo2007](https://github.com/PashaGo2007)**:
