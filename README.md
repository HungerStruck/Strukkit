Strukkit
===========

:warning: This is the 1.8 branch!

HungerStruck/Enviark's fork of SportBukkit.

Contributing
------------

###Building

Build everything from scratch: `./build.sh`

- *The Strukkit binary will be located in ./build/CraftBukkit/target/*

Generate patched Strukkit source code: `./prepare-build.sh`

- *Generated sources will be located in ./build/Bukkit/ and ./build/CraftBukkit/*

Make the changes you want in `./build/Bukkit` or `./build/CraftBukkit`

- *We follow the [Bukkit contributing](https://github.com/Bukkit/Bukkit/blob/master/CONTRIBUTING.md) guidlines. Please read!*

- *If you don't read it at all, at least please mark any NMS code changes using `//Strukkit`*

Compiling your changes you have three options when it comes to compiling Strukkit

1. Run `./compile.sh`
2. Run build from IntelliJ from [`View -> Tool Windows -> Maven Project -> Strukkit -> Lifecycle -> package`](http://i.imgur.com/c6wU0fK.png)
3. Add a new Maven Build Configuration in IntelliJ
    - *The working directory will be `./build/CraftBukkit/`*
    - *The command line will be `package`*

- *The new Strukkit binary will be located in ./build/CraftBukkit/target/*

###Testing

You can copy and paste the newly built jar file everytime you build a new one into a server dir, or you can setup IntelliJ to run one for you. 

Add a new Build Configuration, adding a new [`JAR Application`](http://i.imgur.com/bXJzpBq.png)

Set the `Path to JAR` to be `./build/CraftBukkit/target/strukkit-<VERSION>.jar`

It works now, but it is recommended to also change the Working Directory to somewhere else. I recommand `./build/local-server/`

- *You will have to create `./build/local-server` manually*

###Creating a .patch file

After you've made the changes and tested that they worked (You did test them, right?), you can create a .patch file.

If you modified Bukkit code:
- `cd` into `./build/Bukkit` and create your commit.

If you modified CraftBukkit code:
- `cd` into `./build/CraftBukkit` and create your commit.

- *You do not have to push these, in fact, don't. Just creating the commit is enough for the next step*

- *Do not worry about adding patch numbers, this will be automatically* 

Build the .patch files by running `./rebuild-patches.sh`

- *You should see your patch on screen with a patch number!*

Once you have your .patch files, commit them to Strukkit by commiting in the root dir.

###Cleaning up

To remove all the generated files: `./clean.sh`

- *This will remove all generated source files, so only do this once you've commited your changes!*
