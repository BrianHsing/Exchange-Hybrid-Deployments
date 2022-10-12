# 目錄同步處理
## 設定 Azure AD Connect
 - Azure AD Connect v2 的版本強制使用 TLS 1.2，所以您必須要確保您有啟用 TLS 1.2，您可以使用下列 PowerShell 指令碼，在 Azure AD Connect 伺服器上啟用 TLS 1.2<br>
 ````
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319"SchUseStrongCrypto"=dword:00000001
 ````
 - 開啟瀏覽器，輸入 https://go.microsoft.com/fwlink/?LinkId=615771 ，並下載。<br>
  ![Github](/Images/aad1.png)<br>
 - 開啟 AzureADConnect.exe 安裝<br>
 - 勾選「I agree to the License terms and privacy notes.」，點選「Continue」<br>
   ![Github](/Images/aad0.png)<br>
 - 選擇「自訂」<br>
  ![Github](/Images/aad11.png)<br>
 - 選擇「安裝」<br>
  ![Github](/Images/aad12.png)<br>
 - 選擇「密碼湊同步處理」，按下「下一步」<br>
  ![Github](/Images/aad13.png)<br>
 - 輸入您具有的 Azure AD Global administrator 的管理者帳號，按下「下一步」<br>
  ![Github](/Images/aad2.png)<br>
 - 點選「新增目錄」，選擇「建立新的 AD 帳戶」，輸入您具有 Enterprise admin 權限的帳號，按下「確定」<br>
  ![Github](/Images/aad3.png)<br>
 - 成功後，可以看到您的樹系標示成功，按下「下一步」<br>
  ![Github](/Images/aad4.png)<br>
 - 因為此範例已經實作 Azure AD 自訂網域設定，在 Windows ADDS 樹系名稱一致的狀況下，按下「下一步」<br>
  ![Github](/Images/aad5.png)<br>
  > **Tips.如果您沒有實作自訂網域，請勾選 Continue without matching all UPN suffixes to verified domains 後繼續** <br>
 - 選擇「同步所選取的網域及 OU」，只勾選「M365」，按下「下一步」<br>
  ![Github](/Images/aad6.png)<br>
 - 按下「下一步」<br>
  ![Github](/Images/aad10.png)<br>
 - 按下「下一步」，如果您想針對名稱、群組等篩選，您可以在此設定<br>
  ![Github](/Images/aad7.png)<br>
 - 勾選「Exchange 混合部署」，並且按下「下一步」<br>
  ![Github](/Images/aad8.png)<br>
 - 選擇「安裝」<br>
  ![Github](/Images/aad12.png)<br>
 - 完成<br>
  ![Github](/Images/aad14.png)<br>
 
 完成後，請繼續完成[Exchange Server 混合式佈署](/ExchangeHybrid.md)<br>。<br>