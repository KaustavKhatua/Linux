# Linux
## How to install Google-Chrome in Ubuntu 20.04
Follow steps listed in https://linuxize.com/post/how-to-install-google-chrome-web-browser-on-ubuntu-20-04/

## How to install Visual Studio Code in Ubuntu 20.04
Follow the steps listed in https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/   . Ignore the line after sudo apt update

## How to install Python packages in Ubuntu 20.04
For the first time when I tried to install a package using the command pip3 install numpy. It gave error and said pip3 can not be found but can be installed using sudo apt install python3-pip. But I searched Google and confirmed the command (sudo apt install python3-pip) from this link: https://linuxize.com/post/how-to-install-pip-on-ubuntu-20.04/    . So, pip3 can be installed using these two commands:
```
sudo apt update
sudo apt install python3-pip
```
Now, in my case there was some warning showing:
```
Collecting numpy
  Downloading numpy-1.20.3-cp38-cp38-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (15.4 MB)
     |████████████████████████████████| 15.4 MB 3.2 MB/s 
Installing collected packages: numpy
  WARNING: The scripts f2py, f2py3 and f2py3.8 are installed in '/home/kaustav/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed numpy-1.20.3
```
So, I opened home in File Manager (default place where File Manager opens), enabled the show hidden files option and opened the .bashrc file and at the end of the file in a new line I wrote (ie. appended to the file) according to this link https://techpiezo.com/python/install-python-packages-using-pip-in-ubuntu/   (last paragraph):
```
export PATH=/home/kasustav/.local/bin:$PATH
```
ie. the format is:`
```
export PATH=<folder name shown in the warning>:$PATH
```
Now, if I again install some other package like:
```
pip3 install pandas
```
No, warning comes.
Also, other advantage of adding this folder to PATH is that, when I open Visual Studio Code I do not have to select interpreter, previously I had to do it, everytime I open Visual Studio Code.

## Difference between apt and apt-get
apt is newer method and apt-get is older method. See Conclusion portion from this link to get the idea. https://itsfoss.com/apt-vs-apt-get-difference/


