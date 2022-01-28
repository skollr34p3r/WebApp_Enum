# WebApp_Enum

This WebApp Enumeration script relies on several things. Firstly, in order to install the tools it uses, you need go.

The version of go is important as the creators of the necessary tools have not updated their installation instructions to work with the latest version of go (at the time of writing, the latest version is 1.17.6). The use of "go get" to install packages is deprecated as of go version 1.17 according to: https://go.dev/doc/go-get-install-deprecation

Because of this, we need to install a previous version of go in order to install the necessary tools. I have found that version 1.15.9 is working great in Kali 2021.4. To install an older version of Go, visit this site and download the desired version: https://go.dev/dl/

I downloaded the "go1.15.9.linux-amd64.tar.gz" file, then followed the insrtuctions for Linux here to install it: https://go.dev/doc/install

If you installed using the downloads page from the Official Go website, the download is likely in your ~/Downloads directory. Sudo su to become root (if not already running as root). Change to the directory where yourgo tar.gz file is in then execute the following commands:

`rm -rf /usr/local/go && tar -C /usr/local -xzf go1.17.6.linux-amd64.tar.gz`

`export PATH=$PATH:/usr/local/go/bin`

`export PATH="$PATH:$HOME/go/bin"`

This should properly install a previous version of Go on the system. You can check it by typing "go version".

If there are any issues or you see a newer version of Go reported when chekcing the version, you may need to use apt remove to get rid of the newer version of golang and golang-go. Once the "go version" command resutls with the correct version in the output, and Go is added to your PATH properly, you should be ready to install the required tools for the script.

## Required tools:
- 1- AssetFinder (https://github.com/tomnomnom/assetfinder)
- 2- SubJack (https://github.com/haccer/subjack)
- 3- WaybackURLs (https://github.com/tomnomnom/waybackurls)
- 4- httprobe (https://github.com/tomnomnom/httprobe)
- 5- Nmap (installed by default in Kali)

## Installation
To install the required tools using Go in Kali (commands taken from installation instructions on each repo):
go get -u github.com/tomnomnom/assetfinder
go get github.com/haccer/subjack
go get github.com/tomnomnom/waybackurls
go get -u github.com/tomnomnom/httprobe

With a compatible version of Go installed, and all 4 tools installed using Go, you should be ready to run the WebApp_Enumeration script.
You can copy the script to a folder in your PATH with execution permissions (I used /usr/local/bin) in order to enable it to be executed anywhere.

## Run the script
WebApp_Enumeration.sh [domain] 
example: WebApp_Enumeration.sh google.com

Disclaimer: Only run this on domains within scope of your engagement.
