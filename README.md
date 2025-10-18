# EMac 🍎

> **Infrastructure as Code for macOS Development Environment**

EMac is a comprehensive guide to my daily-used software, configurations, and preferences on macOS, inspired by the concept of [Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_Code). This repository serves as a blueprint for setting up a productive development environment on macOS.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [System Setup](#system-setup)
- [Development Tools](#development-tools)
- [Command Line Tools](#command-line-tools)
- [Applications](#applications)
- [Configuration Files](#configuration-files)
- [Contributing](#contributing)
- [License](#license)

## 🚀 Prerequisites

### Homebrew
The essential package manager for macOS:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Visit [brew.sh](https://brew.sh/) for more information.

## 🔧 System Setup

### 1. Update macOS and Development Tools

```bash
# 1. Update macOS to the latest version via System Preferences
# 2. Update Homebrew packages
brew update && brew upgrade

# 3. Install Xcode Command Line Tools
xcode-select --install

# 4. Accept Xcode license
sudo xcodebuild -license accept
```

## 🛠 Development Tools

### Terminal & Shell

#### iTerm2
A powerful terminal emulator for macOS:
- **Download**: [iTerm2](https://www.iterm2.com/)
- **Features**: Split panes, hotkeys, profiles, and extensive customization

#### Oh My Zsh
Framework for managing Zsh configuration:
- **Installation**: [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
- **Configuration**: `~/.zshrc`

```bash
# Essential zsh configuration
export EDITOR='vim'
plugins=(git autojump encode64 zsh-autosuggestions zsh-bat)

# Git configurations
git config --global pull.rebase true
git config --global fetch.prune true
git config --global diff.colorMoved zebra
```

### Git Setup

#### Installation
```bash
brew install git
```

#### Configuration
```bash
# Basic user configuration
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Recommended settings
git config --global pull.rebase true
git config --global core.autocrlf input
git config --global init.defaultBranch main
```

#### Global Git Ignore
Maintain a global `.gitignore` file to avoid cluttering project-specific ignore files with OS/IDE-related patterns:

```bash
# Set global gitignore file
git config --global core.excludesfile ~/.gitignore_global
```

Create and edit `~/.gitignore_global` with common patterns:
```gitignore
# macOS
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# IDEs
.vscode/
.idea/
*.swp
*.swo
*~

# Logs
*.log
logs/
```

### Development Environment

#### bat - Better cat
Syntax highlighting for code files:
```bash
brew install bat

# Install zsh-bat plugin
git clone https://github.com/fdellwing/zsh-bat.git $ZSH_CUSTOM/plugins/zsh-bat
```

#### tig - Text-mode interface for Git
```bash
brew install tig
```

## 🔨 Command Line Tools

### Navigation & Productivity

#### [autojump](https://github.com/wting/autojump)
Faster filesystem navigation:
```bash
brew install autojump
```

#### [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
Fish shell-like syntax highlighting for Zsh:
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

#### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
Automatic command suggestions based on history:
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Containerization

#### [Docker](https://www.docker.com/)
Container platform for development and deployment:
```bash
brew install --cask docker
```

## 📱 Applications

### Development

#### Xcode
Apple's integrated development environment:
- **Download**: [App Store](https://developer.apple.com/xcode/)
- **Usage**: iOS/macOS development, debugging, and testing

#### Visual Studio Code
Lightweight yet powerful code editor:
- **Download**: [VS Code](https://code.visualstudio.com/)
- **Features**: Extensions, cloud sync, integrated terminal
- **Personal Settings**: [Configuration Gist](https://gist.github.com/Dogzhou/70091ca501d339f4cb2c9ea1bcdb585b)

### Browsers

#### Chrome & Firefox
Essential web browsers with automatic extension synchronization:
- **Chrome**: [Download](https://www.google.com/chrome/)
- **Firefox**: [Download](https://www.mozilla.org/en-US/firefox/new/)

### Communication & Productivity

#### [Slack](https://slack.com/)
Team communication platform

#### [Notion](https://www.notion.com/desktop)
All-in-one workspace for notes, docs, and collaboration

#### [Dropbox](https://www.dropbox.com)
Cloud storage and file synchronization

### Utilities

#### [Spectacle](https://www.spectacleapp.com/)
Window management with keyboard shortcuts:
- Move and resize windows efficiently
- Customizable hotkeys for window positioning

#### [Balsamiq Mockups 3](https://balsamiq.com/download/)
Rapid wireframing and prototyping tool:
- Quick mockup creation for web and mobile
- Comprehensive widget library
- Intuitive drag-and-drop interface

#### [IINA](https://lhc70000.github.io/iina/)
Modern video player for macOS:
- Native macOS design
- Advanced playback features
- Extensive format support

## 📁 Configuration Files

This repository includes configuration files for:
- Shell configuration (`~/.zshrc`)
- Git global settings
- VS Code settings and extensions
- Terminal profiles and themes

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
