# 深度學習初學者祕技! 輕鬆備妥NVIDIA GPU深度學習高速運算環境.
誰說要先學會安裝Ubuntu, CUDA, Docker, NVIDIA support for Docker, Tensorflow/Keras(且以上安裝方式的官網一直會修改)才能開始寫深度學習?  
以下的密技讓你輕鬆備妥NVIDIA GPU高速運算環境, 快速開始撰寫深度學習程式, 投資自己賺取更高的年薪.  
USB隨身碟插上去是GPU加速深度學習機, USB隨身碟拔起來是遊戲機, 從此遊戲+學習兩不誤.  


# 先觀看一分鐘影片 https://youtu.be/_T55PHJ0USQ
1. 下載隨身碟映像檔, 還原到一隻空的高速隨身碟.  
2. 在NVIDIA GTX 1060以上規格GPU的桌機或者筆電上, 修改主機板BIOS開機選項, 從這支隨身碟開機.  
   恭喜你. 你已備妥NVIDIA GPU深度學習高速運算環境, 並直接進入Jupyter Notebook文字編輯器.  
   
___
___

# 逐步說明安裝方法(僅需一次)  
**(僅需一次) 準備:** 
1. 買一隻64GB或者128GB**高速**隨身碟.  
   (最推薦SanDisk Extreme Pro CZ880 128GB, 讀取/寫入速度=420MBps/380MBps)  
   (推薦~~SanDisk Extreme Go CZ800 64GB, 讀取/寫入速度=200MBps/150MBps~~)  
   隨身碟讀取/寫入速度很重要, 訓練過程資料頻繁讀寫, 務必買最快的.
2. 用微軟磁碟管理程式(Disk Management)把新買隨身碟的兩個磁碟分割區合併成一個.  
   新買隨身碟通常有兩個磁碟分割區, 不能用.  
   (7種打開Windows 10磁碟管理程式的方法 https://goo.gl/SpLMqW)  
   (若磁碟管理程式無法合併兩個磁碟分割區成一個, 用'DiskPart'指令, 能完美清除隨身碟上所有磁碟分割區到只剩一個.  
   DiskPart指令有: List Disk -> Select Disk # -> List Partition -> Clean)  
   任意選用Windows能認得的格式, 格式化這個只有一個磁碟分割區的隨身碟.  
3. 下載'Acronis True Image 2018'的映像檔還原工具. (試用期間免費, 正版$49美金).  
   官網網址 = https://www.acronis.com/zh-tw/personal/computer-backup/   
4. 下載我製作的21GB映像檔.  
   檔名 = 'DLImage_v1.0-4-7_full_b1_s1_v1.tib'  
   下載連結 = https://goo.gl/FF3dQ2  

**(僅需一次) 7步驟還原USB映像檔:**  
1. 安裝/註冊'Acronis True Image 2018', 之後關閉應用程式.  
2. 搬移下載的21GB USB映像檔到Windows桌面上.  
3. 在桌面21GB映像檔圖示按下滑鼠右鍵, 選擇'Acronix True Image', 然後選擇'Validate(驗證)'.  
![](/photo/Picture1a.png)  
4. Acronix True Image應用程式會被開啟, 點選顯示於左上方的映像檔. (步驟1) 
![](/photo/Picture1b.png)  
5. 在上方點選'Recovery(還原/恢復)'. (步驟2)  
   在下方點選'Recovery disk(還原磁碟/恢復磁碟)'. (步驟3)  
![](/photo/Picture1c.png)
6. 在中央左方'Backup'打勾確認要還原USB映像檔. (步驟4)  
   在中央右方'Recover to(還原到)'下拉謹慎選對那隻空的USB隨身碟. (步驟5)  
   在右下方點選'Recovery now(開始還原/開始恢復)'. (步驟6)  
![](/photo/Picture1d.png)  
   會打開一個新視窗.  
   務必打勾新視窗下方的 **`'Shot down the computer after completion(完成後自動關機)'`**.  重要! (步驟7)
7. 完成後會自動關機, 這時候去看個電視吧.  

**(僅需一次) 設定主機板BIOS+判別是否成功支持NVIDIA GPU加速:**  
1. 關機時, 插上USB隨身碟.
2. 開機期間, 進入主機板BIOS設定(通常是按DEL鍵,F2或是F10鍵, 依主機板而定).  
3. 在主機板BIOS設定中. **`關閉'Secure Boot'(Disable 'Secure Boot')`** 或者 **`打開CSM(Enable 'CSM (Compatibility Support Module))'`**  
4. 在主機板BIOS設定中. 維持預設的'UEFI開機(UEFI boot)'選項不要去改動它.  
5. 在主機板BIOS設定中. **`'開機優先順序(Boot Priority/Sequency)選擇最先從這隻USB隨身碟開機`**.  
6. 在主機板BIOS設定中. 儲存改變並重開機.  
7. 重開機之後會進到Ubuntu系統內, 系統預設密碼是小寫的 **`nvidia`**  
8. 進到Ubuntu系統內. 按下'ctrl'+'alt'+'t'組合鍵, 打開Ubuntu終端機視窗.  
9. 進到Ubuntu系統內. 在Ubuntu終端機視窗, 輸入指令 **`nvidia-smi`** 檢查你的NVIDIA GPU型號是否被正確的顯示出來.  
   如果你的NVIDIA GPU型號被正確的顯示出來, 表示所有的過程都正確, 你已備妥NVIDIA GPU深度學習高速運算環境.
![](/photo/Picture2a.png)  
10. (選用步驟) 如果你買的USB隨身碟實際容量大於64GB, 在還原映像檔之後你買的USB隨身碟會縮小到只有64GB, 這是因為我的映像檔是從一支64GB容量USB隨身碟拍攝下來的. 你能用Ubuntu指令'sudo gparted'把隱藏的USB隨身碟容量擴增回來.  
     進到Ubuntu系統內. 在Ubuntu終端機視窗, 輸入指令 **`sudo gparted`**  
     它會問你Ubuntu開機密碼, 系統預設密碼是小寫的 **`nvidia`**  
     跳出gparted視窗中, 在64GB的磁碟分區圖上按滑鼠右鍵, 選擇'調整大小(Resize)'.  
     滑鼠點住橫向長條圖的中央分隔線不放, 從中間向右拖到底, 就能把USB隨身碟容量從64GB擴增到最大容量.  
     還沒結束喔. 在gparted視窗上面有一個綠色勾勾按鈕, 按下去確認才算完成改變.  
   
___
___
# 開始使用(每次都要)  
**每次開始寫Deep Learning程式的時候 (基礎篇):**  
1. 用這隻USB隨身碟開機, 系統預設密碼是小寫的 **`nvidia`**  
2. 進到Ubuntu系統內. 按下'ctrl'+'alt'+'t'組合鍵, 打開Ubuntu終端機視窗.  
3. 在Ubuntu終端機視窗, 輸入指令 **`sudo docker start -ai tensorflowkeras`** 啟動'tensorflowkeras'的 docker image.  
   系統預設密碼是小寫的 **`nvidia`**   
![](/photo/Picture3a.png)  
4. 視窗底下出現一個連結, 滑鼠移到連結上按右鍵打開它, 會開啟一個Firefox視窗.  
![](/photo/Picture3b.png)  
5. 恭喜你, 已經打開Jupyter Notebook文字指令編輯器, 現在你能享用NVIDIA GPU深度學習高速運算環境!  
![](/photo/Picture3c.png)   

**每次開始寫Deep Learning程式的時候 (進階篇):**  
1. 下載好的訓練資料, 只會出現在Ubuntu的檔案總管裡, 沒辦法讓NVIDIA Docker Image的虛擬機看見, 怎麼辦呢?  
   別擔心, 都幫你設定好了, 這兩個目錄是虛實相連的:  
   Ubuntu檔案總管裡面的目錄 = /Home/dataset  
   NVIDIA Docker Image裡面的目錄 = /notebooks/dataset  
   你能 **把訓練資料搬到Ubuntu檔案總管裡面的目錄 = /Home/dataset**, 這樣就能 **在NVIDIA Docker Image裡面的目錄 = /notebooks/dataset取用**  
   看我底下的螢幕截圖, 任何新增在左邊視窗Ubuntu檔案總管裡面的目錄 = /Home/dataset內的檔案或目錄, 都能在右邊視窗NVIDIA Docker Image裡面的目錄 = /notebooks/dataset被取用  
   當你需要下載外部訓練訓練資料時(總是如此), 這是一個重要且必備的技能.  
![](/photo/Picture4a.png)  
![](/photo/Picture4b.png)  
2. 好用的Linux指令字典  
A. `查詢所有的docker images`  
Ubuntu終端機指令「sudo docker images」. 看所有的docker images, 與其repository_name:tag資訊.  
B. `查詢所有的containers`  
Ubuntu終端機指令「sudo docker ps 」, 看正在執行中的containers  
Ubuntu終端機指令「sudo docker ps -a 」, 看所有的containers (不管執行中還是沒在執行的). 能看到所有的containers, 包括其container ID, 與container name.  
C. `刪除不要的舊docker image`  
Ubuntu終端機指令「sudo docker rmi [add docker image’s repository_name:tag]」, 刪除之.  
D. `刪除不要的舊container`  
Ubuntu終端機指令「sudo docker rm [add container’s container id]」, 或  
Ubuntu終端機指令「sudo docker rm [add container’s container name]」, 刪除之.  
E. `把container存成一個docker image封存起來 (為了要備份起來, 步驟1)`  
Ubuntu終端機指令「sudo docker commit [container_ID] [repository_name:Tag]」  
F. `把docker image存成一個外部Ubuntu檔案總管能看見的檔案, 方便儲存/搬移/備份 (為了要備份起來, 步驟2)`  
Ubuntu終端機指令「sudo docker save [repository_name:Tag] -o [外部ubuntu檔案絕對路徑/新檔名]」  
G. `改名container方便管理`  
Ubuntu終端機指令「sudo docker rename [原本的container_name] [想要的container_name]」  
H. `重開機之後, start啟動/attach進入已經關閉的container, 取得一個能進入Jupyter Notebook的URL連結`  
每次Ctrl+C退出, 或者電腦整關後, container都是退出且關閉的. 
想進入container必須做兩個動作, 啟動＋進入container.
先用Ubuntu終端機指令「sudo docker ps -a」 看全部包含執行與不執行的containers.
啟動container：用Ubuntu終端機指令「sudo docker start -ai 加上 container_ID」
這時候能顯示URL. 滑鼠右鍵點開URL連結會開啟Firefox視窗, 自動打開Jupyter Notebook. 
I. `如果遇到install過程有小瑕疵, 想要完全複寫重灌`  
在原來指令install之後補參數-reinstall  
例如sudo apt install -reinstall cuda  
J. `如果遇到明明有網路卻不能聯網安裝, 可能是DNS沒有設`  
Ubuntu終端機指令「sudo gedit /etc/default/docker」  
編輯文件 把DNS 8.8.8.8 那行前面#註解符號刪除 (原本寫成了註解沒有執行), 然後儲存並關閉文件.  
重開電腦, 或者重啟服務Ubuntu終端機指令「sudo service docker restart」  
K. `遇到無線網路存在 也不是DNS問題 只是太久沒動電腦無線網路自己斷了不回來`  
到Ubuntu介面 '系統'圖示下 '網路'圖示下 雙擊'無線網路'圖示 會重新連上無線網路  
L. `'!'符號的妙用. 在Jupyter Notebook內臨時需要到外部Terminal安裝模組, 無需跳出Jupyter Notebook到New Terminal`  
只要在Jupyter Notebook內新增一行以!開頭的指令執行, 例如! pip install或者! ls 或者! cd /notebooks/dataset   
M. `'Tab'鍵在Jupyter Notebook編輯器內的妙用 (第一部分)`  
指令plt.後面不知道怎選擇, 能在Jupyter Notebook內新增一行輸入plt.接著按Tab鍵, 所有的選項都自動列出可選.  
N. `'Tab'鍵在Jupyter Notebook編輯器內的妙用 (第二部分)`  
指令需要取用container裡面的訓練/測試資料集, 而目錄名稱不好找, 能在Jupyter Notebook內新增一行輸入目錄的開頭p = patient.PatientData(“/notebooks/ 接著按Tab鍵, 所有的子目錄都自動列出可選).  
   
___
___
**備註**: 這個USB映像檔包含一個範例程式 - 'NVIDIA+GPU+Deep+Learning+Acceleration+Keras+Example+Code.ipynb'  
  **`參考書籍#1: TensorFlow+Keras深度學習人工智慧實務應用 ISBN：9789864342167 作者: 林大貴 出版社: 博碩出版社`**  
  **`參考書籍#2:TensorFlow+Keras深度学习人工智能实践应用 ISBN：9787302493020 作者: 林大貴 出版社: 清华大学出版社`**  
  **特別感謝作者 林大貴 老師這隻範例程式的正版授權** 我特別推薦本書給大家.  
在程式上按兩下打開它, 然後選擇Jupyter Notebook上方選單的 **`Cell`**, 再選 **`Run All`**.  
這會自動跑完60000張手寫0~9文字的深度學習訓練, 體驗NVIDIA GPU深度學習高速運算給你帶來的便利. 
![](/photo/Picture3d.png)  

# 這裡有個簡短的PDF檔, 介紹本秘技給你帶來的好處. https://drive.google.com/open?id=15GhsZpFBQWe4GWcdmnvagsDtRtWRXgF2  

 


