# PowerShell-AD-module
These are the files, from Microsoft, that are required to use AD in PowerShell

If you only need to use them once simply save them in the same folder as your AD PS1 and put this at the top of your AD PS1:

Import-Module .\Microsoft.ActiveDirectory.Management.dll
Import-Module .\ActiveDirectory.psd1

--- More info ---

http://www.labofapenetrationtester.com/2018/10/domain-enumeration-from-PowerShell-CLM.html

Put Microsoft.ActiveDirectory.Management.dll in:
C:\Windows\Microsoft.NET\assembly\GAC_64\Microsoft.ActiveDirectory.Management

Put ActiveDirectory.psd1 in:
C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ActiveDirectory\

Then 'Import-Module' on both if the commands aren't already working.

Full list of files required:
Microsoft.ActiveDirectroy.Management.dll
ActiveDirectory.psd1
ActiveDirectory.Format.ps1xml
ActiveDirectory.Types.ps1xml

Can also be grabbed from:
https://github.com/samratashok/ADModule

--- break ---

Alt, if you have local admin on both systems you can import the AD module from a remote computer:

$adsess = New-PSSession -ComputerName savdaldc01
import-pssession -session $adsess -module ActiveDirectory
Get-ADUser -Filter *
