# Install Steam

1) Install steam via `sudo pacman -Sy && sudo pacman -S steam` (not flatpak, for drive support)

2) Install proton and vulcan: `sudo pacman -S steam gamemode vulkan-icd-loader vulkan-tools`

- for nvidia: `sudo pacman -S nvidia nvidia-utils lib32-nvidia-utils`
- for amd: `sudo pacman -S mesa lib32-mesa vulkan-radeon lib32-vulkan-radeon`

3) Activate proton in steam settings > compability > check and select proton version (proton Hotfix)

4) Install proton-ge: `yay -S protonup-qt` and start with `protonup-qt`

5) Deactivate shader caching in steam > settings > downloads