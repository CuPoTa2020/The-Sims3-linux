# The-Sims3-wine
Quick guide how to launch The Sims 3 via wine

I use Lutris for this but you can do it with wine directly


### Preparing (Lutris)

1. Add new local game via "+" button and choose wine as a runner
2. Set *executable* for installer of The Sims 3
3. Choose an empty folder for Wine Prefix
4. Set *architecture* to 64-bit
5. Click on *Runner Options* and choose **old version of wine for installation**. You may pick other version after installation will finished (I used 6.14)
6. Save settings and close the window

### wineprefix setup

If you don't have winetricks installed you need to install it:

`$ sudo apt-get install winetricks` -- for Ubuntu/Mint

`$ sudo dnf install winetricks` -- for Fedora

`$ sudo pacman -S winetricks` -- for Archlinux/Manjaro

Click on The Sims 3 icon in Lutris' library and click on wine icon at the bottom and choose *Open Bash terminal* and put this in terminal:

```
$ winetricks dotnet20sp2 d3dx9 mfc42 vcrun2005 vcrun2010
```

### Install the game

Now you can launch installer and wait until setup is finished. If installation is freezed try choosing different old versions of wine

### Launch the game

Now you may pick new wine version. Note that using DXVK requiring two libraries in your system. Of you can disable DXVK in runner options

For nvidia:

`$ sudo apt install vulkan-utils` -- For Ubuntu/Mint

`$ sudo dnf install vulkan-loader` -- For Fedora

`$ sudo pacman -S --needed nvidia-utils lib32-nvidia-utils` -- For Archlinux/Manjaro

For radeon:

`$ sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils` -- For Ubuntu/Mint

`$ sudo dnf install vulkan-loader vulkan-tools` -- For Fedora

`$ sudo pacman -S -needed vulkan-radeon lib32-vulcan-radeon` -- For Archlinux/Manjaro


If you don't have sound in game, make sure you install `libpulse` and `lib32-libpulse` libraries


### Changing the language

If you want to change language open *Wine registry* by clicking wine icon at the bottom of Lutris and go to:

```HKEY_LOCAL_MACHINE/Software/Wow6432Node/Sims```

You need to change *Locale* file in each expansion folder (for example, English is en-US, Russian is ru-RU, German is de-DE, Spanish is es-ES)
