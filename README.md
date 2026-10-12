# Zynotes

A place for your thoughts. Write freely, connect ideas, and keep them close.

Zynotes is a local-first notebook for notes, daily writing, fragments, folders, and connected ideas. Your writing stays on your device. No Zynotes account is required.

**[Visit the website](https://zynotes.zynoks.com)** · **[Open the web notebook](https://zynotes.zynoks.com/app.html)** · **[Getting started](https://zynotes.zynoks.com/guide.html)**

![Zynotes notebook](https://zynotes.zynoks.com/product-notebook-dark-v1.png)

## Download

| Platform | Download | Version |
| --- | --- | --- |
| Windows | [Windows installer](https://updates.zynotes.zynoks.com/Zynotes-Setup-0.1.1.exe) | 0.1.1 |
| Android | [Android APK](https://updates.zynotes.zynoks.com/Zynotes-1.0.1.apk) | 1.0.1 |
| Linux x86_64 | [AppImage](https://updates.zynotes.zynoks.com/Zynotes-0.1.1.AppImage) | 0.1.1 |
| Debian / Ubuntu x86_64 | [Debian package](https://updates.zynotes.zynoks.com/zynotes_0.1.1_amd64.deb) | 0.1.1 |
| Arch Linux x86_64 | [Pacman package](https://updates.zynotes.zynoks.com/zynotes-0.1.1.pacman) or the recipe below | 0.1.1 |

For the current downloads, see the [official website](https://zynotes.zynoks.com). Native macOS and iOS downloads are not available yet.

### Windows

Download and run the installer. You can choose a desktop shortcut and open Zynotes when installation finishes. Uninstall through Windows Installed apps or **Uninstall Zynotes** in the installation folder.

The Windows installer is currently unsigned; Windows may show a publisher warning.

### Android

Download the APK on your phone, open it, and allow installation from that browser or file manager when Android asks. Zynotes is currently distributed directly rather than through Google Play.

### Linux AppImage

Download the AppImage, then run these commands in the folder containing it:

```sh
chmod +x Zynotes-0.1.1.AppImage
./Zynotes-0.1.1.AppImage
```

### Debian / Ubuntu

In the folder containing the downloaded package:

```sh
sudo apt install ./zynotes_0.1.1_amd64.deb
```

### Arch Linux: install using this repository

Install Git and the standard Arch packaging tools if needed:

```sh
sudo pacman -S --needed git base-devel
```

Then clone this repository and build the package as your normal user:

```sh
git clone https://github.com/Zynokss/zynotes-app.git
cd zynotes-app
makepkg -si
```

The recipe downloads the published binary from Cloudflare R2, verifies its SHA-512 checksum, and repackages it for pacman. It does not compile Zynotes from source. Launch **Zynotes** from your application menu or run `zynotes`.

If you already installed the direct `zynotes` pacman package, the new `zynotes-bin` package conflicts with it; review pacman's replacement prompt. To remove this package:

```sh
sudo pacman -R zynotes-bin
```

To install a newer version after this repository's recipe is updated:

```sh
git pull --ff-only
makepkg -si
```

This repository is not an AUR listing. For the direct pacman download instead, use `sudo pacman -U ./zynotes-0.1.1.pacman`.

## What you can do

- Write and read notes with Markdown and a visual editor.
- Organize writing with folders, tags, and templates.
- Connect ideas with links, backlinks, Map, and Scatter.
- Keep multiple local notebooks on desktop and in the web app.
- Export a complete ZIP backup and preview it before restoring.
- Follow the backup guides and optional animated tutorial inside the app.

## Back up your writing

1. Open the app's backup screen and create a backup ZIP.
2. Keep a copy somewhere safe. On desktop, you can choose a folder managed by Google Drive, OneDrive, or Dropbox and remember it for later backups. On Android, share the ZIP to an installed drive app or save a copy.
3. Check the filename and location shown after saving. Desktop also offers **Show in folder**. Your cloud provider confirms when the upload finishes.
4. To restore, find or download the ZIP, select it in Zynotes, review the preview, and choose to add a restored collection or replace the current notebook.

A backup captures your writing at that moment; later edits need another backup. Cloud backups are optional and do not automatically sync notebooks between devices. Backup ZIP files are not encrypted, so keep them somewhere private. Export a backup before clearing application or browser data.

## Report a problem

[Open an issue](https://github.com/Zynokss/zynotes-app/issues) with your operating system, Zynotes version, what happened, and steps to reproduce it. Remove private writing and personal information from screenshots or attachments.

## About this repository

This public repository contains installation documentation and a binary packaging recipe. The application source is maintained in a separate private repository. The downloads include executable application code; this repository does not publish the original source tree or its Git history.

Third-party software notices are available in the app's About or Settings screen. Publishing this installation repository does not change the licenses of the application or its dependencies.
