# setup gcm on wsl

```bash
# official guides
https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/wsl.md

# download gcm on windows
https://github.com/git-ecosystem/git-credential-manager/releases

# setup on wsl
git config --global credential.helper "/mnt/c/Program\ Files\ \(x86\)/Git\ Credential\ Manager/git-credential-manager.exe"
git config --global credential.https://dev.azure.com.useHttpPath true  # for Azure Devops support only

# setup env path on windows
SETX WSLENV %WSLENV%:GIT_EXEC_PATH/wp

# reload wsl
```

# setup oh-my-posh

```bash
# official guides
https://ohmyposh.dev/docs/
```

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

# install auto-completion
Install-Module -Name PSReadLine -Force

# install terminal icons
Install-Module -Name Terminal-Icons -Repository PSGallery -Force

# open profile with notepad
notepad $PROFILE
# or open profile with visual studio code
# code $PROFILE

# add following inst
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/jandedobbeleer.omp.json" | Invoke-Expression

Import-Module PSReadLine
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows

Import-Module Terminal-Icons
# re-launch terminal
```