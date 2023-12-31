# **停車管理子系統**
## 第一章問題定義
### 1.1 業務調查
隨著社會的發展和人民生活水準的提高，買車成為了人們奮鬥目標之一，當然已經有很多人買了車。可是隨著車輛的增加，車輛的停泊問題也隨之出現。人們的生活方式發生著深刻的變化。城市的交通用即便是這種變化所引起的現象之一。城市由於交通設施的增加造成的交通擁擠甚至混亂給人們的生活帶來了極大的不便，這種不便迫使人們尋求高技術的有效手段去解決這種不便，這就使得各個停車場需要更加先進，更完善的車輛管理系統，為車主帶來方便，使停車場的管理系統化。因此開發了停車場管理系統。
### 1.2需求陳述
1. 車主進入停車場:車主在停車場外，停車場外的顯示器上顯示空餘停車位的數量，若有空餘，車主來到擋車器前，系統自動識別車牌號，記錄車輛進入停車場的時間與車牌號，擋車器放行，車主進入停車場。若因某些原因，系統無法識別，如：車輛還未上牌，車輛使用的是臨時車牌，這種情況下，由管理員負責手動錄入車輛資訊（車牌號，進入時間，特殊情況備註：未上牌或臨時牌），無特殊情況則不需備註。
1. 車主離開停車場：車主再次來到擋車器前，系統自動識別車牌號，記錄車輛離開停車場的時間，併計算停車費用，車主支付完成後，擋車器放行，車主離開停車場。若出現以上的特殊情況，則由管理員手動處理輸入訊息，費用則由系統完成計算。
1. 管理員查看車輛資訊：管理員登陸該系統，可以對車輛資訊（車牌號，進出時間，停車費費用，特殊情況備註）進行管理，可查訊車輛信息，添加車輛信息，刪除車輛信息。
### 1.3業務模型
#### 1.3.1業務模型
![图1-1 业务用例模型 drawio](https://github.com/ycc17/final_report/assets/91513230/dc8152f9-fe7b-4849-a3f2-1c55cc0f68ba)  
圖1-1 業務用例模型
#### 1.3.2車主業務活動圖
![图1-2车主业务活动图 drawio](https://github.com/ycc17/final_report/assets/91513230/7f13b5c6-2e16-426e-8e64-8609262ce9aa)  
圖1-2車主業務活動圖
#### 1.3.3管理員業務活動圖
![图1-3管理员业务活动图 drawio](https://github.com/ycc17/final_report/assets/91513230/cd51d637-a400-421e-93e3-1079b635a18d)  
圖1-3管理員業務活動圖
## 第二章需求分析
### 2.1系統用例建模（根據對1.2的分析進行系統用例建模）
#### 2.1.1參與者概述
1. 車主－停車服務
1. 管理員－管理車輛進出的相關訊息
#### 2.1.2用例概述
1. 車主來到有剩餘車位的停車場，進入停車場停車，支付停車費用後離開停車場
1. 管理員輸入正確的帳號和密碼登陸系統，管理車輛進出的訊息，包括車牌號碼，進出時間，停車費費用。
#### 2.1.3用例關係
正在上傳…重新上傳取消  
![图2-1系统用例图 drawio](https://github.com/ycc17/final_report/assets/91513230/636676b9-6c02-40d8-82dd-9f4351f148d4)  
圖2-1系統用例圖
### 2.2用例規約說明
表2-1 「進入停車場」用例規約a

| 用例名稱：  | 進入停車場 |
| :--- | :--- |
| **用例id：**  | P1  |
| **參與者：**  | 車主  |
| **用例說明：** |	車主進入停車場  |
| **前置條件：**  | 車主驅車到擋車器前  |
| **主事件流：**  | 1. 車主開車到擋車器前，用例開始。<br> 2. 系統自動辨識車牌號碼，記錄車牌號碼與進入停車場的時間。<br> 3. 記錄完成，擋車器放行。<br> 4. 車主驅車進入停車場。  |
| **異常事件流：**  | 無法辨識車牌號  |
| **後置條件：**  | 車輛資訊記錄成功  |

表2-2「進入停車場」用例規約b

| 用例名稱：  | 進入停車場 |
| :--- | :--- |
| **異常事件流：**  | 車主驅車到擋車器前，系統無法辨識車牌號  |
| 1. 車主開車到擋車器前，用例開始。<br> 2. 輸入車輛訊息。<br> 3. 記錄完成，擋車器放行。<br> 4. 車主驅車進入停車場。  |
| **後置條件：**  | 車輛資訊記錄成功  |

表2-3「支付費用」用例規約

| 用例名稱：  | 	支付費用 |
| :--- | :--- |
| **用例id：**  | P2  |
| **參與者：**  | 車主  |
| **用例說明：** |	車主結算費用  |
| **前置條件：**  | 車主驅車到擋車器前  |
| **主事件流：**  | 1. 車主開車到擋車器前，開始用例。<br> 2. 系統會自動辨識車牌號，找到車輛進入停車場的相關資訊（車牌號，進入停車場的時間），並記錄離開停車場的時間。<br> 3. 系統核對車輛訊息，計算停車費用。<br> 4. 車主支付停車費。  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 支付成功  |

表2-4 「離開停車場」用例規約

| 用例名稱：  | 	離開停車場 |
| :--- | :--- |
| **用例id：**  | P3  |
| **參與者：**  | 車主  |
| **用例說明：** |	車主離開停車場  |
| **前置條件：**  | 車主支付成功  |
| **主事件流：**  | 1. 車主支付成功後，用例開始。<br> 2. 擋車器放行，車主開車離開停車場。  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 無  |

表2-5 「登陸」用例規約a

| 用例名稱：  | 	登陸 |
| :--- | :--- |
| **用例id：**  | P4  |
| **參與者：**  | 管理員  |
| **用例說明：** |	管理者登陸系統  |
| **前置條件：**  | 無  |
| **主事件流：**  | 1. 管理員進入到登陸介面，用例開始。<br> 2. 當管理員未經過身份驗證且身份驗證嘗試次數小於或等於三時。<br>  <pre> 1.系統要求管理員提供其管理員帳號和密碼。<br> 2. 管理員輸入其管理員帳號和密碼。</pre> 3. 管理員帳號和密碼正確無誤。<br> 4. 系統對管理員進行身份驗證。  |
| **異常事件流：**  | 管理員身份驗證失敗。  |
| **後置條件：**  | 管理員登陸系統。  |

表2-7 「查看車輛資訊」使用案例規約

| 用例名稱：  | 	查看車輛資訊 |
| :--- | :--- |
| **用例id：**  | P5  |
| **參與者：**  | 管理員  |
| **用例說明：** |	管理員查看車輛資訊  |
| **前置條件：**  | 管理者已登陸系統  |
| **主事件流：**  | 1. 當管理員選擇要瀏覽的車輛類型時，使用案例開始。<br> 2. 系統將顯示車輛資訊目錄。  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 無  |

表2-8 「查詢車輛​​資訊」用例規約

| 用例名稱：  | 	查詢車輛資訊 |
| :--- | :--- |
| **用例id：**  | P6  |
| **參與者：**  | 管理員  |
| **用例說明：** |	管理員查詢車輛資訊  |
| **前置條件：**  | 管理者已登陸系統  |
| **主事件流：**  | 1. 管理員選擇“查找”，使用案例開始。<br> 2. 管理員輸入搜尋的車牌號碼。<br> 3. 系統搜尋符合條件的車輛。<br> 4. 系統顯示車輛相關訊息。<br> 5. 其他 <br><pre>5.1 系統告訴管理員未找到匹配的車輛</pre>  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 無  |

表2-9「錄入車輛資訊」用例規約

| 用例名稱：  | 	新增車輛資訊 |
| :--- | :--- |
| **用例id：**  | P7  |
| **參與者：**  | 管理員  |
| **用例說明：** |	管理員手動輸入車輛訊息  |
| **前置條件：**  | 管理者已登陸系統  |
| **主事件流：**  | 1. 管理員選擇“新增資訊”，使用案例開始。<br> 2. 系統顯示車輛詳細資料填選表單，包括車牌號碼及進入時間（必填）、<br> 3. 同時（未完成新增）<br><pre>3.1 管理員選擇一個欄位並新增其值。<br>  1. 系統要求管理員確認新增。<br>  2. 管理員選擇確定。<br>  3. 系統將新的車輛添加到目錄中。</pre>  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 	新的車輛資訊已添加到目錄中  |

表2-10 「刪除車輛資訊」用例規約

| 用例名稱：  | 	刪除車輛訊息 |
| :--- | :--- |
| **用例id：**  | P8  |
| **參與者：**  | 管理員  |
| **用例說明：** |	管理員手動刪除車輛訊息  |
| **前置條件：**  | 管理者已登陸系統  |
| **主事件流：**  | 1. 當管理員選擇“刪除資訊”時，用例開始。<br> 2. 系統向管理員詢問車輛識別碼。<br> 3. 管理員輸入車輛識別碼。<br> 4. 系統要求管理員確認刪除。<br> 5. 管理員選擇確定。<br> 6. 系統刪除車輛詳細資料。  |
| **異常事件流：**  | 無  |
| **後置條件：**  | 	車輛的詳細資料已從系統中刪除。  |
## 第三章面向對象分析
### 3.1用例實現
使用順序圖，按BCE架構實現每個用例  
![图3-1登陆时序图 drawio](https://github.com/ycc17/final_report/assets/91513230/f987db6e-80b0-4532-8fe2-815cb967105b)  

圖3-1登陸時序圖

![图3-2删除车辆信息时序图 drawio](https://github.com/ycc17/final_report/assets/91513230/f67a2670-8885-459c-b3a6-ff645de3587d)  

圖3-2刪除車輛資訊時序圖

![图3-3添加车辆信息时序图 drawio](https://github.com/ycc17/final_report/assets/91513230/b6fa860d-9e86-487c-98f1-61c61410f840)  

圖3-3新增車輛資訊時序圖

![图3-5查找车辆信息时序图 drawio](https://github.com/ycc17/final_report/assets/91513230/df932e19-6898-40da-bebe-fe85f03436b7)  

圖3-5找出車輛資訊時序圖  

![图3-6查看车辆信息时序图 drawio](https://github.com/ycc17/final_report/assets/91513230/296d36a3-1360-4c6f-a1d3-7f5788fc3773)  

圖3-6查看車輛資訊時序圖
### 3.2分析類模型
建立系統的分析類別圖，為每個類別分配職責、屬性，及對類別之間的關係建模
![3 2分析类模型 drawio](https://github.com/ycc17/final_report/assets/91513230/81ca3d94-a8ab-4024-9ac1-afe263168152)

## 第四章物件導向設計
### 4.1資料庫設計
資料庫結構
1. 車輛資訊表
   
| 列名  | 資料類型 | 可否為空 | 說明 | 備註 |
| :---: | :---: | :---: | :---: | :---: |
| **Carin**  | Datetime  | Not null  | 入庫時間  | 主碼  |
| **Carout**  | Datetime  |   | 出庫時間  |  |
| **carpay** |	Float(20)  |  | 停車費用  |   |
| **carno**  | Varchar(20)  | Not null  | 車牌號  | 主碼  |

表3.5車輛資訊表

2. 管理員資訊表

| 列名  | 資料類型 | 可否為空 | 說明 | 備註 |
| :---: | :---: | :---: | :---: | :---: |
| **rId**  | varchar（20）  | Not null  | 管理員帳號  | 主碼  |
| **password**  | Varchar(20)  | Not null  | 密碼  |   |

表4.1 管理員資訊表
### 4.2設計類
實體類別

在OOA階段得到的類別圖中有兩個實體，分別是車輛和管理員

- 邊界類

1. 管理者登陸邊界類別—LogOn.java
2. 車輛資訊管理—mainWindowsjava
3. 輸入車輛資訊介面—addcar.java
4. 查詢車輛資訊介面—findcar.java
5. 刪除車輛資訊介面—delcar.java

- 控制類

1. 登陸控制類別—接收登陸請求，控制登陸過程的狀態，呼叫模型，轉送請求到管理者登陸邊界類logOn.java。
2. 車輛資訊管理—接收請求，控制車輛資訊管理的執行狀態，呼叫模型，得到處理結果，轉送請求到車輛資訊管理mainWindows.java。
3. 輸入車輛資訊—接收輸入請求，控制輸入車輛資訊的執行狀態，呼叫模型，得到處理結果，轉發請求到輸入車輛資訊addcar.java。
4. 查詢車輛資訊—接收查詢請求，控制查詢車輛資訊的執行狀態，呼叫模型，得到處理結果，轉發請求到查詢車輛資訊FindCar.java。
5. 刪除車輛資訊—接收刪除要求，控制刪除車輛資訊的執行狀態，呼叫模型，得到處理結果，轉發請求到刪除車輛資訊DelCar.java。
### 4.3軟體體系結構
本系統採用MVC設計模式建構程式結構，模型用來完成業務邏輯的封裝，控制器控制各個程式流程，也就是上一個設計的控制類別的實作；視圖用來顯示頁面，也就是上一步設計的邊界類別的實作。

模型部分除了包含上一步驟設計的實體類別的屬性封裝外，還需要實作實體類別對應的各個方法，對全部的業務功能進行分類，設計各個業務的Bean如下。

carService實現車輛資訊管理相關的業務，包含以下方法：
```
add_in()---在車輛資訊表中新增一條車輛入庫資訊。  
Add_out()---在車輛資訊表中新增一輛車出庫資訊。  
FindCar()---查詢車輛信息。  
delCar()---刪除車輛訊息。  
lookCar()—查看車輛資訊。  
```
### 4.4互動介面設計
1. 登陸logOn.java
   
![登陸介面設計](https://github.com/ycc17/final_report/assets/91513230/6d6e1850-e03c-411d-a5a0-fe0bba227b03)  
  圖4-1登陸介面設計  
2. 車輛資訊管理mainWindows.java

![車輛資訊管理介面設計](https://github.com/ycc17/final_report/assets/91513230/c9da395d-27fc-47a6-9565-9644dbda69f5)  
  圖4-2車輛資訊管理介面設計  
  
![瀏覽車輛信息](https://github.com/ycc17/final_report/assets/91513230/c407e72f-5624-4d1a-8d09-2f93d8b5b409)  
  圖4-3瀏覽車輛信息  
  
![新增車輛信息](https://github.com/ycc17/final_report/assets/91513230/600271b9-384a-41a4-bba1-f9dca2114fe7)  
  圖4-4新增車輛信息  
   
![新增出庫車輛信息](https://github.com/ycc17/final_report/assets/91513230/7c0a769a-28c1-4512-86b6-eccdf061c940)  
  圖4-5新增出庫車輛信息  
  
6. 刪除車輛資訊DelCar.java
   
![刪除車輛信息](https://github.com/ycc17/final_report/assets/91513230/48d96d0e-7108-4efc-bd0d-24a544d73d82)  
  圖4-6刪除車輛信息

7. 查詢車輛資訊findCar.java
   
   ![查詢車輛信息](https://github.com/ycc17/final_report/assets/91513230/70b1d6ec-4677-4ba7-b79a-8872b166137e)  
  圖4-7查詢車輛信息  
## 第五章面向對象實現
### 5.1停車場資訊管理系統編碼實現
本系統基於Java+MySQL+swing，
![1](https://github.com/ycc17/final_report/assets/91513230/f4e9663e-c8cf-4f76-96d6-db25bb49c423)
## 第六章軟體測試與部署
### 6.1 軟體測試
本停車管理系統在設計開發過程中就採用軟體測試的V模型來規範軟體測試。V型推崇開發與測試並行的方式，在開發完一個功能模組後就進行對應的單元測試，注重細節方面的問題。接著再進行整合測試，主要測試模組間的介面能否互通的問題。最後，在進行功能測試來偵測整個系統運作是否正常。

在測試過程中主要採取的是功能測試，透過功能測試可以逐一檢測各個功能是否可以滿足停車場管理人員的需求。

### 6.2 功能測試
功能測試是一種黑盒測試，這是根據軟體需求的要求設計測試案例並驗證系統功能的過程，並且透過與測試系統的外部輸入與輸出的關係來驗證。功能測試在於測試功能是否正常，因此不考慮內部的實作方式，測試的前提是系統已經處於運作狀態。

本停車管理系統對在設計開發過程中多次對系統功能進行測試，確保功能的正常運作。

### 6.3功能測試總結
主要針對停車場管理系統的登入、車輛駛入、車輛駛出、車輛資訊的增刪改查作業進行功能測試。測試過程中介面UI的顯示都符合預期，功能方面符合需求。

### 6.4用例測試
6.4.1登入用例測試
| 測試用例編號 | Login_01 |
| :---: | :---: |
| 測試標題  | 輸入正確的使用者名稱和與之對應的密碼  |
| 預置條件  | 系統存在該用戶  |
| 輸入  | Username:admin123<br>Password:123456  |
| 操作步驟  | 開啟系統登入頁面，輸入<br>username(admin123),password(123456)  |
| 預期輸出  | 密碼輸入時被隱藏，管理員登入系統首頁  |
| **測試用例編號** | **Login_02** |
| 測試標題  | 輸入錯誤的使用者名稱或錯誤的密碼  |
| 預置條件  | 系統不存在該用戶  |
| 輸入  | Username:隨機<br>Password:隨機  |
| 操作步驟  | 開啟系統登入頁面，輸入username,password  |
| 預期輸出  | 提示用戶“登入失敗！用戶名或密碼錯誤”  |

6.4.2添加資訊用例測試

| 測試用例編號 | Add_01 |
| :---: | :---: |
| 測試標題  | 增加後可在頁面中查看該信息  |
| 預置條件  | 管理員登入成功  |
| 輸入  | 輸入要新增的信息  |
| 操作步驟  | 點選【新增】，輸入對應的訊息，點選【新增】  |
| 預期輸出  | 終端輸出“添加成功！”  |

6.4.3查詢資訊用例測試

| 測試用例編號 | Find |
| :---: | :---: |
| 測試標題  | 輸入車牌號碼後可以看到相關訊息  |
| 預置條件  | 管理員登入成功，所查詢的資訊存在  |
| 輸入  | 相應車牌號  |
| 操作步驟  | 輸入要查詢的車牌號碼訊息，點選【查詢】  |
| 預期輸出  | 介面顯示出其相關的資訊。  |

6.4.4瀏覽資訊用例測試

| 測試用例編號 | Look |
| :---: | :---: |
| 測試標題  | 瀏覽所有的車輛信息  |
| 預置條件  |  管理員登入成功，所瀏覽資訊存在 |
| 輸入  | 無  |
| 操作步驟  | 點選【瀏覽車輛資訊】  |
| 預期輸出  | 瀏覽頁面顯示所有的車輛資訊詳情  |

6.4.5刪除資訊用例測試

| 測試用例編號 | Delete |
| :---: | :---: |
| 測試標題  | 確認刪除訊息後無法看到該訊息  |
| 預置條件  |  管理員登入成功，所刪除資訊存在 |
| 輸入  | 無  |
| 操作步驟  | 輸入要刪除的車牌號碼訊息，點選【刪除】  |
| 預期輸出  | 終端輸出“刪除成功！”，頁面中該資訊不存在  |

### 6.5本章小結
本章節主要介紹了對停車場管理系統進行功能測試的必要性和測試結果，針對目前停車管理系統設計了一系列的功能測試案例。透過系統測試使系統更能符合預期要求，並能偵測和修復一些開發過程中的bug。
# 參考文章
- https://blog.csdn.net/qq_61839797/article/details/128164668
