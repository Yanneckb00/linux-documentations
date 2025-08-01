# Arch Linux
## Arch Setup
- Boot from USB
- `loadkeys de-latin1`
- `ip addr show`

### WIFI CONNECT:
- `iwctl`
- `station wlan0 get-networks`
- `station wlan0 connect "<network-name>"`
- `exit`

- `ip addr show`
- `ping -c 4 archlinux.org`

### SSH:
- `systemctl status sshd`
- check if running or else `systemctl start sshd`
- set password `passwd`
- connect with another terminal: `ssh root@<ip>`

### Arch Linux Install:
- `pacman -Sy && pacman-key --init && pacman -S archlinux-keyring && archinstall`
- archinstall language: `en`
- locales:
   - keyboard layout: `de`
   - locale language: `de_DE.UTF-8`
   - locale encoding: `UTF-8`
- disk configuration: best effort (no `/home` directory!)
- hostname: `archlinux`
- root password: `****`
- user account:
   - username: `username`
   - password: `****`
- profile:
   - profile: `GNOME, Hyprland`
   - graphics driver: `AMD / ATI (open source)`
   - greeter: `gdm`
- audio: `pipewire`
- kernels: `linux, linux-lts`
- network configuration: `network manager`
- timezone: `Europe/Berlin`
- additional packages: `7zip kitty firefox nerd-fonts ufw`

## For Gnome:
- Reboot without Boot USB-Stick!

## For Hyperland:
after that go into chroot:
- `su <username>`
- `sudo systemctl enable ufw`
- `sudo pacman -S --needed git base-devel`
- `sudo pacman -S kitty`
- For HyDE Package:
    - `git clone --depth 1 https://github.com/HyDE-Project/HyDE ~/HyDE`
    - `cd ~/HyDE/Scripts`
    - `./install.sh`
- 

##############
# POST SETUP #
##############

## Post Setup

### Install YAY:
```sh
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

### activate multilib
- `sudo nano /etc/pacman.conf`
- comment in: `[multilib]` and `Include = /etc/pacman.d/mirrorlist`
- after that `sudo pacman -Sy`

### Install first YAYs on Arch Linux
- Zen: `yay -S zen-browser`
- VSCode: `yay -S visual-studio-code-bin`
- Discord: `yay -S discord`
- Spotify: `yay -S spotify`

### Install first pacmans on Arch Linux
- Flatpak Store: `sudo pacman -S flatpak`
- OpenRGB: `sudo pacman -S openrgb`
- Gnome Tweaks: `sudo pacman -S gnome-tweaks gnome-shell-extensions`
- Firewall:
```sh
sudo pacman -S ufw
sudo ufw enable
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
```

# Terminal
## Basic Setup
- install kitty: `sudo pacman -S kitty`
- install yazi: `sudo pacman -S yazi ffmpeg 7zip jq poppler fd ripgrep fzf zoxide imagemagick && yay -S resvg`

## ZSH Requirements
```sh
sudo pacman -S fzf zsh git stow lazygit starship zoxide fastfetch lsd tmux neovim zinit
```

## Oh My ZSH
- OMZ: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
- zinit `bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"`

## Flatpak Apps
- Extension Manager

## GNOME Customization
-> https://extensions.gnome.org/
- AppIndicator and KStatusNotifierItem Support
- ArcMenu
- Blur My Shell
- Burn My Windows
- Caffeine
- CHC-E (Custom Hot Corners - Extended)
- Clipboard Indicator
- Compiz windows effect
- Dash to Dock
- Extension List
- Forge
- GSConnect
- Just Perfection
- Media Controls
- Media Progress
- Open Bar
- User Themes
- Tiling Shell
- Useless Gaps
- Vitals
- Removable Drive Menu

## Programms
- Libre Office
- Gimp
- Bottles (Windows Wine Manager)
- GDM-Settings
- Chrome
- Thunderbird
- Steam
- Spotify
- Discord
- Warehouse
- Proton
- NeoVim

- Alpaca
- Audacity
- Cartridges
  - Lutris
  - Heroric
- Mission Center



Symlink Manager for dotfiles:
- `sudo pacman -Ss stow`
- 