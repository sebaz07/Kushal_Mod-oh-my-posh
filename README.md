# Oh-my-posh Kushal personal Mod

This repo contains my personal modification of `kushal` theme

## Preview

![image](https://github.com/user-attachments/assets/6a8f7264-30be-403e-872e-3896da3c08c5)

![image](https://github.com/user-attachments/assets/dad2814e-a168-4d9c-aeff-0ace5631a94b)

### Notes
Dont forget to add the Enviroment variable to the `$PROFILE` file.
```ps1
#Sets an environment variable to display the private IP address.
$Env:MY_PRIVATE_IP = (Get-NetIPAddress -AddressFamily IPv4 | Where-Object { $_.InterfaceAlias -eq "Ethernet" }).IPAddress

#Configuration of Oh My Posh for PowerShell, initializing the theme and loading additional modules.
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\kushal.omp.json" | Invoke-Expression
Import-Module Terminal-Icons
Set-PSReadLineOption -predictionViewStyle ListView

# Creates an alias for cat to use bat instead.
Set-Alias -Name cat -Value bat

# Creates an alias for terraform as tf.
Set-Alias -Name tf -Value terraform


#Defines a function to use fzf with a preview powered by bat, allowing you to view files in a nice format.
function fzb {
    fzf --preview "bat --color=always --style=numbers --line-range=:500 {}"
}
```
