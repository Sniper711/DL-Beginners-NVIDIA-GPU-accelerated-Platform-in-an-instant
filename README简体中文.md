# 深度学习初学者秘技! 轻松备妥NVIDIA GPU深度学习高速运算环境.
谁说要先学会安装Ubuntu, CUDA, Docker, NVIDIA support for Docker, Tensorflow/Keras(且以上安装方式的官网一直会修改)才能开始写深度学习?  
以下的密技让你轻松备妥NVIDIA GPU高速运算环境, 快速开始撰写深度学习代码, 投资自己赚取更高的年薪.  
U插上去是GPU加速深度学习机, USB随身碟拔起来是游戏机, 游戏+学习两不误.  


# 先看一分钟视频(有声版) http://v.youku.com/v_show/id_XMzYwNTc5NzQ3Ng 密码：nvidia  
1. 下载USB映像档, 还原到一只空的高速U盘.  
2. 在NVIDIA GTX 1060以上规格GPU的台式机或者笔记本上, 修改主板BIOS开机选项, 从这支U盘开机.
恭喜你. 你已备妥NVIDIA GPU深度学习高速运算环境, 并直接进入Jupyter Notebook文字编辑器.  
   
___
___

# 手把手教学(仅需一次)  
**(仅需一次) 准备:** 
1. 买一只64GB或者128GB**高速**U盘.  
   (最推荐SanDisk Extreme Pro CZ880 128GB, 读取/写入速度=420MBps/380MBps)  
   (推荐~~SanDisk Extreme Go CZ800 64GB, 读取/写入速度=200MBps/150MBps~~)  
   U盘读取/写入速度很重要, 训练过程资料频繁读写, 务必买最快的.
2. 用微软磁盘管理工具(Disk Management)把新买U盘的两个磁盘分区合并成一个.  
   新买U盘通常有两个磁盘分区, 不能用.  
   (7种打开Windows 10磁盘管理工具的方法 https://www.isunshare.com/windows-10/7-ways-to-open-disk-management-in-windows-10.html)  
   (若磁盘管理工具无法合并两个磁盘分区成一个, 用'DiskPart'指令, 能完美清除U盘上所有磁盘分区到只剩一个.  
   DiskPart指令有: List Disk -> Select Disk # -> List Partition -> Clean)  
   任意选用Windows能认得的格式, 格式化这个只有一个磁盘分区的U盘.  
3. 下载'Acronis True Image 2018'的映像档还原工具. (试用期间免费, 正版$49美金).  
   官网网址 = https://www.acronis.com/zh-cn/personal/computer-backup/  
4. 下载我制作的21GB映像档.  
   档名 = 'DLImage_v1.0-4-7_full_b1_s1_v1.tib'  
   下载链接：https://share.weiyun.com/5nSEZUV 密码：bpanvc  
   备用下载链接：https://pan.baidu.com/s/1XrXkftgXzSazyiynBkt2vQ 密码：k3wj

**(仅需一次) 7步骤还原USB映像档:**  
1. 安装/注册'Acronis True Image 2018', 之後关闭应用程序.  
2. 搬移下载的21GB USB映像档到Windows桌面上.  
3. 在桌面21GB映像档图示按下滑鼠右键, 选择'Acronix True Image', 然後选择'Validate(验证)'.  
![](/photo/Picture1a.png)  
4. Acronix True Image应用程序会被开启, 点选显示於左上方的映像档. (步骤1) 
![](/photo/Picture1b.png)  
5. 在上方点选'Recovery(还原/恢复)'. (步骤2)  
   在下方点选'Recovery disk(还原磁盘/恢复磁盘)'. (步骤3)  
![](/photo/Picture1c.png)
6. 在中央左方'Backup'打勾确认要还原USB映像档. (步骤4)  
   在中央右方'Recover to(还原到)'下拉谨慎选对那只空的U盘. (步骤5)  
   在右下方点选'Recovery now(开始还原/开始恢复)'. (步骤6)  
![](/photo/Picture1d.png)  
   会打开一个新视窗.  
   务必打勾新视窗下方的 **`'Shot down the computer after completion(完成後自动关机)'`**.  重要! (步骤7)
7. 完成後会自动关机, 这时候去看个电视吧.  

**(仅需一次) 设定主板BIOS+判别是否成功支持NVIDIA GPU加速:**  
1. 关机时, 插上U盘.
2. 开机期间, 进入主板BIOS设定(通常是按DEL键,F2或是F10键, 依主板而定).  
3. 在主板BIOS设定中. **`关闭'Secure Boot'(Disable 'Secure Boot')`** 或者 **`打开CSM(Enable 'CSM (Compatibility Support Module))'`**  
4. 在主板BIOS设定中. 维持预设的'UEFI开机(UEFI boot)'选项不要去改动它.  
5. 在主板BIOS设定中. **`'开机优先顺序(Boot Priority/Sequency)选择最先从这只U盘开机`**.  
6. 在主板BIOS设定中. 储存改变并重开机.  
7. 重开机之後会进到Ubuntu系统内, 系统预设密码是小写的 **`nvidia`**  
8. 进到Ubuntu系统内. 按下'ctrl'+'alt'+'t'组合键, 打开Ubuntu终端机视窗.  
9. 进到Ubuntu系统内. 在Ubuntu终端机视窗, 输入指令 **`nvidia-smi`** 检查你的NVIDIA GPU型号是否被正确的显示出来.  
   如果你的NVIDIA GPU型号被正确的显示出来, 表示所有的过程都正确, 你已备妥NVIDIA GPU深度学习高速运算环境.
![](/photo/Picture2a.png)  
10. (選用步驟) 如果你買的U盤實際容量大於64GB, 在還原映像檔之後你買的U盤會縮小到只有64GB, 這是因為我的映像檔是從一支64GB容量U盤拍攝下來的. 你能用Ubuntu指令'sudo gparted'把隱藏的U盤容量擴增回來.  
     进到Ubuntu系统内. 在Ubuntu终端机视窗, 输入指令 **`sudo gparted`**  
     它会问你Ubuntu开机密码, 系统预设密码是小写的 **`nvidia`**  
     跳出gparted视窗中, 在64GB的磁盘分区图上按鼠标右键, 选择'调整大小(Resize)'.  
     鼠标点住横向长条图的中央分隔线不放, 从中间向右拖到底, 就能把U盘容量从64GB扩增到最大容量.  
     还没结束喔. 在gparted视窗上面有一个绿色勾勾按钮, 按下去确认才算完成改变.  
   
___
___
# 开始使用(每次都要)  
**每次开始写Deep Learning程式的时候 (基础篇):**  
1. 用这只U盘开机, 系统预设密码是小写的 **`nvidia`**  
2. 进到Ubuntu系统内. 按下'ctrl'+'alt'+'t'组合键, 打开Ubuntu终端机视窗.  
3. 在Ubuntu终端机视窗, 输入指令 **`sudo docker start -ai tensorflowkeras`** 启动'tensorflowkeras'的 docker image.  
   系统预设密码是小写的 **`nvidia`**   
![](/photo/Picture3a.png)  
4. 视窗底下出现一个连结, 鼠标移到连结上按右键打开它, 会开启一个Firefox视窗.  
![](/photo/Picture3b.png)  
5. 恭喜你, 已经打开Jupyter Notebook文字指令编辑器, 现在你能享用NVIDIA GPU深度学习高速运算环境!  
![](/photo/Picture3c.png)   

**每次开始写Deep Learning程式的时候 (进阶篇):**  
1. 下载好的训练资料, 只会出现在Ubuntu的档案总管里, 没办法让NVIDIA Docker Image的虚拟机看见, 怎麽办呢?  
   别担心, 都帮你设定好了, 这两个目录是虚实相连的:  
   Ubuntu档案总管里面的目录 = /Home/dataset  
   NVIDIA Docker Image里面的目录 = /notebooks/dataset  
   你能 **把训练资料搬到Ubuntu档案总管里面的目录 = /Home/dataset**, 这样就能 **在NVIDIA Docker Image里面的目录 = /notebooks/dataset取用**  
   看我底下的屏幕截图, 任何新增在左边视窗Ubuntu档案总管里面的目录 = /Home/dataset内的档案或目录, 都能在右边视窗NVIDIA Docker Image里面的目录 = /notebooks/dataset被取用  
   当你需要下载外部训练训练资料时(总是如此), 这是一个重要且必备的技能.  
![](/photo/Picture4a.png)  
![](/photo/Picture4b.png)  
2. 好用的Linux指令字典  
A. `查询所有的docker images`  
Ubuntu终端机指令「sudo docker images」. 看所有的docker images, 与其repository_name:tag资讯.  
B. `查询所有的containers`  
Ubuntu终端机指令「sudo docker ps 」, 看正在执行中的containers  
Ubuntu终端机指令「sudo docker ps -a 」, 看所有的containers (不管执行中还是没在执行的). 能看到所有的containers, 包括其container ID, 与container name.  
C. `删除不要的旧docker image`  
Ubuntu终端机指令「sudo docker rmi [add docker image’s repository_name:tag]」, 删除之.  
D. `删除不要的旧container`  
Ubuntu终端机指令「sudo docker rm [add container’s container id]」, 或  
Ubuntu终端机指令「sudo docker rm [add container’s container name]」, 刪除之.  
E. `把container存成一个docker image封存起来 (为了要备份起来, 步骤1)`  
Ubuntu终端机指令「sudo docker commit [container_ID] [repository_name:Tag]」  
F. `把docker image存成一个外部Ubuntu档案总管能看见的档案, 方便储存/搬移/备份 (为了要备份起来, 步骤2)`  
Ubuntu终端机指令「sudo docker save [repository_name:Tag] -o [外部ubuntu档案绝对路径/新档名]」  
G. `改名container方便管理`  
Ubuntu终端机指令「sudo docker rename [原本的container_name] [想要的container_name]」  
H. `重开机之後, start启动/attach进入已经关闭的container, 取得一个能进入Jupyter Notebook的URL连结`  
每次Ctrl+C退出, 或者电脑整关後, container都是退出且关闭的. 
想进入container必须做两个动作, 启动＋进入container.
先用Ubuntu终端机指令「sudo docker ps -a」 看全部包含执行与不执行的containers.
启动container：用Ubuntu终端机指令「sudo docker start -ai 加上 container_ID」
这时候能显示URL. 鼠标右键点开URL连结会开启Firefox视窗, 自动打开Jupyter Notebook. 
I. `如果遇到install过程有小瑕疵, 想要完全复写重灌`  
在原来指令install之後补参数-reinstall  
例如sudo apt install -reinstall cuda  
J. `如果遇到明明有网路却不能联网安装, 可能是DNS没有设`  
Ubuntu终端机指令「sudo gedit /etc/default/docker」  
编辑文件 把DNS 8.8.8.8 那行前面#注解符号删除 (原本写成了注解没有执行), 然後储存并关闭文件.  
重开电脑, 或者重启服务Ubuntu终端机指令「sudo service docker restart」  
K. `遇到无线网路存在 也不是DNS问题 只是太久没动电脑无线网路自己断了不回来`  
到Ubuntu介面 '系统'图示下 '网路'图示下 双击'无线网路'图示 会重新连上无线网路  
L. `'!'符号的妙用. 在Jupyter Notebook内临时需要到外部Terminal安装模组, 无需跳出Jupyter Notebook到New Terminal`  
只要在Jupyter Notebook内新增一行以!开头的命令执行, 例如! pip install或者! ls 或者! cd /notebooks/dataset   
M. `'Tab'键在Jupyter Notebook编辑器内的妙用 (第一部分)`  
指令plt.後面不知道怎选择, 能在Jupyter Notebook内新增一行输入plt.接着按Tab键, 所有的选项都自动列出可选.  
N. `'Tab'键在Jupyter Notebook编辑器内的妙用 (第二部分)`  
指令需要取用container里面的训练/测试资料集, 而目录名称不好找, 能在Jupyter Notebook内新增一行输入目录的开头p = patient.PatientData(“/notebooks/ 接着按Tab键, 所有的子目录都自动列出可选).  
   
___
___
# 推荐中文书籍  
**备注**: 这个USB映像档包含一个范例程式 - 'NVIDIA+GPU+Deep+Learning+Acceleration+Keras+Example+Code.ipynb'  
  **`参考书籍#1: TensorFlow+Keras深度学习人工智慧实务应用 ISBN：9789864342167 作者: 林大贵 出版社: 博硕出版社`**  
  **`参考书籍#2:TensorFlow+Keras深度学习人工智能实践应用 ISBN：9787302493020 作者: 林大贵 出版社: 清华大学出版社`**  
  **特别感谢作者 林大贵 老师这只范例程式的正版授权** 我特别推荐本书给大家.  
在程式上按两下打开它, 然後选择Jupyter Notebook上方选单的 **`Cell`**, 再选 **`Run All`**.  
这会自动跑完60000张手写0~9文字的深度学习训练, 体验NVIDIA GPU深度学习高速运算给你带来的便利.  
![](/photo/Picture3d.png)  

___
___
# NVIDIA GPU 加速19倍快  
**GTX 1080 GPU 是 i7 CPU的 18.38倍快, 在IMBD影评分析上**  
![](/photo/GPUis18.38xfasterthanCPU.jpg)  
**GTX 1080 GPU 是 i7 CPU的 12.84倍快, 在MNIST手写辨识分析上**  
![](/photo/GPUis12.84xfasterthanCPU.jpg)  

# 这里有个简短的PDF档, 介绍本秘技给你带来的好处. 下载链接：https://pan.baidu.com/s/1HU12dji2olfdiVP-HXNhBA 密码：mf5f 

 


