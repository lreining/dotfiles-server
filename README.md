# Server Dotfiles — Lars Reining

Minimal dotfiles for work servers.

## What's included

| File | Purpose |
|---|---|
| `.bashrc` | Aliases, history settings, PATH, tool initialization |
| `.config/starship.toml` | Starship prompt, always shows the hostname |
| `.config/yadm/bootstrap` | Installs starship, zoxide and fzf into `~` |

## Bootstrap

Install yadm (a single script, no package manager needed):

```bash
mkdir -p ~/.local/bin
curl -fLo ~/.local/bin/yadm https://github.com/yadm-dev/yadm/raw/master/yadm
chmod a+x ~/.local/bin/yadm
export PATH="$HOME/.local/bin:$PATH"
```

Back up the existing `.bashrc`, then clone and apply:

```bash
cp ~/.bashrc ~/.bashrc.orig
yadm clone https://github.com/lreining/dotfiles-server.git
yadm checkout -f
yadm bootstrap
exec bash
```
