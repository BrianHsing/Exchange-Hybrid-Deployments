# 目錄同步處理
## 設定 Azure AD Connect
 - Azure AD Connect v2 的版本強制使用 TLS 1.2，所以您必須要確保您有啟用 TLS 1.2，您可以使用下列 PowerShell 指令碼，在 Azure AD Connect 伺服器上啟用 TLS 1.2<br>
 ````
    New-Item 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319' -name 'SystemDefaultTlsVersions' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319' -name 'SchUseStrongCrypto' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-Item 'HKLM:\SOFTWARE\Microsoft\.NETFramework\v4.0.30319' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SOFTWARE\Microsoft\.NETFramework\v4.0.30319' -name 'SystemDefaultTlsVersions' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SOFTWARE\Microsoft\.NETFramework\v4.0.30319' -name 'SchUseStrongCrypto' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-Item 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server' -name 'Enabled' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server' -name 'DisabledByDefault' -value 0 -PropertyType 'DWord' -Force | Out-Null

    New-Item 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client' -name 'Enabled' -value '1' -PropertyType 'DWord' -Force | Out-Null

    New-ItemProperty -path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client' -name 'DisabledByDefault' -value 0 -PropertyType 'DWord' -Force | Out-Null
    Write-Host 'TLS 1.2 has been enabled.'
 ````
 - 開啟瀏覽器，輸入 https://go.microsoft.com/fwlink/?LinkId=615771 ，並下載。<br>
 - 開啟 AzureADConnect.exe 安裝<br>
 - 勾選「I agree to the License terms and privacy notes.」，點選「Continue」<br>
 - 選擇「Customize」<br>
 - 選擇「Install」<br>
 - 選擇「Password Hash Synchronization」，按下「Next」<br>
 - 輸入您具有的 Azure AD Global administrator 的管理者帳號，按下「Next」<br>
 - 點選「Add Directory」，選擇「Create new AD account」，輸入您具有 Enterprise admin 權限的帳號，按下「OK」<br>
 - 成功後，可以看到您的樹系標示成功，按下「Next」<br>
 - 因為此範例已經實作 Azure AD 自訂網域設定，在 Windows ADDS 樹系名稱一致的狀況下，按下「Next」<br>
  > **Tips.如果您沒有實作自訂網域，請勾選 Continue without matching all UPN suffixes to verified domains 後繼續** <br>
 - 選擇「Sync selected domains and OUs」，只勾選「AVD」，按下「Next」<br>
 - 按下「Next」<br>
 - 按下「Next」，如果您想針對名稱、群組等篩選，您可以在此設定<br>
 - 按下「Next」<br>
 - 選擇「Install」<br>
 - 完成<br>
 
 完成後，請[]()。<br>