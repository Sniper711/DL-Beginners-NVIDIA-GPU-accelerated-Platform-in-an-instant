# 深度學習初學者祕技! 輕鬆備妥NVIDIA GPU深度學習高速運算環境.
誰說要先學會安裝Ubuntu, CUDA, Docker, NVIDIA support for Docker, Tensorflow/Keras(且以上安裝方式的官網一直會修改)才能開始寫深度學習?  
以下的密技讓你輕鬆備妥NVIDIA GPU高速運算環境, 快速開始撰寫深度學習程式, 投資自己賺取更高的年薪.  
USB隨身碟插上去是GPU加速深度學習機, USB隨身碟拔起來是遊戲機, 遊戲+學習兩不誤.  


# 先觀看一分鐘影片 https://youtu.be/_T55PHJ0USQ
1. 下載隨身碟映像檔, 還原到一隻空的高速隨身碟.  
2. 在NVIDIA GTX 1060以上規格GPU的桌機或者筆電上, 修改主機板BIOS開機選項, 從這支隨身碟開機.  
   恭喜你. 你已備妥NVIDIA GPU深度學習高速運算環境, 並直接進入Jupyter Notebook文字編輯器.  
   
___
___

# 逐步說明安裝方法
**(只需做一次) 準備:** 
1. 買一隻64GB或者128GB**高速**隨身碟.  
   (推薦SanDisk Extreme Pro CZ880 128GB, 讀取/寫入速度=420MBps/380MBps)  
   (推薦~~SanDisk Extreme Go CZ800 64GB, 讀取/寫入速度=200MBps/150MBps~~)  
   隨身碟讀取/寫入速度很重要, 務必買最快的.
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

**(只需做一次) 還原USB映像檔:**  
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
   會打開一個新視窗.  
   務必打勾新視窗下方的 **`'Shot down the computer after completion(完成後自動關機)'`**.  重要! (步驟7)
![](/photo/Picture1d.png)  
7. 完成後會自動關機, 這時候去看個電視吧.  

**(只需做一次) 設定主機板BIOS+判別是否支持NVIDIA GPU加速:**  
1. 關機時, 插上USB隨身碟.
2. 開機期間, 進入主機板BIOS設定(通常是按DEL鍵,F2或是F10鍵, 依主機板而定).  
3. 在主機板BIOS設定中, **`關閉'Secure Boot'(Disable 'Secure Boot')`** 或者 **`打開CSM(Enable 'CSM (Compatibility Support Module))'`**  
4. On BIOS. Remain default 'UEFI boot' option without change it.  
5. On BIOS. **`'Boot Priority/Sequency' choose to boot from the USB Drive`**.  
6. On BIOS. Save changes and reboot.  
7. In Ubuntu. It will boot into Ubuntu, the Ubuntu login password = **`nvidia`**  
8. In Ubuntu. Press hot keys 'ctrl'+'alt'+'t' to open Ubuntu terminal window.  
9. In Ubuntu. Type command **`nvidia-smi`** to exam if your NVIDIA GPU model is correctly recognized and listed.  
   If your NVIDIA GPU model is shown, it means everything works fine.
![](/photo/Picture2a.png)  
10. (Optional) If your USB Drive is more than 64GB. This USB Image is created with 64GB sized USB Drive. If your USB Drive is more than 64GB physically, after restore your USB Drive will show 64GB only. You can use Ubuntu instruction 'sudo gparted' to expend size.  
     In Ubuntu, Type command **`sudo gparted`**  
     It requires Ubuntu login password, the Ubuntu login password = **`nvidia`**  
     Right click 64GB partition, select Resize it.  
     Drag bar to right end to increase 64GB partition to max physical capacity.
     Click the 'Green Check Mark' to 
     

 
**Every time Start DL Coding (basic):**  
1. Boot from restored Ubuntu USB Drive, the Ubuntu login password = **`nvidia`**  
2. Press hot keys 'ctrl'+'alt'+'t' to launch Ubuntu terminal window.  
3. Type command **`sudo docker start -ai tensorflowkeras`** to run the 'tensorflowkeras' docker image.  
   Ubuntu login password = **`nvidia`**  
![](/photo/Picture3a.png)  
4. It will show a link, right click mouse to open that link with Firefox.  
![](/photo/Picture3b.png)  
5. It's Jupyter Notebook, now you can start Deep Learning coding with NVIIDA GPU Accelerations. Congratulations!  
![](/photo/Picture3c.png)   

**Every time start DL Coding (advanced):**  
1. These 2 foder path are connexted:  
   Ubuntu path = /Home/dataset  
   Docker Image path = /notebooks/dataset  
   You can **move training data under Ubuntu path = /Home/dataset**, then you can **access it under Docker Image path = /notebooks/dataset**  
   Look at the example screenshot, any files you put under the left window Ubuntu path = /Home/dataset, you can find it on the right window Docker Image path = /notebooks/dataset  
   This is important skill for you to train external dataset files.
![](/photo/Picture4a.png)  
![](/photo/Picture4b.png)  
2. Useful Linux instructions  
A. `Check docker images`  
Instruction $「sudo docker images」. You can see all docker images, and repository_name:tag info of all docker images.  
B. `Check containers`  
Instruction $「sudo docker ps 」, to check running containers  
Instruction $「sudo docker ps -a 」, to check all containers (no matter it’s running or not). You can see all containers, all containers’ ID, all containers’ name.  
C. `Delete docker image`  
Instruction $「sudo docker rmi [add docker image’s repository_name:tag]」, to delete it.  
D. `Delete container`  
Instruction $「sudo docker rm [add container’s container id]」, or  
Instruction $「sudo docker rm [add container’s container name]」, to delete it.  
E. `Save/Snapshot a container into a docker image (to keep it forever)`  
Instruction $「sudo docker commit [container_ID] [repository_name:Tag]」  
F. `Save/Snapshot a docker image as a file to be visible by Ubuntu File Folder application, therefore you can move/backup/manage it`  
Instruction $「sudo docker save [repository_name:Tag] -o [external_ubuntu_file_path/file_name]」  
G. `Rename Container`  
Instruction $「sudo docker rename [Original container_name] [Wanted container_name]」  
H. `After reboot, start/attach closed container, find/copy/paste URL to enter Jupyter Notebook`  
Container will be deactivated, whenever quit with Ctrl+C, or PC shutdown.  
You need to start/attach container.  
Instruction $「sudo docker ps -a」, to check all available containers (include activated/deactivated containers).  
Instruction $「sudo docker start -ai [add container’s container id]」, to start/attach container.  
Now you will see an unique URL link. Copy/Paste it to Firefox then enter Jupyter Notebook.  
I. `In case of installation failure, you want to reinstall`  
Add “-reinstall” after original install instruction.  
For example: sudo apt install -reinstall cuda  
J. `In case of you failed to download while you do have internet connection, that might caused by DNS setup issue`  
Instruction $「sudo gedit /etc/default/docker」  
Edit document, to remove “#” sign before “DNS 8.8.8.8”, then save and close document.  
Reboot PC, or Instruction $「sudo service docker restart」, to reboot PC.  
K. `Sometimes wifi disconnect because of PC enter power saving mode`  
Go to Ubuntu OS, under “System” icon, find “Internet” icon.   
Double click “internet” icon, wifi will be reconnected.  
L. `Inside Jupyter Notebook, how to run instructions # (without quiting Jupyter Notebook and go to terminal`  
You just need to add 1 line of code, which is start with “!” sign.  
For example: 「! pip install」, or「! ls」, or「! cd/home/(your Ubuntu ID)/container」.   
M. `Inside Jupyter Notebook, “Tab” key is useful (part 1)`  
If you run instruction # inside Jupyter Notebook with “!” sign, and don’t know all the optional parameters, here is a useful way by press “Tab” key. (without quit Jupyter Notebook)  
For example, you can add 1 line of code「! Plt.」, and press “Tab” key now, it will show all the optional parameters of plt.  
N. `Inside Jupyter Notebook, “Tab” key is useful (part 2)`  
If you run instruction # inside Jupyter Notebook with “!” sign, and you need to call the dataset directory, here is a useful way by press “Tab” key. (without quit Jupyter Notebook)  
For example, you can add 1 line of text 「p = patient.PatientData(“/home/ and press “Tab” now, it will automatically output all the sub-dictory.  

**NOTE**: The USB image includes an example code - 'NVIDIA+GPU+Deep+Learning+Acceleration+Keras+Example+Code.ipynb'   
Double click to open it, then choose  **`Cell`**, then choose **`Run All`**.  
Use 60000 hand write 0~9 texts for DL convolutional training on NVIDIA GPU. 
![](/photo/Picture3d.png)  

# Your Benefits - Short PDF Deck https://drive.google.com/open?id=1lO3m7iRyBn1wYJ74W7-NKCy7SsgZRKsT
 


