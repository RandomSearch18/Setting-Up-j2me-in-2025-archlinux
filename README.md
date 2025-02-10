# Welcome hackclub retrospect refugees!
If you're not from hackclub and you're trying to build a j2me application in 2025, I question your motives but heres the most up to guide on the internet for it. 

## Install a 32 bit JDK
Extract [this](https://files.mercurywork.shop/rafflesia/java-8-openjdk-32.tar.gz) tarball file and move its contents into /usr/lib/jvm/java-8-openjdk-32. 
Set it as your default jre with `sudo archlinux-java set java-8-openjdk-32`

# Enable Multilib
* I don't know exactly what you need installed but libraries reported to me include
* lib32-libxtst
* lib32-libxrender

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

## Installing the other plugins you need
1. Go back to Tools > Plugins
2. Open the Downloaded tab
3. click Add Plugins
4. Select all the plugins from the zip file you used earlier except for the following:
    * Java ME SDK CPU Profiler Snapshot Viewer
    * Profiler (Java ME Projects Support)
    * Profiler Ant Support
    * Toolbar core
    * Java ME SDK Welcome Screen.
5. Install these plugins

## Setting the platform
1. Go back to the main page and select Tools > Java Platforms
2. Click `Add Platform`
3. Select Platform Type: Java ME CLDC Emulators
4. Select `/opt/sun-wtk`
5. Proceed and finish
### Note:
If this fails, try setting your WTK_JRE_PATH="/usr/lib/jvm/java-8-openjdk-32/" environment variable, and then launching netbeans. If this works, you can add it to /etc/environment

## Creating your first project
* The examples plugin didn't install for you most likely, but I have extracted the Samples and put them in `Samples/` of this repo
* You can also just create a new project (Box icon), select Java ME, and have your fun that way

## Fixing the inbuilt emulator
* I recommend just running Microemulator as its less problematic but the inbuilt emulator can usually be fixed by running `sudo execstack -c /opt/sun-wtk/bin/*.so`. This requires the aur package https://aur.archlinux.org/packages/execstack. Some people report still having issues with Malloc, this seems to be system dependent.

## Notes:
* The run button is broken, install microemulator and build every time you need to run, running `microemulator (yourthing).jad` in the commandline
* If you have images to submit to this guide, open a github issue and I'll be happy to add them
* I didn't test this guide exactly in this order, but its still the correct steps to my knowledge
