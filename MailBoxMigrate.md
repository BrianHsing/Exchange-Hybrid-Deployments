# 信箱移轉測試

## 前置作業

- 確認已指派 Exchange Online 授權給予需要移轉的使用者。<br>
- 確認批次移轉的信箱數量。<br>
- 確認批次移轉的時間。<br>

## 信箱移轉

- 登入 M365 系統管理，並且進入 Exchange Online 系統管理中心(傳統)，在收件者功能頁面中，選擇移轉頁籤。<br>
  ![Github](/Images/migrate1.png)<br>
- 點選 ... ，並且點選移轉端點。<br>
  ![Github](/Images/migrate2.png)<br>
- 確認移轉端點裡面已經有 Hybrid Migration Endpoint -EWS (Default Web Site)，在這邊點選編輯可以變更批次移轉的上限數量與增量同步的處理上限。增量同步主要功用是當移轉作業還未執行，僅作同步時，每 24 個小時會針對此批次同步一次。<br>
  ![Github](/Images/migrate3.png)<br>
- 點選新增，並且選擇移轉至 Exchange Online，點選下一步。<br>
  ![Github](/Images/migrate4.png)<br>
- 在跳出的視窗中，選擇遠端移動移轉，點選下一步。<br>
  ![Github](/Images/migrate5.png)<br>
- 選擇 Exchange Server 內的 MailBox，在這個範例中，選擇其中一個 brian@brianhsing.store，點選下一步。<br>
  ![Github](/Images/migrate6.png)<br>
- 在這個頁面中會跳出所辨認出的 Exchange Server for Hybrid 對外的 FQDN，確認無誤後，點選下一步。<br>
  ![Github](/Images/migrate7.png)<br>
- 在這個頁面您需要自訂移轉批次的名稱，你也可以看到目標傳輸網域的資訊，選擇移動主要信箱與封存信箱，點選下一步。<br>
  ![Github](/Images/migrate8.png)<br>
- 在新增批次移轉頁面中，您有三個部分要設置，第一個是設定這個移轉批次狀態報告的收件者，第二個步驟是信箱同步，你可以選擇自動啟動、手動啟動，或是排程啟動，第三個是信箱同步後，執行移轉的作業，可以選擇自動、手動或排程完成批次作業，建議使用手動，因為遇到錯誤的時候才能排除問題，點選下一步。<br>
  ![Github](/Images/migrate9.png)<br>
- 完成後可以檢視一下正在同步處理的狀態，可以看到批次狀態、信箱同步狀態。<br>
  ![Github](/Images/migrate11.png)<br>
- 已完成同步處理的狀況如下圖。<br>
  ![Github](/Images/migrate12.png)<br>
- 你也可以點選信箱狀態下方的連結，檢視詳細資料。<br>
  ![Github](/Images/migrate13.png)<br>
- 手動完成此次批次作業，點選右方的完成這個移轉批次，在跳出的警告視窗中，選點是，會立刻開始進行批次移轉作業。<br>
  ![Github](/Images/migrate14.png)<br>
- 完成後的畫面如下所示。<br>
  ![Github](/Images/migrate16.png)<br>
- 完成批次移轉後，可以在兩個地方察看信箱狀況，首先到 Exchange 系統管理中心查看使用者信箱，可以看到 brian 信箱類型變成了 Office 365。<br>
  ![Github](/Images/migrate15.png)<br>
- 在 Exchange Online 系統管理中心收件者，信箱頁籤中，可以看到 brian 已經出現在此信箱列表中。<br>
  ![Github](/Images/migrate17.png)<br>

   完成後，請繼續完成[郵件路由測試](/MailFlow.md)。<br>