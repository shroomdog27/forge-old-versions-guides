# Common Issues with the Game
## Prelude
Remember, these guides are the only help you will receive.

**DO NOT POST ANY LOGS TO #tech-support IN THE FORGE DISCORD. YOU WILL NOT RECEIVE ANY HELP, IN ACCORDANCE WITH #rules 11. THESE GUIDES ARE THE ONLY HELP YOU WILL RECEIVE FROM THE FORGE DISCORD.**

## Common Issues
### `Caused by: java.lang.ClassCastException: class jdk.internal.loader.ClassLoaders$AppClassLoader cannot be cast to class java.net.URLClassLoader (jdk.internal.loader.ClassLoaders$AppClassLoader and java.net.URLClassLoader are in module java.base of loader 'bootstrap')`?

You're using Java 9+ on a version that requires Java 8.

You can download Java from the Adoptium project: https://adoptium.net/temurin/releases/
Select the Version dropdown option for the Java version you wish to download.
- 1.18 and later need Java 17
- 1.17 needs Java 16
- 1.16.5 and older need Java 8

### OptiFine?
If you're running OptiFine, try removing it first. OptiFine is a closed source mod that uses xdelta files to directly modify Minecraft's game files. Some mods can be incompatible, and game crashes caused by OptiFine can be hard to read. If you're experiencing issues, try removing OptiFine first. If the problem no longer occurs without OptiFine, then you know that at least one mod is incompatible with OptiFine. If you want to try and find out which mod(s), use the binary search method. For information on this, type `!binarysearch` in the #bot-commands channel in the Forge Discord. 
