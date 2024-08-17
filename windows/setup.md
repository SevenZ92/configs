# setup gcm on wsl

```bash
# follow inst below
https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/wsl.md
```

# setup oh-my-posh

- wsl

```bash
# install posh
curl -s https://ohmyposh.dev/install.sh | bash -s

#  edit .profile
eval "$(oh-my-posh init bash --config ~/.cache/oh-my-posh/themes/quick-term.omp.json)"

# re-launch terminal
```

- powershell

```bash
# install posh
winget install JanDeDobbeleer.OhMyPosh -s winget

# enable local scripts
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

# open profile with notepad
notepad $PROFILE
# or open profile with visual studio code
# code $PROFILE

# add following inst
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/jandedobbeleer.omp.json" | Invoke-Expression

# re-launch terminal
```