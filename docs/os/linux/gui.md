## 🖼️ Установка и настройка графической оболочки (GUI) в Linux

Если вы установили минимальную версию Linux без графической среды, её можно легко добавить.

---

### 🖥️ Что такое GUI?

GUI (Graphical User Interface) — это графический интерфейс пользователя. В Linux есть несколько популярных сред:

| DE (Desktop Environment) | Особенности |
|--------------------------|-------------|
| GNOME | Современный, простой, по умолчанию в Ubuntu |
| KDE Plasma | Мощный, гибкий, красивый |
| XFCE | Лёгкий, подходит для старых машин |
| LXDE/LXQT | Очень лёгкие |
| MATE | Классический стиль GNOME 2 |

---

### 🧱 Установка GUI

#### Для Ubuntu/Debian:
```bash
sudo apt update
sudo apt install ubuntu-desktop     # GNOME
sudo apt install kde-plasma-desktop # KDE
sudo apt install xfce4              # XFCE
```

#### Для Arch/Manjaro:
```bash
sudo pacman -S xorg
sudo pacman -S plasma               # KDE
sudo pacman -S gnome                # GNOME
sudo pacman -S xfce4                # XFCE
```

---

### 🚀 Запуск GUI

После установки перезагрузитесь:
```bash
sudo reboot
```

Если GUI не запускается автоматически, можно вручную:
```bash
startx
```

---

### 🧩 Установка Display Manager

| Display Manager | Команда установки |
|-----------------|--------------------|
| LightDM | `sudo apt install lightdm` |
| SDDM (KDE) | `sudo apt install sddm` |
| GDM (GNOME) | `sudo apt install gdm3` |

После установки выберите нужный через:
```bash
sudo dpkg-reconfigure lightdm   # (на Debian/Ubuntu)
```

---

### 🌐 Полезные ссылки

- [Arch Wiki — Desktop Environments](https://wiki.archlinux.org/title/Desktop_environment)
- [How to Install KDE on Ubuntu](https://linuxhint.com/install_kde_plasma_ubuntu/)
- [XFCE Official Site](https://xfce.org/)
