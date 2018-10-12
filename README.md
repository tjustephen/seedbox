# seedbox
A guide to set up a seedbox:

**1. first to test the seedbox**  
  
    wget -qO- bench.sh | bash

**2.1 Install BBR**  
  
    wget --no-check-certificate -qO 'BBR.sh' 'https://moeclub.org/attachment/LinuxShell/BBR.sh' && chmod a+x BBR.sh && bash BBR.sh -f  
  
**2.2 Install 魔改bbr（option）** 
      
    wget --no-check-certificate -qO 'BBR_POWERED.sh' 'https://moeclub.org/attachment/LinuxShell/BBR_POWERED.sh' && chmod a+x BBR_POWERED.sh && bash BBR_POWERED.sh  
  
**3. Install Inexistence**

    bash -c "$(wget --no-check-certificate -qO- https://github.com/Aniverse/inexistence/raw/master/inexistence.sh)"  
  or
  
    wget --no-check-certificate -qO inexistence.sh https://github.com/Aniverse/inexistence/raw/master/inexistence.sh & bash inexistence.sh

  or 无交互  #自行添加用户名密码
  
    wget --no-check-certificate -qO inexistence.sh https://github.com/Aniverse/inexistence/raw/master/inexistence.sh & bash inexistence.sh -u <username> -p <password> --apt-yes --mt-max --de 1.3.15 --qb 4.1.3 --rt 0.9.6 --tr no --flood-no --rdp-no --wine-no --tools-yes --flexget-yes --rclone-yes --bbr-no --tweaks-yes -y

**4. rclone**

    rclone config  #略去具体过程
rclone mount

    wget https://www.moerats.com/usr/shell/rcloned && nano rcloned
 修改以下内容：
 
    NAME=""  #rclone name名，及配置时输入的Name
    REMOTE=''  #远程文件夹，Google Drive网盘里的挂载的一个文件夹
    LOCAL=''  #挂载地址，VPS本地挂载目录
    
    #设置自启
    mv rcloned /etc/init.d/rcloned
    chmod +x /etc/init.d/rcloned
    update-rc.d -f rcloned defaults
    bash /etc/init.d/rcloned start
