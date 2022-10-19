# 郵件路由測試

完成信箱移轉之後，我們需要進行幾項測試，確認郵件路由的可用性，我們可以在系統管理中心的郵件流程功能中的郵件追蹤頁籤中來觀察。<br>
- 地端信箱到雲端信箱的郵件路由測試，mark@brianhsing.store 寄送至 brian@brianhsing.store。<br>
  - 在使用者面向可以觀察以下信件截圖。<br>
    ![Github](/Images/mailflow1.png)<br>
  - 在 Exchange Online 系統管理中心中，選擇郵件流程下拉式選單，點選郵件追蹤。<br>
    ![Github](/Images/mailflow2.png)<br>
  - 點選啟動追蹤後，輸入寄件者或收件者電子郵件信箱，完成後點選搜尋。<br>
    ![Github](/Images/mailflow3.png)<br>
  - 在郵件追蹤搜尋結果的頁面中，可以觀察到此封信件的紀錄如下。<br>
    ![Github](/Images/mailflow4.png)<br>
- 雲端信箱到地端信箱的郵件路由測試，brian@brianhsing.store 寄送至 mark@brianhsing.store。<br>
  - 在使用者面向可以觀察以下信件截圖。<br>
    ![Github](/Images/mailflow5.png)<br>
  - 在 Exchange Online 系統管理中心中，選擇郵件流程下拉式選單，點選郵件追蹤。<br>
    ![Github](/Images/mailflow2.png)<br>
  - 點選啟動追蹤後，輸入寄件者或收件者電子郵件信箱，完成後點選搜尋。<br>
    ![Github](/Images/mailflow7.png)<br>
  - 在郵件追蹤搜尋結果的頁面中，可以觀察到此封信件的紀錄如下。<br>
    ![Github](/Images/mailflow6.png)<br>
- 外部信箱寄信到雲端信箱能夠透過 Exchange Hybrid 功能轉送至雲端信箱，brian.hsing.tw@gmail.com 寄送至 brian@brianhsing.store。<br>
  - 在使用者面向可以觀察以下信件截圖。<br>
    ![Github](/Images/mailflow9.png)<br>
  - 在 Exchange Online 系統管理中心中，選擇郵件流程下拉式選單，點選郵件追蹤。<br>
    ![Github](/Images/mailflow2.png)<br>
  - 點選啟動追蹤後，輸入寄件者或收件者電子郵件信箱，完成後點選搜尋。<br>
    ![Github](/Images/mailflow3.png)<br>
  - 在郵件追蹤搜尋結果的頁面中，可以觀察到此封信件的紀錄如下。<br>
    ![Github](/Images/mailflow10.png)<br>
  - 在 Microsoft 365 安全性的總管功能中，可以信件資料中看到更詳細的資料，在這裡我就可以看到寄件者的 IP 位址與路由方向。<br>
    ![Github](/Images/mailflow11.png)<br>

已完成實戰演練，回[Exchange Hybrid Deployments](/README.md)。<br>