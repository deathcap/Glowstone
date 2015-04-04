Glowstone
==========

Introduction
------------
Glowstone is a lightweight, from scratch, open source
[Minecraft](http://minecraft.net) server written in Java that supports plugins
written for the [Bukkit](http://bukkit.org) API.

The main goals of the project are to provide a lightweight implementation
of the Bukkit API and Minecraft server where exact vanilla functionality is
not needed or higher performance is desired than the official software can
deliver. Glowstone makes use of a thread-per-world model and performs
synchronization only when necessitated by the Bukkit API.

Features
--------
Glowstone has a few key advantages over CraftBukkit:
 * It is **100% open source**. While CraftBukkit and most other mods are open
   source, they rely on decompiled Minecraft source code. Glowstone's code is
   completely original.
 * Because of this, it is easy to contribute to Glowstone's development. The
   barrier of entry to contributions is lower because there is no need to work
   around decompiled source or maintain a minimal diff.
 * Glowstone supports all plugins written for the Bukkit API natively. In
   practice, some plugins may try to make use of parts of the API which are not
   yet implemented, but in a completed state Glowstone would support all plugins.
 * Glowstone's simplicity affords it a performance improvement over CraftBukkit
   and other servers, making it especially suited for situations where a large
   amount of players must be supported but Vanilla game features are not needed.
 
However, there are several drawbacks:
 * Glowstone **is not finished**. Nothing is guaranteed to work, though many things
   are likely to. If in doubt, ask in `#glowstone`.
 * Vanilla survival features are entirely absent (mobs, hunger, health, so on).
   Glowstone cannot yet replicate a vanilla survival environment. These will be
   added over time.
 * Bukkit plugins which expect the presence of CraftBukkit-specific code
   (that in the `org.bukkit.craftbukkit` or `net.minecraft.server` packages)
   will not work on Glowstone unless they are designed to fail gracefully.
 * Glowstone is not produced by the Bukkit team, and while we do make an effort
   to produce quality work, Glowstone does not undergo the same rigorious testing
   as the Bukkit project.
   
Some of the key features that have been implemented are:
 * World loading, saving, and streaming to players.
 * Player interaction with the world (building, digging).
 * Somewhat-complete inventory support.
 * A simple world generator (support for others through Bukkit).
 * World weather (rain, thunder/lightning).
 * Op, ban, IP ban, and whitelist support.
 * Many of the advanced API features of Bukkit.

Building and Running
--------------------
Glowstone can be built with the
[Java Development Kit](http://oracle.com/technetwork/java/javase/downloads) and
[Maven](https://maven.apache.org) The command `mvn package` will build Glowstone and
place the final jar in `target/` named `glowstone-0.0.1-SNAPSHOT.jar`.

Running Glowstone is simple because its dependencies are shaded into the output
jar at compile time. Simply execute `java -jar glowstone.jar` along with any
extra JVM options desired. A variety of command-line options are also available -
run `java -jar glowstone.jar --help` for more information.

By default, configuration is stored in the `config/` subdirectory and logs
are stored in the `logs/` subdirectory. The main configuration file is
`config/glowstone.yml`, which replaces CraftBukkit's `server.properties` and
`bukkit.yml`. Settings from these two files will be copied over to Glowstone's
configuration during the default configuration generation process.

Glowstone uses [JLine](http://jline.sf.net) for console input and colored
console output. The JLine console can be disabled in the configuration if a
flat console is desired.

Docs and Support
-------------
The best place to receive support is on the [Glowstone Forums](https://forums.glowstone.net/),
where you can ask a question and someone who knows the answer can respond.
If you prefer IRC, visit our IRC channel `#glowstone` on EsperNet (`irc.esper.net`).

User and contributor documentation and other articles can be found on the
[GitHub wiki](https://github.com/SpaceManiac/Glowstone/wiki).
Javadocs can be generated by using the `mvn javadoc:javadoc` command and are
placed in the `target/site/apidocs/` directory, but these are incomplete
-in some places and in general the code is the best reference.


For documentation on the Glowkit API (an updated Bukkit which is used to
write plugins), see the [Glowkit Javadocs](http://build.greatmancode.com/job/Glowkit/javadoc/),
or visit the official [Bukkit Javadocs](http://jd.bukkit.org/).

Credits
-------
 * [The Minecraft Coalition](http://wiki.vg/) and [`#mcdevs`](http://mcdevs.org/) -
   protocol and file formats research.
 * [The Bukkit team](http://bukkit.org) for their outstandingly well-designed
   plugin API.
 * [Trustin Lee](http://gleamynode.net) - author of the
   [Netty](http://netty.io/) library.
 * [Graham Edgecombe](https://github.com/grahamedgecombe/) - author of the
   original [Lightstone](https://github.com/grahamedgecombe/lightstone).
 * All the people behind [Maven](https://maven.apache.org) and
   [Java](http://java.oracle.com).
 * [Notch](http://mojang.com/notch) and the rest of
   [Mojang](http://mojang.com) - for making such an awesome game in the first
   place!

Copyright
---------
Glowstone is open-source software released under the MIT license. Please see
the `LICENSE` file for details.
