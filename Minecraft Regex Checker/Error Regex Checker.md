So, this is a fairly simple utility that extracts the useful information from Minecraft server error messages.

Why make this? Cause, I thought it'd be cool to build upon it and make a Discord bot that automatically replies and handles common errors

This basically extracts
- The Event name
- The plugin name and version
- The type of error
- The path to the line causing it

I also only tested this with one error, so, it may not even work fully. But, it does with this error, and, that's good enough!

Anyways..

Event name: "(?<=Could not pass event\s).+?(?=\s\bto\b)"
Plugin name and version: "(?<=Could not pass event.+?\bto\s)\w+\s[\w\.]+"
Type of error: "(?<=Caused by:\s)\S+"
Path to line: "?<=at\s).+?(?=\s~\[\?:\?])"

Maybe someone will find this interesting, haha.

Oh, here's the error I tested with

[02:06:24 ERROR]: Could not pass event EntityTargetLivingEntityEvent to IDK v1.0
org.bukkit.event.EventException
        at org.bukkit.plugin.java.JavaPluginLoader$1.execute(JavaPluginLoader.java:306) ~[spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at org.bukkit.plugin.RegisteredListener.callEvent(RegisteredListener.java:62) ~[spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at org.bukkit.plugin.SimplePluginManager.fireEvent(SimplePluginManager.java:502) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at org.bukkit.plugin.SimplePluginManager.callEvent(SimplePluginManager.java:487) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityInsentient.setGoalTarget(EntityInsentient.java:143) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.PathfinderGoalTarget.d(PathfinderGoalTarget.java:83) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.PathfinderGoalSelector.a(SourceFile:113) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityInsentient.doTick(EntityInsentient.java:653) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityLiving.n(EntityLiving.java:2037) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityInsentient.n(EntityInsentient.java:501) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityMonster.n(EntityMonster.java:24) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityZombie.n(EntityZombie.java:155) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityLiving.A_(EntityLiving.java:1893) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityInsentient.A_(EntityInsentient.java:244) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityMonster.A_(EntityMonster.java:28) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.EntityZombieVillager.A_(EntityZombieVillager.java:70) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.World.entityJoinedWorld(World.java:1629) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.World.h(World.java:1604) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.World.tickEntities(World.java:1430) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.WorldServer.tickEntities(WorldServer.java:618) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.MinecraftServer.D(MinecraftServer.java:814) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.DedicatedServer.D(DedicatedServer.java:399) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.MinecraftServer.C(MinecraftServer.java:678) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at net.minecraft.server.v1_11_R1.MinecraftServer.run(MinecraftServer.java:576) [spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        at java.lang.Thread.run(Unknown Source) [?:1.8.0_77]
Caused by: java.lang.NullPointerException
        at me.libert.kits.kitpvp.pet(kitpvp.java:214) ~[?:?]
        at sun.reflect.GeneratedMethodAccessor7.invoke(Unknown Source) ~[?:?]
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source) ~[?:1.8.0_77]
        at java.lang.reflect.Method.invoke(Unknown Source) ~[?:1.8.0_77]
        at org.bukkit.plugin.java.JavaPluginLoader$1.execute(JavaPluginLoader.java:302) ~[spigot.jar:git-Spigot-d4f98a3-cb61ac0]
        ... 24 more

PASTE (Not sure how long it'll stay here, that's why it's pasted): https://paste.helpch.at/raw/ayadixijet
