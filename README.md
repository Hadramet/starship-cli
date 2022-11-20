# Starship command line config

__Prerequisites__ :

- Install font provided by [Nerd Font](https://www.nerdfonts.com/)  and enabled in your terminal.;
- Install [Starship](https://starship.rs/#quick-install).

__starship.toml__ : 

- use the configuration file . Inspired [Christian Lempa](https://github.com/ChristianLempa/dotfiles-win/blob/main/.starship/starship.toml).
- On windows terminal settings , change the font to an nerd font.
- change color theme, u can use [Christian Lempa](https://github.com/ChristianLempa/dotfiles-win/blob/main/windows-terminal-settings.json) colors. Just the `Schemes` part.

I am using vs code to edit the below files.

__Powershell__ :

- Open `code $PROFILE` and set this :

```ps1
$ENV:STARSHIP_CONFIG = "__PATH__\starship.toml"
$ENV:STARSHIP_DISTRO = "  __NAME__ "
Invoke-Expression (&starship init powershell)
```

__cmd__ : you will need to use [Clink](https://github.com/chrisant996/clink/releases) download and install latest release.

- open `%LocalAppData%\clink\starship.lua` and add 

```lua
os.setenv('STARSHIP_CONFIG', '__PATH__\\starship.toml')
os.setenv('STARSHIP_DISTRO', '  __NAME__ ')
load(io.popen('starship init cmd'):read("*a"))()
```

__bash (LINUX)__ : 

- open `code ~/.bashrc` and add at the bottom

```sh
export STARSHIP_CONFIG="__PATH__/starship.toml"
export STARSHIP_DISTRO="  __NAME__ "
eval "$(starship init bash)"

```
