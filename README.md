# DL-Beginners-NVIDIA-GPU-accelerated-Platform-in-an-instant
DL(Deep Learning) beginners to deploy NVIDIA GPU accelerated platform in an instant.

# How - 1 minute video https://youtu.be/_T55PHJ0USQ
1. Restore Image to a high speed USB Drive.  
2. On NVIDIA GPU Desktop/Laptop (GeForce GTX 1060 and above), change motherboard BIOS settings and boot from USB Drive.  
   Congratulations. You can start using Jupyter Notebook editor, with NVIDIA GPU accelerated Docker platform for DL coding.  

   **Every time Start DL Coding:**  
   1. Boot from restored Ubuntu USB Drive, the Ubuntu login password = **`nvidia`**  
   2. Press hot keys 'ctrl'+'alt'+'t' to launch Ubuntu terminal window.  
   3. Type command **`sudo docker start -ai tensorflowkeras`** to run the 'tensorflowkeras' docker image.  
      Ubuntu login password = **`nvidia`**  
   ![](/photo/Picture3a.png)  
   4. It will show a link, right click mouse to open that link with Firefox.  
   ![](/photo/Picture3b.png)  
   5. It's Jupyter Notebook, now you can start Deep Learning coding with NVIIDA GPU Accelerations.  
   ![](/photo/Picture3c.png)  
   Congratulations! You are all set to go.  
   
___
___

# Step by Step https://drive.google.com/open?id=1Ej6yEKNOf5cP-3wNcayEGJ_BN4GpzYGz
**(One-time) Preparation:** 
1. Buy 1pcs high speed USB Drive 64GB or 128GB.  
   (Recommend SanDisk Extreme Pro CZ880 128GB, Read/Write=420MBps/380MBpcs)  
   (Recommend SanDisk Extreme Go CZ800 64GB, Read/Write=200MBps/150MBps)  
2. Use Windows 10 Disk Management to merge USB Drive 2 partitions into just 1.  
   Newly purchased USB Drive used to have 2 partitions that we cannot use.  
   (7 ways to open Disk Management in Windows 10 https://goo.gl/SpLMqW )  
   Format the Single Partition USB Drive in any format that Windows can recognize.  
3. Download “Acronis True Image 2018”. (Trial period for free, $49.99 per copy).  
   Link = https://www.acronis.com/en-us/personal/computer-backup/  
4. Download 21GB USB Drive image I prepared for you.  
   File Name = “DLImage_v1.0-4-7_full_b1_s1_v1.tib”  
   Link = https://goo.gl/FF3dQ2  

**(One-time) Restore USB Image:**  
1. Install/Sign_In "Acronis True Image 2018", then quit/close it.  
2. Move downloaded 21GB USB Drive image to windows desktop.  
3. Right click that 21GB Drive image icon on desktop, click 'Acronix True Image', then click 'Validate'.  
![](/photo/Picture1a.png)  
4. Acronix True Image app will be launched, choose the image been added on the upper left. (STEP1)  
![](/photo/Picture1b.png)  
5. Choose 'Recovery' on the top. (STEP2)  
   Choose 'Recovery disk' on the bottom. (STEP3)  
![](/photo/Picture1c.png)
6. Choose the 'Backup Image' on the middle left. (STEP4)  
   Choose the 'Recover to' empty USB Disk on the middle right. (STEP5)  
   Choose the 'Recovery now' on the bottom right. (STEP6)  
   On the next pop up page, Check the **`'Shot down the computer after completion'`** on the bottom. Important! (STEP7)
![](/photo/Picture1d.png)  
7. Automatically shot down after Restore USB Image.  

**(One-time) Setup motherboard BIOS and test USB Drive:**  
1. When power off, plug-in the USB Drive.
2. While booting up, enter motherboard BIOS settings.  
3. On BIOS. **`Disable 'Secure Boot'`** or **`Enable 'CSM (Compatibility Support Module)'`**  
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
     

 
**Every time Start DL Coding:**  
1. Boot from restored Ubuntu USB Drive, the Ubuntu login password = **`nvidia`**  
2. Press hot keys 'ctrl'+'alt'+'t' to launch Ubuntu terminal window.  
3. Type command **`sudo docker start -ai tensorflowkeras`** to run the 'tensorflowkeras' docker image.  
   Ubuntu login password = **`nvidia`**  
![](/photo/Picture3a.png)  
4. It will show a link, right click mouse to open that link with Firefox.  
![](/photo/Picture3b.png)  
5. It's Jupyter Notebook, now you can start Deep Learning coding with NVIIDA GPU Accelerations. Congratulations!  
![](/photo/Picture3c.png)  

**NOTE**: The USB includes an example code - 'NVIDIA+GPU+Deep+Learning+Acceleration+Keras+Example+Code.ipynb'   
Double click to open it, then choose  **`Cell`**, then choose **`Run All`**.  
Use 60000 hand write 0~9 texts for DL convolutional training on NVIDIA GPU. 
![](/photo/Picture3d.png)  

# Your Benefits - Short PDF Deck https://drive.google.com/open?id=1lO3m7iRyBn1wYJ74W7-NKCy7SsgZRKsT
