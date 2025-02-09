So, you're trying to build a j2me application in 2025. I question your motives but heres the most up to guide on the internet for it.

## Install a 32 bit JDK
Extract [this](https://files.mercurywork.shop/rafflesia/java-8-openjdk-32.tar.gz) tarball file and move its contents into /usr/lib/jvm/java-8-openjdk-32. 
Set it as your default jre with `sudo archlinux-java set java-8-openjdk-32`

# Download sun-wtk from the AUR
* Self explanatory

# Download these plugins 
1. Download [*this*](https://files.mercurywork.shop/rafflesia/oracle-jmesdk-3-4-rr-nb-plugins.zip) zip file
2. extract this file
3. You'll use this later

## Installing Mobility
Install Netbeans 8.2. This requires an oracle account so I posted it here.
1. Run the installer I linked [here](https://files.mercurywork.shop/rafflesia/netbeans-8.2-linux.sh)
2. When asked for jvm, use the java-8-openjdk-32 you installed
3. finish installation
4. Open tools > plugins
5. Install the **Mobility** Plugin

## Installing the other plugins you need (Painful)
1. Go back to Tools > Plugins
2. Open the Downloaded tab
3. click Add Plugins
4. Select all the plugins from the zip file you used earlier. Some of them will give you an error. unselect these and try again until you have all the plugins you *can* install

## Setting the platform
1. Go back to the main page and select Tools > Java Platforms
2. Click `Add Platform`
3. Select Platform Type: Java ME CLDC Emulators
4. Select `/opt/sun-wtk`
5. Proceed and finish

## Creating your first project
* The examples plugin didn't install for you most likely, but I have extracted the Samples and put them in `Samples/` of this repo
* You can also just create a new project (Box icon), select Java ME, and have your fun that way

