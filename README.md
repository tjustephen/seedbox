# seedbox
A guide to set up a seedbox:

1. first to test the seedbox  
  wget -qO- bench.sh | bash

2. Install BBR  
    wget --no-check-certificate -qO 'BBR.sh' 'https://moeclub.org/attachment/LinuxShell/BBR.sh' && chmod a+x BBR.sh && bash BBR.sh -f  
    
    Install 魔改bbr（option） 
      
    wget --no-check-certificate -qO 'BBR_POWERED.sh' 'https://moeclub.org/attachment/LinuxShell/BBR_POWERED.sh' && chmod a+x BBR_POWERED.sh && bash BBR_POWERED.sh  
  
3. Install Inexistence  
  bash -c "$(wget --no-check-certificate -qO- https://github.com/Aniverse/inexistence/raw/master/inexistence.sh)"  
  or  
  wget --no-check-certificate -qO inexistence.sh https://github.com/Aniverse/inexistence/raw/master/inexistence.sh & 
bash inexistence.sh  
  or无交互  #自行添加用户名密码  
  wget --no-check-certificate -qO inexistence.sh https://github.com/Aniverse/inexistence/raw/master/inexistence.sh & 
bash inexistence.sh -u <username> -p <password> --apt-yes --mt-max --de 1.3.15 --qb 4.1.3 --rt 0.9.6 --tr no --flood-no --rdp-no --wine-no --tools-yes --flexget-yes --rclone-yes --bbr-no --tweaks-yes -y
