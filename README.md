# **1 Install WSL**

Please refer to below link for details:

> https://learn.microsoft.com/en-us/windows/wsl/install

Brief summary of the relevant commands for WSL installation using windows command line:

1. Install WSL in windows command line:

    > wsl --install

2. By default, WSL2 will be installed but you can change the version using below commands, replacing <Version#> with either 1 or 2

    > wsl --set-default-version <Version#>

3. Command to list all the linux distribution installed on WSL

    > wsl -l -v

4. Command to list all the linux distribution available to download and installed

    > wsl -l -o
    
5. Command to install additional linux distribution
    > wsl --install -d <Distribution Name>

6. Command to switch to a different Linux distribution for WSL
    > wsl --setdefault <DistributionName>

7. Command to update WSL
   > wsl --update

8. Command to restart WSL
    > wsl --shutdown

Once WSL is installed, you will see convenient entries in your windows start menu that you can use to log in to the Linux distributions insatlled.

![image](https://user-images.githubusercontent.com/115331932/236579305-cdfca349-14d9-42ee-bf0d-ae2b5715109f.png)

# **2 Install VScode for development on WSL**

Please refer to below link for details:

https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode

Brief summary:

1. Get [VS Code](https://code.visualstudio.com/download)
2. Install the [Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) - this is essential for accessing WSL folder from VScode on windows
3. log into your Linux distribution to update & install wget:
    > sudo apt-get update
    > sudo apt-get install wget ca-certificates
4. Open VScode, press "ctrl+shift+p", and enter below commands
![image](https://user-images.githubusercontent.com/115331932/236580652-194c447a-4cd2-4173-a724-4efcf228f349.png)
6. Then VSCode will connect to WSL and you will be able to:
    1. Develop Linux application in WSL using VSCode on windows
    2. Access a Linux terminal in VScode
        ![image](https://user-images.githubusercontent.com/115331932/236581695-f1db9bf6-2662-4994-8390-9a42d22e7794.png)
        ![image](https://user-images.githubusercontent.com/115331932/236581720-0391ed4a-ebcb-4e3a-ac93-00d9b8111fc0.png)

    3. Many other things I have no idea at this point...

# 3 Enables Linux GUI applications
###  This is one of the best update for WSL to enable users running Linux apps like other windows apps! By enabling this, we can edit .ui file in WSL2 distribution (e.g. Ubuntu) from VScode installed on windows

Please refer to details from below link:
https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps

Most important components from my point of view:

1. Install GPU drivers:
    [Intel GPU driver](https://www.intel.com/content/www/us/en/download/19344/intel-graphics-windows-dch-drivers.html)
    [AMD GPU driver](https://www.amd.com/en/support)
    [NVIDIA GPU driver](https://www.nvidia.com/Download/index.aspx?lang=en-us)

    You may need to restart WSL to let the drivers take effect. 
2. Install Google Chrome for Linux - this would make it much easier to download the online installer for Qt instead of installing Qt from terminal
    1. Open a terminal in VScode that was connected to WSL
    2. In terminal, execute below commands:
        > cd /tmp
        > sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
        > sudo dpkg -i google-chrome-stable_current_amd64.deb
        > sudo apt install --fix-broken -y
        > sudo dpkg -i google-chrome-stable_current_amd64.deb
        
    3. Test if chrome was installed successfully
        > google-chrome

3. After you have installed the Linux apps in the above link, you should be able to launch the apps using the shortcuts in your start menu like below

    ![image](https://user-images.githubusercontent.com/115331932/236586355-8dfa9829-fc44-4e64-ae42-359ea93f89da.png)
 
4. In addition, any app ( QtCreator/Google-Chrome/etc... ) installed on Ubuntu (or other Linux OS) can be launched from the terminal opened in VScode connected to WSL

# 4. Install Qt on Ubuntu

In progress
 
