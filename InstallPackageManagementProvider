#Включаем возможность установки Nuget
Set-ItemProperty -Path 'HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NetFramework\v4.0.30319' -Name 'SchUseStrongCrypto' -Value '1' -Type DWord
Set-ItemProperty -Path 'HKLM:\SOFTWARE\Microsoft\.NetFramework\v4.0.30319' -Name 'SchUseStrongCrypto' -Value '1' -Type DWord
#Перезапустить PowerShell  и выполнить
[Net.ServicePointManager]::SecurityProtocol


Get-PSRepository
Register-PSRepository -Default -Verbose

Get-PSRepository
Set-PSRepository -Name "PSGallery" -InstallationPolicy Trusted
Get-PSRepository

Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force
#Установка nuget
Write-Host "$( Get-Date ) Install-PackageProvider -Name NuGet -Force -RequiredVersion 2.8.5.201"
Install-PackageProvider -Name NuGet -Force -RequiredVersion 2.8.5.201;
Write-Host "$( Get-Date ) Install-Module -Name PackageManagementProviderResource -Force -RequiredVersion 1.0.3"
Install-Module -Repository PSGallery PackageManagementProviderResource
Install-Module -Name PackageManagementProviderResource -Force #-RequiredVersion 1.0.3;


Get-Module –list

# I add the switch Trusted because I trust all the modules and scripts from Powershell Gallery
Register-PSRepository -Default -InstallationPolicy Trusted

#For Powershell with version less than v5:
Register-PSRepository -Name PSGallery -SourceLocation https://www.powershellgallery.com/api/v2/ -InstallationPolicy  Trusted
