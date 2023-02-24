# Gaming on Linux
This guide shows you how to install Manjaro Linux on your computer and which software you need for gaming.

**Before you install Linux on your PC, backup your most important data.**

## Download Manjaro
- Manjaro is a great Linux distribution with up-to-date software. It's easy to install and comes with Steam, nVidia/AMD graphics driver and other things that make your life easier. It also has access to the Arch User Repository (AUR) which contains A LOT of software that is not the standard software repo. I have been using Linux for 20 years now and Manjaro is the most straightforward Linux distribution that just works. But there are other great distros out there, this is just what works best for me. Give it a try and once you have Manjaro up and running maybe you want to check other distros out as well. 
- I recommend the Manjaro XFCE version, as it just works and does not require much system ressources. KDE Plasma for example has had stability issues in the past, but it may just work for you and it does not make much of a difference for this guide which desktop environment you use.

https://manjaro.org/download/

## Put Manjaro image on USB Stick
This step will enable you to boot into a Manjaro live session from a USB stick
- get Ventoy (Ventoy installs its own system on a USB stick and going forward you can simply copy any image files onto the stick and the stick will boot them for you)
https://www.ventoy.net/en/download.html
- install Ventoy and follow instructions to prepare a USB stick
- copy the Manjaro image on your USB stick
- dismount the USB stick


## enter UEFI Boot
- boot PC and press F2 to enter UEFI
- disable fast boot 
- disable secure boot (this usually requires setting a password)
- now is a good time to insert your USB stick into your computer
- save and exit
- PC reboots

## Boot from USB stick
- if you have not done so, insert USB stick and reboot PC
- press F12 right after reboot to select USB stick with Manjaro on it
- you will see a boot menu
- select "Boot with proprietary drivers"
- wait until you see the desktop
- if you are using WIFI, enable it in the lower right (icon next to the clock)
- klick on "Install Manjaro Linux"
- follow instructions (just click "next" a few times - **this will delete your hard drive and all your data! Make a backup if you want to keep your cat pictures!**)
- once installation finishes, restart PC


## Setting up Manjaro

### Update the system
- klick on the package manager icon next to your taskbar clock > Updates > wait for it to sync and then confirm to install updates

### Enable AUR (needed to install some of the programs below)
- go to software center: click on start button to see menu and type "software" > then click on "Add/Remove Software" > click on three dots in upper right > Preferences > Third Party 
- "Enable AUR support" 

### Install these packages (copy a line into the terminal and press Enter)

sudo pacman -S --noconfirm bash-completion neofetch

sudo pacman -S --noconfirm discord # if you use Discord

sudo pacman -S --noconfirm gamemode # Optimize system for gaming

sudo pacman -S --noconfirm lutris # emulator

sudo pacman -S --noconfirm lib32-glibc lib32-gamemode lib32-gst-plugins-base-libs lib32-libxslt lib32-mangohud lib32-ocl-icd lib32-vkd3d lib32-vulkan-icd-loader linux-steam-integration python-evdev python-pyqt6 vkd3d vulkan-icd-loader winetricks # various programs that are needed for gaming (mostly in older games but still good to have)

sudo pacman -S --noconfirm mangohud # shows overlay with fps and other information

sudo pacman -S --noconfirm mono # .NET platform data for Windows games

sudo pacman -S --noconfirm ventoy # alternative for Belena Etcher

sudo pacman -S wine-staging # most up-to-date Wine

sudo pacman -S --noconfirm wine-gecko # replaces Microsoft Internet Explorer in WINE

sudo pamac build --no-confirm arma3-unix-launcher-bin # if you play Arma 3

sudo pamac build --no-confirm cpupower-gui # manage CPU governors 

sudo pamac build --no-confirm goverlay # manage Vulkan/OpenGL overlays

sudo pamac build --no-confirm gwe # nVidia control tool

sudo pamac build --no-confirm libstrangle #fps limiter for Lutris

sudo pamac build --no-confirm opentrack # headtracker

sudo pamac build --no-confirm proton-ge-custom-bin # modified Proton version

sudo pamac build --no-confirm protontricks # required to install dependencies for Steam games

sudo pamac build --no-confirm pulseeffects-legacy # audio effects like compressor

sudo pamac build --no-confirm ttf-ms-fonts # Microsoft fonts

sudo pamac build --no-confirm vkbasalt lib32-vkbasalt # Vulkan post-processing layer


### For SteamVR
sudo pacman -S --noconfirm lib32-pipewire 

sudo pamac build --no-confirm lib32-gtk 

sudo pacman -S --noconfirm lib32-gtk2

sudo pacman -S --noconfirm openvr


### For Corsair mouse/keyboard

sudo pamac build --no-confirm ckb-next

sudo systemctl start ckb-next-daemon

sudo systemctl enable ckb-next-daemon


### Games
sudo pacman -S --noconfirm xonotic # a cool arena shooter - obviously not needed

### Steam
- Steam is already installed, open it in the Start menu
- In settings
  - Steam Play: enable both "Enable Steam Play for supported titles" and "Enable Steam Play for all other titles", run other titles with (select Steam Experimental or 7 or any other recent version)
  - Opt into Steam beta
  - Music > disable scanning
  - Shader Precaching DISABLE, and DISABLE allow background processsing
  - Account > Beta participation > opt into Steam beta
- SteamVR (if installed), also opt into beta

### Time/Date
- Start Menu > Settings > Manjaro Settings Manager > Time and Date: enable set time and date automatically

### Enable Firewall
- (click on start button to see menu and type "firewall" > click on "Firewall configuration" > enable firewall (click on slider next to Status)

### Install Language Packages
- Start Menu > Manjaro Settings > Languages > Install Packages

### Optional: Change Desktop Theme, DPI
- Start Menu > Appearance 
  > style: matcha-dark-azul
  > fonts: DPI: 135

### Disable mouse acceleration
- Start Menu > Mouse & Touchpad > Devices > Pointer Speed (set to 0)

### XFCE Smart Window Placement
- Start Menu > Window Manager Tweaks > Placement > Minimum Size of windows: set to smallest value (far left)

## What is next?
- That is all you need to get started. 
- Check out https://www.protondb.com/ to see if a game runs on Linux (many do and for some you can find workarounds on protondb)
- Use Steam to install games. 
- Use Lutris to install non-Steam games.
- If you don't know how to do something or you encounter an error, search for a solution.

Have fun!

