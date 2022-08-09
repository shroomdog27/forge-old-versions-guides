# Common Issues with the Installer
## Prelude
Remember, these guides are the only help you will receive from the Forge Discord.

In addition, the **only** place to download official Forge installers is at https://files.minecraftforge.net/net/minecraftforge/forge/

**DO NOT POST ANY LOGS TO #tech-support IN THE FORGE DISCORD. YOU WILL NOT RECEIVE ANY HELP, IN ACCORDANCE WITH #rules 11. THESE GUIDES ARE THE ONLY HELP YOU WILL RECEIVE FROM THE FORGE DISCORD.**

## Common Issues
### Whenever I open the installer, it just redownloads or it opens with an archive manager. 

Certain Java archive (JAR) files, such as the Forge installer/launcher JARs, are designed to be self-executing; if double-clicking the file does nothing or opens an archive manager (like WinRAR/7-zip) then you need to adjust the Windows registry to fix the file association.

A program has been created to do this automatically, here: https://johann.loefflmann.net/downloads/jarfix.exe

It will automatically detect your Java version and correct the file association. You may need to restart your computer to apply the fix. 

If not Java version is detected, it will prompt you to download Java, which you should.

The program edits your registry to fix the file association, which is necessary to make the registry edits.

### `javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target`?

There are two main causes of this. 

1. You installed a client that supports pirated Minecraft versions. If this is the case, we do not support piracy, buy the game.

2. You need to install an updated version of Java. Download and install the latest Java version from https://adoptium.net/. You may need to run Jar Fix from the section above.


## My issue isn't listed.

Then you will have to look into the issue.

First, were there any pop up messages that provided instructions, such as deleting a file or directory? If so, you should follow those instructions and try again.

If not, then you will have to examine in the installer log. The installer log is the name of the installer with `.log` appended to it. For example, if you ran the `forge-1.8.9-11.15.1.2318-1.8.9-installer.jar` installer, its installer log would be named `forge-1.8.9-11.15.1.2318-1.8.9-installer.jar.log`. Look to see what errors occurred, and google what it would take to resolve them.