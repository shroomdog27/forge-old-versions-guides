
# Common Issues with the Game
## Prelude
Remember, these guides are the only help you will receive from the Forge Discord.

The purpose of this guide is to explain how to read `debug.log` and `crash-reports` in order to help you debug what went wrong.

**DO NOT POST ANY LOGS TO #tech-support IN THE FORGE DISCORD. YOU WILL NOT RECEIVE ANY HELP, IN ACCORDANCE WITH #rules 11. THESE GUIDES ARE THE ONLY HELP YOU WILL RECEIVE FROM THE FORGE DISCORD.**

## `debug.log`
### What is `debug.log`?
`debug.log` is a file located in your `logs` folder in your Minecraft installation. It is one of the first files created when Forge starts and it has lots of useful debugging information. In some rare instances, crashes can occur before this file is created. In this case, use `!launcherlogs` in #bot-commands to see how to get the launcher logs. Ignore the part where it stays to upload to a paste site, we will not be able to provide help with reading logs. This is what this guide is for.
### How do I read it?
`debug.log` is just a text file. You can use any text editor to read it, but I would recommend [Notepad++](https://notepad-plus-plus.org/downloads/). It's a wonderful, lightweight text editor that makes it easy to scroll and read logs.
### It's open, now what?
So this is the tricky part, as your issue could be anywhere in the log. If it's a crash, usually it's located near the bottom. In Minecraft, crashes are usually caused by an error that prints what is called a stack trace.

### What's a stack trace?

In simple terms, a stack trace is a list of function calls that the game was in the middle of executing when the problem occurred. Here's an example stack trace.
```
org.spongepowered.asm.mixin.transformer.throwables.MixinTransformerError: An unexpected critical error was encountered
	at org.spongepowered.asm.mixin.transformer.MixinProcessor.applyMixins(MixinProcessor.java:392) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinTransformer.transformClass(MixinTransformer.java:250) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.service.modlauncher.MixinTransformationHandler.processClass(MixinTransformationHandler.java:131) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.launch.MixinLaunchPluginLegacy.processClass(MixinLaunchPluginLegacy.java:131) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at cpw.mods.modlauncher.serviceapi.ILaunchPluginService.processClassWithFlags(ILaunchPluginService.java:154) ~[modlauncher-8.1.3.jar:8.1.3+8.1.3+main-8.1.x.c94d18ec] {}
	at cpw.mods.modlauncher.LaunchPluginHandler.offerClassNodeToPlugins(LaunchPluginHandler.java:85) ~[modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.ClassTransformer.transform(ClassTransformer.java:120) ~[modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.TransformingClassLoader$DelegatedClassLoader.findClass(TransformingClassLoader.java:265) ~[modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.TransformingClassLoader.loadClass(TransformingClassLoader.java:136) ~[modlauncher-8.1.3.jar:?] {re:classloading}
	at cpw.mods.modlauncher.TransformingClassLoader.loadClass(TransformingClassLoader.java:98) ~[modlauncher-8.1.3.jar:?] {re:classloading}
	at java.lang.ClassLoader.loadClass(ClassLoader.java:351) ~[?:1.8.0_322] {}
	at net.minecraftforge.fml.network.NetworkInitialization.getHandshakeChannel(NetworkInitialization.java:41) ~[forge:?] {re:classloading}
	at net.minecraftforge.fml.network.FMLNetworkConstants.<clinit>(FMLNetworkConstants.java:49) ~[forge:?] {re:classloading}
	at net.minecraftforge.fml.ModLoader.<init>(ModLoader.java:129) ~[forge:?] {re:classloading}
	at net.minecraftforge.fml.ModLoader.get(ModLoader.java:154) ~[forge:?] {re:classloading}
	at net.minecraftforge.fml.client.ClientModLoader.lambda$begin$1(ClientModLoader.java:103) ~[forge:?] {re:classloading,pl:runtimedistcleaner:A}
	at net.minecraftforge.fml.client.ClientModLoader.lambda$createRunnableWithCatch$4(ClientModLoader.java:123) ~[forge:?] {re:classloading,pl:runtimedistcleaner:A}
	at net.minecraftforge.fml.client.ClientModLoader.begin(ClientModLoader.java:103) ~[forge:?] {re:classloading,pl:runtimedistcleaner:A}
	at net.minecraft.client.Minecraft.<init>(Minecraft.java:437) ~[?:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:randompatches.mixins.json:client.MinecraftMixin,pl:mixin:APP:flywheel.mixins.json:ShaderCloseMixin,pl:mixin:APP:architectury.mixins.json:MixinMinecraft,pl:mixin:APP:abnormals_core.mixins.json:client.MinecraftMixin,pl:mixin:APP:mixins.zycraft.json:client.MinecraftMixin,pl:mixin:APP:kubejs-common.mixins.json:MinecraftMixin,pl:mixin:APP:immersiveengineering.mixins.json:accessors.client.MinecraftAccess,pl:mixin:APP:assets/botania/botania.mixins.json:AccessorMinecraft,pl:mixin:APP:create.mixins.json:WindowResizeMixin,pl:mixin:A,pl:runtimedistcleaner:A}
	at net.minecraft.client.main.Main.main(Main.java:149) ~[1.16.5-forge-36.2.40-1.16.x-shroom-hacks.jar:?] {re:classloading,pl:runtimedistcleaner:A}
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[?:1.8.0_322] {}
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62) ~[?:1.8.0_322] {}
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[?:1.8.0_322] {}
	at java.lang.reflect.Method.invoke(Method.java:498) ~[?:1.8.0_322] {}
	at net.minecraftforge.fml.loading.FMLClientLaunchProvider.lambda$launchService$0(FMLClientLaunchProvider.java:51) ~[forge-1.16.5-36.2.40-1.16.x-shroom-hacks.jar:36.2] {}
	at cpw.mods.modlauncher.LaunchServiceHandlerDecorator.launch(LaunchServiceHandlerDecorator.java:37) [modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:54) [modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:72) [modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.Launcher.run(Launcher.java:82) [modlauncher-8.1.3.jar:?] {}
	at cpw.mods.modlauncher.Launcher.main(Launcher.java:66) [modlauncher-8.1.3.jar:?] {}
Caused by: org.spongepowered.asm.mixin.injection.throwables.InjectionError: Critical injection failure: Constant modifier method getMaxNBTCompoundTagPacketSize(J)J in randompatches.mixins.json:packetsizelimits.PacketBufferMixin failed injection check, (0/1) succeeded. Scanned 1 target(s). Using refmap randompatches.refmap.json
	at org.spongepowered.asm.mixin.injection.struct.InjectionInfo.postInject(InjectionInfo.java:468) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinTargetContext.applyInjections(MixinTargetContext.java:1362) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinApplicatorStandard.applyInjections(MixinApplicatorStandard.java:1051) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinApplicatorStandard.applyMixin(MixinApplicatorStandard.java:400) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinApplicatorStandard.apply(MixinApplicatorStandard.java:325) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.TargetClassContext.apply(TargetClassContext.java:383) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.TargetClassContext.applyMixins(TargetClassContext.java:365) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	at org.spongepowered.asm.mixin.transformer.MixinProcessor.applyMixins(MixinProcessor.java:363) ~[mixin-0.8.4.jar:0.8.4+Jenkins-b308.git-2accda5000f7602229606b39437565542cc6fba4] {}
	... 29 more
```
There are several parts to digest, so let's start with the first line. 

#### `org.spongepowered.asm.mixin.transformer.throwables.MixinTransformerError: An unexpected critical error was encountered` 
This explains the immediate error that wasn't caught. This isn't necessarily the problematic error, it is just the one that immediately had an issue. The various `at` lines are method calls written as how Java interprets them.

#### `Caused by: org.spongepowered.asm.mixin.injection.throwables.InjectionError: Critical injection failure: Constant modifier method getMaxNBTCompoundTagPacketSize(J)J in randompatches.mixins.json:packetsizelimits.PacketBufferMixin failed injection check, (0/1) succeeded. Scanned 1 target(s). Using refmap randompatches.refmap.json` 
This is a `Caused by:` error. This is an exception that was thrown that was included in the stack trace. Exceptions that happen first are the lowest on the stack trace, so there could be multiple `Caused by:` lines. The bottom most one is the first Exception that occurred. In this case, a mod had a problem using a Mixin. 

How can we tell which mod had the problem? There's two ways we can tell. The first is to look at the `Caused by:` line and look for mod names or mod name abbreviations. In this case, we see a reference to "randompatches". So we know from this that the mod "Random Patches" has an issue with its Mixins, and needs to be removed.

Another way to tell is to look at one of the `at`s and see if there's a mod name somewhere. In this case, there isn't. However, there might be in your case.

### So, I should always be looking for `MixinTransformerError` then?
No, not necessarily. This was just an example given to you to help you understand how to read stack traces that appear in both the `debug.log` and `crash-reports`. 

## `crash-reports`
### What's the deal with `crash-reports`?
A crash report is (usually) almost always generated whenever the game crashes. However, there are exceptions to this. If a mod modifies with the crash report handler, then the game could crash while it's trying to save the crash report. In this case, looking in the `debug.log` is absolutely necessary. 
### How are `crash-reports` organized?
There are several parts. 

First is the immediate stack trace. This is the error that immediately caused the game to crash. Try looking for mod names here! 

Next is the details. The game will post as much information about the current state of the game, and the exception in order to help you debug. Some parts that may be included include the stack trace, Details about what's currently going on, such as what Screen was being rendered, what the current level information is like, including entities and players being rendered, and other details.

Finally is System Details. This is information regarding your the Minecraft Version, Java Version, Operating System, and lots of information regarding what's currently loaded. 
### So... what information do I actually care about?
Usually the problematic mod name or mod name's abbreviation will appear in the stack trace. You'll have to do some sleuthing, as the mod names that appear in these stack traces might not be the same as the name of the mod .jar file. You'll have to examine and see what mod is really causing the problem.
