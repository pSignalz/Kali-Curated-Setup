# Kali 2022.2 : Setup

<br>

> ## NOTES:
>>  - `/opt` folder is great to store downloaded/sysLinked tools
>>
>>  - `apt` is for user level
>>
>>  - `apt-get` is for system level
>>
>>  - `apt update` (`apt-get`) updates packages
>>
>>  - `apt upgrade` (`apt-get`) upgrades packages
>>
>>  - `apt full-upgrade` (`apt-get`) upgarades packages and removes old packages when neeeded to upgrade
>>
>>  - `sudo updatedb` (`apt-get`) update db of locate command
>>
>>  - `apt remove` (`apt-get`) just uninstall
>>
>>  - `apt autoremove` (`apt-get`) remove all no longer needed files
>>
>>  - `apt purge` (`apt-get`) remove and delete all files
>>
>>  - `tar -xvf` extract tar.gz files with verbose

<br>

> ## MacBook Wifi (2013):
>
> Broadcom WL Driver: [Driver](https://tutorialforlinux.com/2020/02/26/step-by-step-broadcom-wl-driver-kali-2020-gnu-linux-installation-guide/2/)

<br>

> ## INITIAL UPDATES
>
> - 1 - Update `/etc/apt/source.list`
> - 2 - Uncomment source already there
>
>> **Add Sources:**
>> - `deb http://deb.debian.org/debian/ bullseye main contrib non-free`
>> - `deb-src http://deb.debian.org/debian/ bullseye main`
>> - `deb http://security.debian.org/debian-security bullseye-security main`
>> - `deb-src http://security.debian.org/debian-security bullseye-security main`
>> - `deb http://deb.debian.org/debian/ bullseye-updates main`
>> - `deb-src http://deb.debian.org/debian/ bullseye-updates main`
> 
>> 		sudo apt update
>> 		sudo apt full-upgrade -y
>> 		sudo apt-get install git python3 golang
>
> **Install pimpmykali:**	
> [Repo: https://github.com/Dewalt-arch/pimpmykali](https://github.com/Dewalt-arch/pimpmykali)
>
>>			rm -rf pimpmykali/
>>			git clone https://github.com/Dewalt-arch/pimpmykali
>>			cd pimpmykali
>>			sudo ./pimpmykali.sh
>>			N   **To run new VM Scan
		
<br>

> ## Chrome:
>> 		sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
>> 		sudo apt install ./google-chrome-stable_current_amd64.deb

<br>

> ## BurpSuite:
>> **FireFox** → Settings   →   Extensions  →  Foxy Proxy
>>
>> **FoxyProxy** → Options  →  Add Proxy  → 
>>>	**Burpsuite** 	HTTP 127.0.0.1 : 8080
>>>
>>>	**Postman** 	HTTP 127.0.0.1 : 5555
>>
>> [Certificate:	http://burpsuite](http://burpsuite)
>>>	 With **BurpSuite** running:
>>>
>>>	**FireFox** → Settings → Security → Certificates → Authorities → Import
>>>
>>>	**Chrome** → Settings → Priv/Sec → Security → Certificates → Authorities → Import
>
> ## BURP COLLABORATOR **ALTERNATIVES**:
>>
>> **InteractSH**
>>> - [blog - https://blog.projectdiscovery.io/interactsh-release/](https://blog.projectdiscovery.io/interactsh-release/)
>>> - [repo - https://github.com/projectdiscovery/interactsh](https://github.com/projectdiscovery/interactsh)
>>
>> **DNS Observer**
>>> - [repo - https://github.com/allyomalley/dnsobserver](https://github.com/allyomalley/dnsobserver)
>>
>> **DNS Bin**
>>> - [repo - https://github.com/ettic-team/dnsbin](https://github.com/ettic-team/dnsbin)
>>
>> **Malidate**
>>> - [repo - https://github.com/redfast00/malidate](https://github.com/redfast00/malidate)
>>
>> **Request Bin**
>>> - [repo - https://requestbin.net/](https://requestbin.net/)
>>
>> **BeeCeptor**
>>> - [repo - https://beeceptor.com/](https://beeceptor.com/)
>>
>> **YoutubeVid**
>>> - [repo - https://www.youtube.com/watch?v=hLAuacX3CbQ&feature=youtu.be](https://www.youtube.com/watch?v=hLAuacX3CbQ&feature=youtu.be)

<br>

> ## Amass:
>
>>		mkdir $HOME/.config/amass
>>		curl https://raw.githubusercontent.com/OWASP/Amass/master/config/config.ini > $HOME/.config/amass/config.ini
>
>> Add [api keys : https://github.com/OWASP/Amass](https://github.com/OWASP/Amass) → sourcelist

<br>

> ## ExifTool:
>
> [Download Tool https://exiftool.org/install.html#Unix](https://exiftool.org/install.html#Unix)
>	
> **Install:**
>> Copy (or Extract then Copy) Tool to `/opt/` folder 
>>
>>		tar -xvf Image-ExifTool-12.42
>>		sudo cp Image-ExifTool-12.42 /opt/
>>		cd /opt/Image-ExifTool-12.42
>>		perl Makefile.PL
>>		make test
>>		sudo make install
>
> **Uninstall:**
>>
>>		cd /opt/Image-ExifTool
>>		sudo make unistall
					
<br>
	
> ## KiteRunner:
>
> [Repo](https://github.com/assetnote/kiterunner.git)
>
>> Copy Kitrunner to `/opt` folder
>>
>>		git clone https://github.com/assetnote/kiterunner.git
>>		cd kitrunner
>>		make build
>>		sudo ln -s $(pwd)/dist/kr /usr/local/bin/kr
					
<br>
							
> ## DOCKER:
>
> [**Kali Install Instructions**](https://www.kali.org/docs/containers/installing-docker-on-kali/)
>
> [**Docker: Kali Install Instructions**](https://docs.docker.com/engine/install/debian/)
>
>>  Show current containers:
>>
>>		docker container ls -a
					
<br>

> ## VirtualBox: (May be more Mac Friendly)
>
> [Virtualbox-Host Install](https://www.kali.org/docs/virtualization/install-virtualbox-host/)
					
<br>

> ## VMWare:
>
> [VMWare Install Instructions](https://www.kali.org/docs/virtualization/install-vmware-host/\)
>
>> **Troubleshooting step at bottom of page:**
>>
>> Follow the instructions to install kernel support
										
<br>

> ## OWASP-ZAP:
>
> **Configure proxy:**
>> [Instructions](https://www.zaproxy.org/docs/desktop/start/proxies/)
>
> **Server Certificate:**
>> [Install Server Certificate](https://www.zaproxy.org/docs/desktop/addons/network/options/servercertificates/)
>
> **Setup w/ Foxy Proxy:**
>> [Foxy Proxy Setup](https://www.thedutchhacker.com/configure-owasp-zap-with-firefox/)
>
> **Open Zap** 
>
>> Tools → Options → Local Proxy:
>>
>>>			IP: 127.0.0.1		Port: 8080 
>>
>>	Dynamic SSL Certificate		
>>>		Save
>>>		dir: 	/etc/ca-certificates/update.d
>>
>>	Open Firefox Settings → Privacy and Security → Open Certificates:
>>>		Import owasp_zap_certifcate
>
>	Set Foxy Proxy to use ZAP proxy
					
<br>

> ## Juice-Shop:
>
>>		docker pull bkimminich/juice-shop
>>		docker run --rm -p 80:3000 bkimminich/juice-shop
					
<br>

> ## PIXI:
>
>>		git clone https://github.com/DevStop/Pixi.git
>>		cd Pixi
>>		sudo docker-compose up
					
<br>
	
> ## DVGA:
>
>>		sudo docker pull dolevf/dvga
>>		docker run -t -p 5000:5000 -e WEB_HOST=0.0.0.0 dolevf/dvga
					
<br>

> ## crAPI:
>
>>		git clone https://github.com/OWASP/crAPI
>>		cd crAPI			
>>		sudo docker-compose up
>
> **Follow instructions for Linux Machines & Docker Compose**

<br>

> ## PimpMyKali:
>
> [Instructions](https://github.com/Dewalt-arch/pimpmykali)
>
>>		rm -rf pimpmykali/
>>		git clone https://github.com/Dewalt-arch/pimpmykali
>>		cd pimpmykali
>>		sudo ./pimpmykali.sh
>>
>>> **For a new kali vm, run menu option N**


<br>

> ## Visual Studio Code:
> 
> [Instructions](https://code.visualstudio.com/docs/setup/linux)
>>		sudo apt-get install wget gpg
>>		wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
>>		sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
>>		sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
>>		rm -f packages.microsoft.gpg
>>		sudo apt update
>>		sudo apt install apt-transport-https
>>		sudo apt update
>>		sudo apt install code

<br>

> ## BurpSuite (update):
>
> [Download Update](https://portswigger.net/burp/communitydownload)
>> Download linux64
>
>>		cd ~/Downloads/
>>		sudo chmod +x burpsuite_...
>>		sudo ./buprsuite_...

<br>

> ## TimeShift:
>
> [Instructions](https://teejeetech.in/timeshift/)
>>		sudo apt-get update
>>		sudo apt-get install timeshift
>
> **TimeShift Create Image:**
>>
>> Insert USB Drive
>>
>> Open Timeshift
>>
>> Select rSync
>>
>> Select USB Drive
>>
>> Accept exclude `Home/` and `Root/` Dirs
>>
>> Finish Setup
>>
>> Create Image
>
> **Make Image:**
>>
>> Insert USB Drive
>>
>> Open USB Directory - Enter Password
>>
>> Open TimeShift - Enter Password
>>
>> Select Create
>>
> **LUKS Encrypted USB (Do before removing usb)**
>>
>>		List usb devices			lsusb
>>		Open File Directory			Select USB Drive --> Right Click and Unmount
>>									 --> Right Click and Eject
>>		List usb devices			lsusb
>>		Show mounted disks			sudo fdisk -l
>>		Unmount encrypted usb drive		sudo umount /dev/mapper/<id>


<br>

> ## Brave Browser:
>
> [Instructions](https://brave.com/linux/)
>
>>		sudo apt install apt-transport-https curl
>>		sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/	brave-browser-archive-keyring.gpg
>>		echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
>>		sudo apt update
>>		sudo apt install brave-browser

<br>

> ## Terminator
>
> [Documentation](https://terminator-gtk3.readthedocs.io/en/latest/)
>
>>		sudo apt update
>>		sudo apt install terminator
