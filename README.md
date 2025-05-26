# fedora: linux
# 🚀 Fedora Linux Optimization Guide

Набор проверенных настроек для ускорения работы и улучшения внешнего вида Fedora Linux (GNOME)

## 🔧 Основные оптимизации

### 🚀 Системные настройки

# Обновление системы

```bash
 sudo dnf upgrade --refresh
```
# Установка fastfetch (альтернатива neofetch)

```bash
 sudo dnf install fastfetch
```
В конце ```nano ./bashrc``` ```nano ./zshrc``` добавить fastfetch. 

### Красивый fastfetch:

 Шрифт:  Adwaite Mono Bold 10

⚙️ Настройка конфигурации Fastfetch:

    Перейдите в свой каталог .config → cd ~/.config

    Если вы не видите папку fastfetch , создайте ее → mkdir -p fastfetch

    Сгенерируйте конфигурацию по умолчанию → fastfetch --gen-config

    Удалите файл конфигурации по умолчанию → rm fastfetch/config.jsonc

    Загрузите мою обновленную конфигурацию → wget https://raw.githubusercontent.com/harilvfs/fastfetch/refs/heads/old-days/fastfetch/config.jsonc

    Закройте терминал и откройте его снова.

    Теперь запустите → fastfetch

🖥️ Расширения GNOME

- Desktop Icons NG (DING) - ярлыки на рабочий стол

- Blur my Shell - эффект размытия панели
 
- User Themes - поддержка кастомных тем
 
- GSConnect & OpenWeather - интеграция с телефоном и погода
 
- AppIndicator Support - отображение фоновых приложений
 
- Unblank lock screen - предотвращение отключения экрана
 
- Forge - оконный менеджер

# ⚡ Оптимизация SSD
```bash
sudo nano /etc/fstab
```
Добавьте параметры:

```bash
compress=zstd:1,defaults,noatime,discard=async
```

# 🐧 Ускорение DNF
```bash
sudo dnf install dnf-automatic
```
```bash
sudo systemctl enable dnf-automatic.timer
```

Конфигурация:
```bash
 sudo nano /etc/dnf/dnf.conf
```

```ini
fastestmirror=True
max_parallel_downloads=10
defaultyes=True
keepcache=True
```
# 🎨 Персонализация
🖼️ Темы и иконки

Установка Papirus иконок:
```bash
sudo dnf install papirus-icon-theme
```
# Цветные папки
```bash
wget -qO- https://git.io/papirus-folders-install | sh
papirus-folders -C black --theme Papirus-Dark
```


# Утилиты для настройки GNOME
```bash
sudo dnf install gnome-tweaks
```

# Установка кодеков
```bash
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```
```bash
sudo dnf install lame\* --exclude=lame-devel
```
```bash
sudo dnf group upgrade --with-optional Multimedia
```
⚙️ Дополнительные настройки
🔄 Выбор ядра
```bash
sudo dnf install grubby
```
```bash
sudo grubby --info=ALL | grep -E "^kernel|^index"
```
```bash
sudo grubby --set-default-index=0
```
```bash
sudo grubby --default-title
```

<div align="center"> <sub>Создано с ❤️ для Fedora Linux</sub> </div> 

