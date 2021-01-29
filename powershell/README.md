```bash
$url = "https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1"
$file = "$env:temp\ConfigureRemotingForAnsible.ps1"

(New-Object -TypeName System.Net.WebClient).DownloadFile($url, $file)

powershell.exe -ExecutionPolicy ByPass -File $file

$testUserAccountName = 'ansible'
$testUserAccountPassword = (ConvertTo-SecureString -String '1qaz@WSX' -AsPlainText -Force)
if (-not (Get-LocalUser -Name $testUserAccountName -ErrorAction Ignore)) {
    $newUserParams = @{
        Name                 = $testUserAccountName
        AccountNeverExpires  = $true
        PasswordNeverExpires = $true
        Password             = $testUserAccountPassword
    }
    $null = New-LocalUser @newUserParams
}

## Add the local user to the administrators group. If this step isn't doing, Ansible sees an "AccessDenied" error
Get-LocalUser -Name $testUserAccountName | Add-LocalGroupMember -Group 'Administrators'
```