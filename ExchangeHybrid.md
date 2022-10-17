# Exchange Server 混合式佈署

## 前置作業

- 本篇 Exchange 版本為 2016，所以會在這一台直接啟用混合部署功能，後續此台簡稱為 EX2016，確認有獨立的對外 IP、對應的 FQDN。<br>
- 確認公開憑證主體別名有包含原先使用的相關 FQDN 與 ExHybrid 所使用的 FQDN。<br>
- 確保此台有安裝 Microsoft Edge 瀏覽器<br>

## 安裝 Exchange 混合部署精靈

- 在 EX2016 中登入 ECP，在左邊功能欄位選擇混合，這一頁會提示說您可以點選此連結 https://aka.ms/HybridWizard，下載混合部署精靈。<br>
  ![Github](/images/hybrid1.png)<br>
- 瀏覽器會跳出提示視窗，點選開啟。<br>
  ![Github](/images/hybrid2.png)<br>
- 開啟後，當程式下載完後，會跳出安裝提示，點選安裝，安裝完成後點選開啟。<br>
  ![Github](/images/hybrid3.png)<br>
  ![Github](/images/hybrid4.png)<br>
  ![Github](/images/hybrid5.png)<br>
- 開啟後可以看到已經進入混合式部署精靈歡迎介面，點選下一步<br>
  ![Github](/images/hybrid6.png)<br>
- 在這裡可以看到您現有的 Exchange Server 組織，如果您是另外建一台 Exchange Server 當作 Hybrid Server，會在這給予授權。完成後選擇下一步<br>
  ![Github](/images/hybrid7.png)<br>
- 在這個頁面，主要是會抓取您內部的 Exchange 系統管理員與 Microsoft 365 的全域管理員，如果沒有問題，點選下一步。<br>
  ![Github](/images/hybrid8.png)<br>
- 此步驟會自動設定相關資訊<br>
  ![Github](/images/hybrid9.png)<br>
  ![Github](/images/hybrid10.png)<br>
- 在這個頁面您可以選擇所需要的混合式功能，如果只是要用於搬遷，可以選擇基本混合式組態，如果是要共存的話，建議選擇完整混合式設定。選擇後點選下一步<br>
  ![Github](/images/hybrid11.png)<br>
- 在這個頁面您可以選擇傳統混合式拓樸與新式混合式拓樸，差異是新式混合式拓樸會安裝混合式代理程式，由代理程式來協助處理遷移的作業，但如果需要在 Teams 上看到內部部署 Exchange 的行事曆的話，建議選擇傳統混合式拓樸，確認後點選下一步。<br>
  ![Github](/images/hybrid12.png)<br>
- 在這個頁面您需要再次輸入 Exchange 系統管理員的身分憑證，用於 Exchange Web 服務及移轉功能的認證。輸入完成後，選點下一步。<br>
  ![Github](/images/hybrid14.png)<br>
  ![Github](/images/hybrid15.png)<br>
- 在這個頁面式設定 Exchange Server 和 Exchange Online 的雙向郵件傳輸，如果您有集線 / 集中式傳輸的需求，再進行勾選，否則選擇第一個選項即可，選擇完選擇下一步。<br>
  ![Github](/images/hybrid16.png)<br>
- 在這個頁面是選擇您的 Exchange Onlin 的接收連接器組態，您需要選擇要做為接收 Exchange Online 信件的伺服器，如果是額外建立的 Exchange Server for Hybrid，請選擇此台。如果 Exchange Online 無法寄信到 Exchange Server，您首先就是要來檢查這個連接器。本範例是直接使用 Ex2016 啟用混合部署功能，所以在這裡選擇 EX2016。完成後選擇下一步。<br>
  ![Github](/images/hybrid17.png)<br>
- 在這個頁面是選擇您的 Exchange Server 組織對 Exchange Online 的傳送連接器，如果 Exchange Server 無法寄信到 Exchange Online，您首先就是要來檢查這個連接器。本範例是直接使用 Ex2016 啟用混合部署功能，所以在這裡選擇 EX2016。完成後選擇下一步。<br>
  ![Github](/images/hybrid18.png)<br>
- 在這個頁面是選擇您的 Exchange 組織所使用的公開憑證，Exchange Server 對 Exchange Online 的傳輸路由會使用 TLS 1.2 進行傳輸，如果您有建立額外的 Exchange Server for Hybrid，請記住此憑證需要包含 Exchange Server for Hybrid 對應的 FQDN。<br>
  ![Github](/images/hybrid19.png)<br>
- 在這個頁面是設定 Exchange Online 路由到 Exchange Server 所辨認的 FQDN，本範例是直接使用 mail.brianhsing.store，如果您有建立額外的 Exchange Server for Hybrid，需要設定對應的 FQDN，如 exhybrid.brianhsing.store。完成後點選下一步<br>
  ![Github](/images/hybrid20.png)<br>
- 完成上述步驟後，在這個頁面點選更新按鈕，此過程會持續數十分鐘，請不要關閉此視窗。<br>
  ![Github](/images/hybrid21.png)<br>
  ![Github](/images/hybrid22.png)<br>
- 您可以開啟 Exchange management shell 來輸入 `Get-HybridConfiguration` 來驗證是否啟用。<br>
  ![Github](/images/hybrid26.png)<br>
- 也需要特別檢查 Exchange 系統管理中心的組織，在共用的頁籤中，同盟信任是否有啟用，如果沒啟用請點選啟用。<br>
  ![Github](/images/hybrid23.png)<br>

 完成後，請繼續完成[信箱移轉測試](/MailBoxMigrate.md)。<br>