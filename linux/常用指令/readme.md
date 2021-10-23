
#
```
值得收藏！Linux系統常用命令速查手冊
民工哥
民工哥

6 人贊同了該文章
給大家收集整理了日常常用的Linux系統命令，僅供大家參考。

系統資訊
arch      #顯示機器的處理器架構(1)
uname -m  #顯示機器的處理器架構(2)
uname -r  #顯示正在使用的內核版本
dmidecode -q          #顯示硬體系統部件 - (SMBIOS / DMI)
hdparm -i /dev/hda    #羅列一個磁片的架構特性
hdparm -tT /dev/sda   #在磁片上執行測試性讀取操作
cat /proc/cpuinfo     #顯示CPU info的資訊
cat /proc/interrupts  #顯示中斷
cat /proc/meminfo     #校驗記憶體使用
cat /proc/swaps       #顯示哪些swap被使用
cat /proc/version     #顯示內核的版本
cat /proc/net/dev     #顯示網路介面卡及統計
cat /proc/mounts      #顯示已載入的檔案系統
lspci -tv   #羅列PCI設備
lsusb -tv   #顯示USB設備
date 顯示系統日期
cal 2007              #顯示2007年的日曆表
date 041217002007.00   #設置日期和時間 - 月日時分年.秒
clock -w              #將時間修改保存到 BIOS
關機 (系統的關機、重啟以及登出 )
shutdown -h now    #關閉系統(1)
init 0            #關閉系統(2)
telinit 0         #關閉系統(3)
shutdown -h hours:minutes &   #按預定時間關閉系統
shutdown -c       #取消按預定時間關閉系統
shutdown -r now   #重啟(1)
reboot   #重啟(2)
logout   #註銷
檔和目錄
cd /home    #進入 '/ home' 目錄'
cd ..       #返回上一級目錄
cd ../..    #返回上兩級目錄
cd          #進入個人的主目錄
cd ~user1   #進入個人的主目錄
cd -       #返回上次所在的目錄

pwd        #顯示工作路徑

ls      #查看目錄中的檔
ls -F   #查看目錄中的檔
ls -l   #顯示檔和目錄的詳細資料
ls -a   #顯示隱藏檔
ls *[0-9]*   #顯示包含數位的檔案名和目錄名
tree         #顯示檔和目錄由根目錄開始的樹形結構(1)
lstree       #顯示檔和目錄由根目錄開始的樹形結構(2)

mkdir dir1         #創建一個叫做 'dir1' 的目錄'
mkdir dir1 dir2    #同時創建兩個目錄
mkdir -p /tmp/dir1/dir2   #創建一個目錄樹

rm -f file1    #刪除一個叫做 'file1' 的檔'
rmdir dir1     #刪除一個叫做 'dir1' 的目錄'
rm -rf dir1    #刪除一個叫做 'dir1' 的目錄並同時刪除其內容
rm -rf dir1 dir2    #同時刪除兩個目錄及它們的內容
mv dir1 new_dir     #重命名/移動 一個目錄

cp file1 file2     #複製一個檔
cp dir/* .         #複製一個目錄下的所有檔到當前工作目錄
cp -a /tmp/dir1 .   #複製一個目錄到當前工作目錄
cp -a dir1 dir2     #複製一個目錄

ln -s file1 lnk1  #創建一個指向檔或目錄的軟連結
ln file1 lnk1     #創建一個指向檔或目錄的物理連結

touch -t 0712250000 file1   #修改一個檔或目錄的時間戳記 - (YYMMDDhhmm)

file file1 outputs the mime type of the file as text

iconv -l   #列出已知的編碼
iconv -f fromEncoding -t toEncoding inputFile > outputFile creates a new from the given input file by assuming it is encoded in fromEncoding and converting it to toEncoding.
find . -maxdepth 1 -name *.jpg -print -exec convert "{}" -resize 80x60 "thumbs/{}" ; batch resize files in the current directory and send them to a thumbnails directory (requires convert from Imagemagick)


文件搜索
find / -name file1     #從 '/' 開始進入根檔案系統搜索檔和目錄
find / -user user1     #搜索屬於用戶 'user1' 的檔和目錄
find /home/user1 -name *.bin        #在目錄 '/ home/user1' 中搜索帶有'.bin' 結尾的文件
find /usr/bin -type f -atime +100    #搜索在過去100天內未被使用過的執行檔
find /usr/bin -type f -mtime -10     #搜索在10天內被創建或者修改過的檔
find / -name *.rpm -exec chmod 755 '{}' ;      #搜索以 '.rpm' 結尾的文件並定義其許可權
find / -xdev -name *.rpm        #搜索以 '.rpm' 結尾的檔，忽略光碟機、捷盤等可移動設備
locate *.ps       #尋找以 '.ps' 結尾的文件 - 先運行 'updatedb' 命令
whereis halt       #顯示一個二進位檔案、源碼或man的位置
which halt         #顯示一個二進位檔案或可執行檔的完整路徑


掛載一個檔案系統
mount /dev/hda2 /mnt/hda2    #掛載一個叫做hda2的盤 - 確定目錄 '/ mnt/hda2' 已經存在
umount /dev/hda2            #卸載一個叫做hda2的盤 - 先從掛載點 '/ mnt/hda2' 退出
fuser -km /mnt/hda2         #當設備繁忙時強制卸載
umount -n /mnt/hda2         #運行卸載操作而不寫入 /etc/mtab 檔- 當檔為唯讀或當磁片寫滿時非常有用
mount /dev/fd0 /mnt/floppy        #掛載一個軟碟
mount /dev/cdrom /mnt/cdrom       #掛載一個cdrom或dvdrom
mount /dev/hdc /mnt/cdrecorder    #掛載一個cdrw或dvdrom
mount /dev/hdb /mnt/cdrecorder    #掛載一個cdrw或dvdrom
mount -o loop file.iso /mnt/cdrom    #掛載一個檔或ISO鏡像檔
mount -t vfat /dev/hda5 /mnt/hda5    #掛載一個Windows FAT32檔案系統
mount /dev/sda1 /mnt/usbdisk         #掛載一個usb 捷盤或快閃記憶體設備
mount -t smbfs -o username=user,password=pass //WinClient/share /mnt/share      #掛載一個windows網路共用


磁碟空間
df -h           #顯示已經掛載的分區列表
ls -lSr |more    #以尺寸大小排列檔和目錄
du -sh dir1      #估算目錄 'dir1' 已經使用的磁碟空間'
du -sk * | sort -rn     #以容量大小為依據依次顯示檔和目錄的大小
rpm -q -a --qf '%10{SIZE}t%{NAME}n' | sort -k1,1n 
#以大小為依據依次顯示已安裝的rpm包所使用的空間 (fedora, redhat類系統)
dpkg-query -W -f='${Installed-Size;10}t${Package}n' | sort -k1,1n 
#以大小為依據顯示已安裝的deb包所使用的空間 (ubuntu, debian類系統)


用戶和群組
groupadd group_name   #創建一個新用戶組
groupdel group_name   #刪除一個用戶組
groupmod -n new_group_name old_group_name   #重命名一個用戶組

useradd -c "Name Surname " -g admin -d /home/user1 -s /bin/bash user1     #創建一個屬於 "admin" 用戶組的用戶
useradd user1      #創建一個新用戶
userdel -r user1   #刪除一個用戶 ( '-r' 排除主目錄)
usermod -c "User FTP" -g system -d /ftp/user1 -s /bin/nologin user1   #修改使用者屬性

passwd         #修改口令
passwd user1   #修改一個用戶的口令 (只允許root執行)
chage -E 2005-12-31 user1    #設置用戶口令的失效期限
pwck     #檢查 '/etc/passwd' 的檔案格式和語法修正以及存在的使用者
grpck    #檢查 '/etc/passwd' 的檔案格式和語法修正以及存在的群組
newgrp group_name     #登陸進一個新的群組以改變新創建檔的預設群組


文件的許可權
使用 "+" 設置許可權，使用 "-" 用於取消

ls -lh    #顯示許可權
ls /tmp | pr -T5 -W$COLUMNS   #將終端劃分成5欄顯示
chmod ugo+rwx directory1      #設置目錄的所有人(u)、群組(g)以及其他人(o)以讀（r ）、寫(w)和執行(x)的許可權
chmod go-rwx directory1      #刪除群組(g)與其他人(o)對目錄的讀寫執行許可權
chown user1 file1            #改變一個檔的所有人屬性
chown -R user1 directory1    #改變一個目錄的所有人屬性並同時改變改目錄下所有檔的屬性
chgrp group1 file1          #改變檔的群組
chown user1:group1 file1     #改變一個檔的所有人和群組屬性
find / -perm -u+s           #羅列一個系統中所有使用了SUID控制的檔

chmod u+s /bin/file1        #設置一個二進位檔案的 SUID 位 - 運行該檔的用戶也被賦予和所有者同樣的許可權
chmod u-s /bin/file1        #禁用一個二進位檔案的 SUID位
chmod g+s /home/public      #設置一個目錄的SGID 位元 - 類似SUID ，不過這是針對目錄的
chmod g-s /home/public      #禁用一個目錄的 SGID 位元
chmod o+t /home/public      #設置一個檔的 STIKY 位 - 只允許合法所有人刪除檔
chmod o-t /home/public      #禁用一個目錄的 STIKY 位元


檔的特殊屬性
- 使用 "+" 設置許可權，使用 "-" 用於取消
chattr +a file1   #只允許以追加方式讀寫檔
chattr +c file1   #允許這個檔能被內核自動壓縮/解壓
chattr +d file1   #在進行檔案系統備份時，dump程式將忽略這個檔
chattr +i file1   #設置成不可變的檔，不能被刪除、修改、重命名或者連結
chattr +s file1   #允許一個檔被安全地刪除
chattr +S file1   #一旦應用程式對這個檔執行了寫操作，使系統立刻把修改的結果寫到磁片
chattr +u file1   #若檔被刪除，系統會允許你在以後恢復這個被刪除的檔
lsattr           #顯示特殊的屬性


打包和壓縮檔
bunzip2 file1.bz2   #解壓一個叫做 'file1.bz2'的文件
bzip2 file1         #壓縮一個叫做 'file1' 的檔
gunzip file1.gz     #解壓一個叫做 'file1.gz'的文件
gzip file1          #壓縮一個叫做 'file1'的檔
gzip -9 file1       #最大程度壓縮

rar a file1.rar test_file          #創建一個叫做 'file1.rar' 的包
rar a file1.rar file1 file2 dir1   #同時壓縮 'file1', 'file2' 以及目錄 'dir1'
rar x file1.rar     #解壓rar包
unrar x file1.rar   #解壓rar包

tar -cvf archive.tar file1   #創建一個非壓縮的 tarball
tar -cvf archive.tar file1 file2 dir1  #創建一個包含了 'file1', 'file2' 以及 'dir1'的檔案檔
tar -tf archive.tar    #顯示一個包中的內容
tar -xvf archive.tar   #釋放一個包
tar -xvf archive.tar -C /tmp     #將壓縮包釋放到 /tmp目錄下
tar -cvfj archive.tar.bz2 dir1   #創建一個bzip2格式的壓縮包
tar -jxvf archive.tar.bz2        #解壓一個bzip2格式的壓縮包
tar -cvfz archive.tar.gz dir1    #創建一個gzip格式的壓縮包
tar -zxvf archive.tar.gz         #解壓一個gzip格式的壓縮包

zip file1.zip file1    #創建一個zip格式的壓縮包
zip -r file1.zip file1 file2 dir1    #將幾個檔和目錄同時壓縮成一個zip格式的壓縮包
unzip file1.zip    #解壓一個zip格式壓縮包


RPM 包 - （Fedora, Redhat及類似系統）
rpm -ivh package.rpm    #安裝一個rpm包
rpm -ivh --nodeeps package.rpm   #安裝一個rpm包而忽略依賴關係警告
rpm -U package.rpm        #更新一個rpm包但不改變其設定檔
rpm -F package.rpm        #更新一個確定已經安裝的rpm包
rpm -e package_name.rpm   #刪除一個rpm包
rpm -qa      #顯示系統中所有已經安裝的rpm包
rpm -qa | grep httpd    #顯示所有名稱中包含 "httpd" 字樣的rpm包
rpm -qi package_name    #獲取一個已安裝包的特殊資訊
rpm -qg "System Environment/Daemons"     #顯示一個元件的rpm包
rpm -ql package_name       #顯示一個已經安裝的rpm包提供的檔列表
rpm -qc package_name       #顯示一個已經安裝的rpm包提供的設定檔列表
rpm -q package_name --whatrequires     #顯示與一個rpm包存在依賴關係的列表
rpm -q package_name --whatprovides    #顯示一個rpm包所占的體積
rpm -q package_name --scripts         #顯示在安裝/刪除期間所執行的腳本l
rpm -q package_name --changelog       #顯示一個rpm包的修改歷史
rpm -qf /etc/httpd/conf/httpd.conf    #確認所給的檔由哪個rpm包所提供
rpm -qp package.rpm -l    #顯示由一個尚未安裝的rpm包提供的檔列表
rpm --import /media/cdrom/RPM-GPG-KEY    #導入公開金鑰數位憑證
rpm --checksig package.rpm      #確認一個rpm包的完整性
rpm -qa gpg-pubkey      #確認已安裝的所有rpm包的完整性
rpm -V package_name     #檢查檔尺寸、 許可、類型、所有者、群組、MD5檢查以及最後修改時間
rpm -Va                 #檢查系統中所有已安裝的rpm包- 小心使用
rpm -Vp package.rpm     #確認一個rpm包還未安裝
rpm2cpio package.rpm | cpio --extract --make-directories *bin*   #從一個rpm包運行可執行檔
rpm -ivh /usr/src/redhat/RPMS/`arch`/package.rpm    #從一個rpm源碼安裝一個構建好的包
rpmbuild --rebuild package_name.src.rpm       #從一個rpm源碼構建一個 rpm 包


YUM 套裝軟體升級器 - （Fedora, RedHat及類似系統）
yum install package_name             #下載並安裝一個rpm包
yum localinstall package_name.rpm    #將安裝一個rpm包，使用你自己的軟體倉庫為你解決所有依賴關係
yum update package_name.rpm    #更新當前系統中所有安裝的rpm包
yum update package_name        #更新一個rpm包
yum remove package_name        #刪除一個rpm包
yum list                   #列出當前系統中安裝的所有包
yum search package_name     #在rpm倉庫中搜尋套裝軟體
yum clean packages          #清理rpm緩存刪除下載的包
yum clean headers           #刪除所有標頭檔
yum clean all                #刪除所有緩存的包和標頭檔


DEB 包 (Debian, Ubuntu 以及類似系統)
dpkg -i package.deb     #安裝/更新一個 deb 包
dpkg -r package_name    #從系統刪除一個 deb 包
dpkg -l                 #顯示系統中所有已經安裝的 deb 包
dpkg -l | grep httpd    #顯示所有名稱中包含 "httpd" 字樣的deb包
dpkg -s package_name    #獲得已經安裝在系統中一個特殊包的資訊
dpkg -L package_name    #顯示系統中已經安裝的一個deb包所提供的檔列表
dpkg --contents package.deb    #顯示尚未安裝的一個包所提供的檔列表
dpkg -S /bin/ping              #確認所給的檔由哪個deb包提供


APT 軟體工具 (Debian, Ubuntu 以及類似系統)
apt-get install package_name      #安裝/更新一個 deb 包
apt-cdrom install package_name    #從光碟安裝/更新一個 deb 包
apt-get update      #升級列表中的套裝軟體
apt-get upgrade     #升級所有已安裝的軟體
apt-get remove package_name     #從系統刪除一個deb包
apt-get check     #確認依賴的軟體倉庫正確
apt-get clean     #從下載的套裝軟體中清理緩存
apt-cache search searched-package    #返回包含所要搜索字串的套裝軟體名稱


查看檔內容
cat file1      #從第一個位元組開始正向查看檔的內容
tac file1      #從最後一行開始反向查看一個檔的內容
more file1     #查看一個長檔的內容
less file1     #類似於 'more' 命令，但是它允許在檔中和正向操作一樣的反向操作
head -2 file1    #查看一個檔的前兩行
tail -2 file1    #查看一個檔的最後兩行
tail -f /var/log/messages     #即時查看被添加到一個檔中的內容


文本處理
cat file1 file2 ... | command <> file1_in.txt_or_file1_out.txt general syntax for text manipulation using PIPE, STDIN and STDOUT
cat file1 | command( sed, grep, awk, grep, etc...) > result.txt 
#合併一個檔的詳細說明文本，並將簡介寫入一個新檔中
cat file1 | command( sed, grep, awk, grep, etc...) >> result.txt 

#合併一個檔的詳細說明文本，並將簡介寫入一個已有的檔中

grep Aug /var/log/messages     #在檔 '/var/log/messages'中查找關鍵字"Aug"
grep ^Aug /var/log/messages    #在檔 '/var/log/messages'中查找以"Aug"開始的詞彙
grep [0-9] /var/log/messages   #選擇 '/var/log/messages' 檔中所有包含數位的行
grep Aug -R /var/log/*         #在目錄 '/var/log' 及隨後的目錄中搜索字串"Aug"

sed 's/stringa1/stringa2/g' example.txt 

#將example.txt文件中的 "string1" 替換成 "string2"
sed '/^$/d' example.txt           #從example.txt檔中刪除所有空白行
sed '/ *#/d; /^$/d' example.txt   #從example.txt檔中刪除所有注釋和空白行
echo 'esempio' | tr '[:lower:]' '[:upper:]'    #合併上下儲存格內容
sed -e '1d' result.txt          #從文件example.txt 中排除第一行
sed -n '/stringa1/p'            #查看只包含詞彙 "string1"的行
sed -e 's/ *$//' example.txt    #刪除每一行最後的空白字元
sed -e 's/stringa1//g' example.txt  


#從文檔中只刪除詞彙 "string1" 並保留剩餘全部
sed -n '1,5p;5q' example.txt     #查看從第一行到第5行內容
sed -n '5p;5q' example.txt       #查看第5行
sed -e 's/00*/0/g' example.txt   #用單個零替換多個零
cat -n file1       #標示文件的行數
cat example.txt | awk 'NR%2==1'      #刪除example.txt檔中的所有偶數行

echo a b c | awk '{print $1}'        #查看一行第一欄
echo a b c | awk '{print $1,$3}'     #查看一行的第一和第三欄
paste file1 file2           #合併兩個檔或兩欄的內容
paste -d '+' file1 file2    #合併兩個檔或兩欄的內容，中間用"+"區分
sort file1 file2              #排序兩個檔的內容
sort file1 file2 | uniq       #取出兩個檔的並集(重複的行只保留一份)
sort file1 file2 | uniq -u    #刪除交集，留下其他的行
sort file1 file2 | uniq -d    #取出兩個檔的交集(只留下同時存在於兩個檔中的檔)
comm -1 file1 file2    #比較兩個檔的內容只刪除 'file1' 所包含的內容
comm -2 file1 file2    #比較兩個檔的內容只刪除 'file2' 所包含的內容
comm -3 file1 file2    #比較兩個檔的內容只刪除兩個檔共有的部分


字元設置和檔案格式轉換
dos2unix filedos.txt fileunix.txt      #將一個文字檔的格式從MSDOS轉換成UNIX
unix2dos fileunix.txt filedos.txt      #將一個文字檔的格式從UNIX轉換成MSDOS
recode ..HTML < page.txt > page.html   #將一個文字檔轉換成html
recode -l | more                       #顯示所有允許的轉換格式


檔案系統分析
badblocks -v /dev/hda1    #檢查磁片hda1上的壞磁塊
fsck /dev/hda1            #修復/檢查hda1磁片上linux檔案系統的完整性
fsck.ext2 /dev/hda1       #修復/檢查hda1磁片上ext2檔案系統的完整性

e2fsck /dev/hda1          #修復/檢查hda1磁片上ext2檔案系統的完整性
e2fsck -j /dev/hda1       #修復/檢查hda1磁片上ext3檔案系統的完整性

fsck.ext3 /dev/hda1       #修復/檢查hda1磁片上ext3檔案系統的完整性
fsck.vfat /dev/hda1       #修復/檢查hda1磁片上fat檔案系統的完整性
fsck.msdos /dev/hda1      #修復/檢查hda1磁片上dos檔案系統的完整性
dosfsck /dev/hda1         #修復/檢查hda1磁片上dos檔案系統的完整性


初始化一個檔案系統
mkfs /dev/hda1        #在hda1分區創建一個檔案系統
mke2fs /dev/hda1      #在hda1分區創建一個linux ext2的檔案系統
mke2fs -j /dev/hda1   #在hda1分區創建一個linux ext3(日誌型)的檔案系統
mkfs -t vfat 32 -F /dev/hda1   #創建一個 FAT32 檔案系統
fdformat -n /dev/fd0           #格式化一個軟碟
mkswap /dev/hda3               #創建一個swap檔案系統


SWAP檔案系統
mkswap /dev/hda3             #創建一個swap檔案系統
swapon /dev/hda3             #啟用一個新的swap檔案系統
swapon /dev/hda2 /dev/hdb3   #啟用兩個swap分區



備份
dump -0aj -f /tmp/home0.bak /home    #製作一個 '/home' 目錄的完整備份
dump -1aj -f /tmp/home0.bak /home    #製作一個 '/home' 目錄的互動式備份
restore -if /tmp/home0.bak          #還原一個互動式備份
rsync -rogpav --delete /home /tmp    #同步兩邊的目錄
rsync -rogpav -e ssh --delete /home ip_address:/tmp           #通過SSH通道rsync
rsync -az -e ssh --delete ip_addr:/home/public /home/local    #通過ssh和壓縮將一個遠端目錄同步到本地目錄
rsync -az -e ssh --delete /home/local ip_addr:/home/public    #通過ssh和壓縮將本地目錄同步到遠端目錄
dd bs=1M if=/dev/hda | gzip | ssh user@ip_addr 'dd of=hda.gz'  


#通過ssh在遠端主機上執行一次備份本地磁片的操作
dd if=/dev/sda of=/tmp/file1 
#備份磁片內容到一個檔
tar -Puf backup.tar /home/user 執行一次對 '/home/user' 
#目錄的互動式備份操作
( cd /tmp/local/ && tar c . ) | ssh -C user@ip_addr 'cd /home/share/ && tar x -p' 
#通過ssh在遠端目錄中複製一個目錄內容
( tar c /home ) | ssh -C user@ip_addr 'cd /home/backup-home && tar x -p' 
#通過ssh在遠端目錄中複製一個本地目錄
tar cf - . | (cd /tmp/backup ; tar xf - ) 
#本地將一個目錄複寫到另一個地方，保留原有許可權及連結
find /home/user1 -name '*.txt' | xargs cp -av --target-directory=/home/backup/ --parents 
#從一個目錄查找並複製所有以 '.txt' 結尾的檔到另一個目錄
find /var/log -name '*.log' | tar cv --files-from=- | bzip2 > log.tar.bz2 
#查找所有以 '.log' 結尾的檔並做成一個bzip包
dd if=/dev/hda of=/dev/fd0 bs=512 count=1 
#做一個將 MBR (Master Boot Record)內容複製到軟碟的動作
dd if=/dev/fd0 of=/dev/hda bs=512 count=1 
#從已經保存到軟碟的備份中恢復MBR內容


光碟
cdrecord -v gracetime=2 dev=/dev/cdrom -eject blank=fast -force 
#清空一個可複寫的光碟內容
mkisofs /dev/cdrom > cd.iso             #在磁片上創建一個光碟的iso鏡像檔
mkisofs /dev/cdrom | gzip > cd_iso.gz    #在磁片上創建一個壓縮了的光碟iso鏡像檔
mkisofs -J -allow-leading-dots -R -V "Label CD" -iso-level 4 -o ./cd.iso data_cd 

#創建一個目錄的iso鏡像檔
cdrecord -v dev=/dev/cdrom cd.iso               #燒錄一個ISO鏡像檔
gzip -dc cd_iso.gz | cdrecord dev=/dev/cdrom -  #燒錄一個壓縮了的ISO鏡像檔
mount -o loop cd.iso /mnt/iso                  #掛載一個ISO鏡像檔
cd-paranoia -B             #從一個CD光碟轉錄音軌到 wav 檔中
cd-paranoia -- "-3"        #從一個CD光碟轉錄音軌到 wav 檔中（參數-3）
cdrecord --scanbus         #掃描匯流排以識別scsi通道
dd if=/dev/hdc | md5sum    #校驗一個設備的md5sum編碼，例如一張 CD


網路 - （乙太網和WIFI無線）
ifconfig eth0    #顯示一個乙太網卡的配置
ifup eth0        #啟用一個 'eth0' 網路設備
ifdown eth0      #禁用一個 'eth0' 網路設備
ifconfig eth0 192.168.1.1 netmask 255.255.255.0     #控制IP位址
ifconfig eth0 promisc     #設置 'eth0' 成混雜模式以嗅探資料包 (sniffing)
dhclient eth0            #以dhcp模式啟用 'eth0'
route -n    #查看路由表
route add -net 0/0 gw IP_Gateway    #配置預設閘道器
route add -net 192.168.0.0 netmask 255.255.0.0 gw 192.168.1.1 
#配置靜態路由到達網路'192.168.0.0/16'
route del 0/0 gw IP_gateway        #刪除靜態路由
hostname #查看機器名
host www.example.com       #把一個主機名稱解析到一個網際位址或把一個網際位址解析到一個主機名稱。
nslookup www.example.com   #用於查詢DNS的記錄，查看功能變數名稱解析是否正常，在網路故障的時候用來診斷網路問題。
ip link show            #查看網卡資訊
mii-tool                #用於查看、管理介質的網路介面的狀態
ethtool                 #用於查詢和設置網卡配置
netstat -tupl           #用於顯示TCP/UDP的狀態資訊
tcpdump tcp port 80     #顯示所有http協定的流量

```
