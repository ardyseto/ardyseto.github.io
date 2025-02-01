---
layout: post
title: Beautify Mac Terminal
date: 2025-01-29 01:59:00
description: A guide to enhancing your Mac terminal experience by setting up iTerm2 as a powerful terminal emulator, configuring Zsh shell with modern features, and customizing your prompt with Starship for improved productivity and visual appeal.
tags: mac terminal
categories: programming
mermaid: true
---

# Beautify Your Mac Terminal with iTerm2, Zsh, and Starship

Do you spend a lot of time in the terminal and want to make it more visually appealing and productive? In this guide, I’ll walk you through how to transform your Mac terminal into a beautiful and efficient workspace using **iTerm2**, **Zsh**, and **Starship**. Whether you’re a developer, sysadmin, or just love tinkering with your setup, this step-by-step tutorial is for you.

---

## Table of Contents
- [Beautify Your Mac Terminal with iTerm2, Zsh, and Starship](#beautify-your-mac-terminal-with-iterm2-zsh-and-starship)
  - [Table of Contents](#table-of-contents)
  - [1. Introduction to iTerm2](#1-introduction-to-iterm2)
  - [2. Downloading and Installing iTerm2](#2-downloading-and-installing-iterm2)
  - [3. Setting Up Nerd Fonts](#3-setting-up-nerd-fonts)
  - [4. Basic iTerm2 Configuration](#4-basic-iterm2-configuration)
  - [5. Configuring Zsh](#5-configuring-zsh)
    - [Optional Zsh Installation Steps](#optional-zsh-installation-steps)
  - [6. Installing Oh My Zsh](#6-installing-oh-my-zsh)
  - [7. Adding Plugins for Zsh](#7-adding-plugins-for-zsh)
  - [8. Adding Starship Prompt](#8-adding-starship-prompt)
  - [9. Using a Starship Template](#9-using-a-starship-template)
  - [10. Bonus: Configuring VS Code](#10-bonus-configuring-vs-code)
  - [11. Wrap-Up](#11-wrap-up)

---

## 1. Introduction to iTerm2
iTerm2 is a powerful terminal emulator for macOS that offers extensive features and customization options. It’s a great alternative to the default macOS Terminal app and provides a smoother experience for developers and power users.

---

## 2. Downloading and Installing iTerm2
1. **Download iTerm2**: Head over to the [iTerm2 website](https://iterm2.com/) and download the latest version.
2. **Install iTerm2**: Once downloaded, open the `.dmg` file and drag iTerm2 to your Applications folder.

---

## 3. Setting Up Nerd Fonts
Nerd Fonts provide icons and glyphs for your terminal applications, making them visually appealing and functional.

1. **Download Nerd Fonts**:
   - Visit the [Nerd Fonts website](https://www.nerdfonts.com/).
   - Choose or search for a font like **FiraMono Nerd Font**.
   - Download the font file (usually a `.zip` archive).
2. **Install Nerd Fonts**:
   - Unzip the downloaded file.
   - Select all the `.ttf` font files and double-click to open the Font window.
   - Click **Install** to add the fonts to your system.

---

## 4. Basic iTerm2 Configuration
1. **Open Preferences**:
   - Open iTerm2 and go to **Preferences** (`Cmd + ,`).
2. **Customize Appearance**:
   - Navigate to the **Profiles** tab.
   - Under the **Colors** section, choose a theme you like. For a modern look, try the **Smoooooth** color scheme.
3. **Set Font**:
   - Go to the **Text** tab.
   - Choose a font like **FiraMono Nerd Font Propo** for better compatibility with icons and symbols.
   - Adjust the font size if needed.
4. **Enable Natural Editing**:
   - Go to the **Keys** tab.
   - Select **Natural Text Editing** and click **Remove** to confirm and load the preset. This allows you to navigate between words using `Cmd` keys.

---

## 5. Configuring Zsh
Zsh (Z Shell) is a powerful shell that offers many improvements over the default Bash shell, including themes and plugins. Modern macOS versions already use Zsh as the default shell.

### Optional Zsh Installation Steps
If you’re using an older macOS version or prefer to install Zsh manually:
1. Install Homebrew (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Install Zsh:
   ```bash
   brew install zsh
   ```
3. Set Zsh as your default shell:
   ```bash
   chsh -s $(which zsh)
   ```

---

## 6. Installing Oh My Zsh
Oh My Zsh is a framework for managing your Zsh configuration.

1. Run the following command to install Oh My Zsh:
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

---

## 7. Adding Plugins for Zsh
Enhance your terminal experience by adding useful plugins like **zsh-syntax-highlighting** and **zsh-autosuggestions**.

1. **Install Plugins**:
   ```bash
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```
2. **Configure Plugins**:
   - Open the `.zshrc` file in a text editor:
     ```bash
     nano ~/.zshrc
     ```
   - Find the `plugins` array and add the plugins:
     ```bash
     plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
     ```
   - Save the file and restart your terminal or run:
     ```bash
     source ~/.zshrc
     ```

---

## 8. Adding Starship Prompt
Starship is a cross-shell prompt that is fast, customizable, and minimalistic.

1. **Install Starship**:
   ```bash
   brew install starship
   ```
2. **Configure Starship**:
   - Open the `.zshrc` file in a text editor:
     ```bash
     nano ~/.zshrc
     ```
   - Add the following line at the end of the file:
     ```bash
     eval "$(starship init zsh)"
     ```
   - Save the file and restart your terminal or run:
     ```bash
     source ~/.zshrc
     ```

---

## 9. Using a Starship Template
To simplify customization, use a pre-configured Starship template.

1. Create the Starship configuration directory and apply a preset:
   ```bash
   mkdir -p ~/.config && starship preset gruvbox-rainbow -o ~/.config/starship.toml
   ```
2. Customize the prompt further by editing the `~/.config/starship.toml` file. You can find more presets [here](https://starship.rs/presets/).

---

## 10. Bonus: Configuring VS Code
If you use VS Code with its integrated terminal, ensure the font settings are updated.

1. Open VS Code and go to **Settings** (`Cmd + ,`).
2. Search for **Font Family** and set **FiraMono Nerd Font Propo** for both:
   - **Editor: Font Family**
   - **Terminal › Integrated: Font Family**

---

## 11. Wrap-Up
That’s it! You’ve successfully transformed your Mac terminal into a beautiful and productive environment using **iTerm2**, **Zsh**, and **Starship**. 

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/iterm-beauty.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

Let me know in the comments if you have any questions or suggestions for future tutorials. Happy coding!