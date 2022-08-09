# Common Issues with the Installer
## Prelude
Remember, this guide is the only help you will receive.

In addition, the **only** place to download official Forge installers is at https://files.minecraftforge.net/net/minecraftforge/forge/

**DO NOT POST ANY LOGS TO #tech-support IN THE FORGE DISCORD. YOU WILL NOT RECEIVE ANY HELP, IN ACCORDANCE WITH #rules 11. THIS GUIDE IS THE ONLY HELP YOU WILL RECEIVE.**

## Common Issues
### Whenever I open the installer, it just redownloads or it opens with an archive manager. 

Certain Java archive (JAR) files, such as the Forge installer/launcher JARs, are designed to be self-executing; if double-clicking the file does nothing or opens an archive manager (like WinRAR/7-zip) then you need to adjust the Windows registry to fix the file association.

A program has been created to do this automatically, here: https://johann.loefflmann.net/downloads/jarfix.exe

It will automatically detect your Java version and correct the file association. You may need to restart your computer to apply the fix. 

If not Java version is detected, it will prompt you to download Java, which you should.

The program edits your registry to fix the file association, which is necessary to make the registry edits.'

### `javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target`?

There are two main causes of this. 

1. You installed a client that supports pirated Minecraft versions and requires edits to the `C:\Windows\System32\drivers\etc\hosts` file. If this is the case, we do not support piracy. Buy the game, and then remove the entries in the `hosts` file. 

2. You need to install an updated version of Java. Download and install the latest Java version from https://adoptium.net/. You may need to run Jar Fix from the section above.
