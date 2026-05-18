## If you happen to use Windows (and don't want to use WSL) please:
### Java
0. Check if Java is installed. Open cmd, type ```java -version```. If it returns some version, you can skip installing Java. If not,
1. [get an up-to-date Java Runtime Environment (JRE) if you haven't already](https://www.java.com/en/download/). You'll probably need "Windows Offline (64-bit)".
2. Just run the installer after downloading.
### Apache Ant
0. Check if Ant is installed. Open cmd, type ```ant -version```. If it returns some version, you can skip installing Ant. If not,
1. [download Apache Ant (zip)](https://ant.apache.org/bindownload.cgi) (Yes, the page looks confusing. Download the "…bin.zip" file.)
2. unzip the file to the ```C:\Pogram Files\``` folder. If Windows for some reason decides that you shouldn't be able to access this folder on your computer, try to create/use something like ```C:\Users\<YourUsernameHere>\bin\```
3. Open *Edit environment variables for your account* by simply searching for it via the search option of the Windows menu. (No, this isn't the same as "Edit the system environment variables".)
4. Find the ```PATH``` variable in the list. Select it and click ```edit```.
5. Choose *new* and paste the path of the ```bin``` folder inside the Ant folder you just unzipped. It likely looks something like this: ```C:\Program Files\apache-ant-1.10.15-bin\apache-ant-1.10.15\bin```
6. Open a new cmd terminal.
7. Run ```ant -v``` to check if it worked. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means everything works as expected.


## If you’re using Linux
Try ```ant -v```, it should already be installed. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist!Build failed``` This actually means everything works as expected. If Ant isn’t installed for some reason, get it via apt, pacman, etc.


## If you’re using macOS
Maybe it's already installed; maybe it isn't.

1. Open your terminal by searching for "Terminal" via Spotlight (Cmd + Space).
2. Type ```ant -v``` and hit enter. Don’t worry if it returns something like: ```Buildfile: build.xml does not exist! Build failed``` This actually means everything works as expected.
3. If it isn't installed:
	- Check if Homebrew is installed by typing ```brew --version```.
	- If it isn't, you can install it by following the instructions at https://brew.sh/.
	- When Homebrew is installed, install Ant: ```brew install ant```.
	- After installation, run ```ant -v``` again to verify the installation.
