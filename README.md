# MiA BSFD Modding Tools

# Contract


Throughout this guide I will use specific term to convey certain instructions along with their importance.

They are defined as follow:

+ **Note** : Additional context to an instruction.
    You can usually glance over it.

+ **Tip** : Usually related to work organization, or something I encourage you to do to help your future self.  
    I try to stay coherent, I thus use **tips** to make sure you follow along with what I am doing.

    However my way is not the only way, you are free to customize your workspace in a way that works for *you*.  
    But please note that even if it is not required to follow it, I will refer to previous **tips** in further instructions to maintain *continuity*.

    Put simply I assume you followed the **tips**, if you didn't this is perfectly ok !  
    But you now become responsible for any problems that might arise as I cannot test your specific setup or know what you did.

+ **Important** : Important instructions, failure to follow them *will* create issues, be it immediately or later down the line.

    I will try to provide fixes when possible if I know which error / problem will result from not following instructions.  
    But please understand that as we go further and further into the guide and touch upon more complex subject you will rise to my own competency level and the limit of my knowledge, I will thus treat you as an equal and consider you capable of understanding what you are doing.

+ **Advanced** : Advanced instructions, be it comments, context or tips.  
    They might not always make sense to you yet and are destined to someone who is already familiar with the material / already a modder.

+ **Experimental** : Consider this oral tradition from a white whistle.
    + Information on what I have seen in the files,
    + What I think something is doing,
    + A potential explanation to something,
    + My thought on a solution to a problem etc.

    I will not elaborate further, what you can understand from it will entirely depend on you.  
    The information might also not be accurate.

    Over time some of this information could become facts as fellow divers uncover the mysteries of the abyss.  
    I could then put them under **Advanced**.
    
    You can see modders as divers, each one follows a route they uncovered through trial and errors.  
    By the simple virtue of taking a different path you might understand a concept in a different way or make discovery another diver would have never made.
    
    One modder could have an interest in artifacts lost in the system, while another will focus on the wildlife, meanwhile yet another will focus on diving tools.
    
    Each one brings its own contribution. 

## External Link

Whenever possible I will link to external resources for further reading and download.

I cannot be held responsible if at some point in the future some of these resources become unavailable.  
I can however guarantee that as of the creation of this document or upon updating a specific section I make / will make sure to review the availability of the links.

If a specific resource become unavailable, I will try to find an alternative or failing that clearly indicate that I could not find any.

## Operating System

I mod on Windows 10.  
If you use any other operating system I cannot guarantee how each tool will work.

It might work just fine.  
It might not work.  
It might summon a Madokajack, who knows ?

Whenever you download a tool, the onus will be on you to check if it is available for your system.

## Basic Knowledge

I will assume that you have a basic understanding of how to use a computer in general, and Windows in particular.

I will not explain how to unzip an archive, open common file formats or navigate inside the file system, etc.

Only knowledge specific to modding this game will be detailled.

## Security

I guarantee that all the files I ask you to download be it from an external link or from this github page, have also been downloaded by me.

I make sure to check them, and you should too, especially if it is a script.  
I will not willingly provide you with a malicious tool or program.

Please understand that Windows and/or your antivirus can flag some of them as malicious, this is normal as some (Unreal Unlocker for example) hook into the game processes and this is a method also used by malwares as a form of attack.  
Meaning the way in which they operate is also shared by malicious parties to gain access to a system (in the method, not the goal).

You will in essence do the same thing, the game devs did not intend for you to hook into their game to understand how it works and modify it to your will, in a way you are acting maliciously and are too acting as a virus.  
This is all a matter of perspective, thus windows and/or your antivirus have no way to decipher a concept such as *intent*, they can only perceive a *method*.

The guide's author is not labelling you as a virus, any such perception is purely fortuitous :)

## Issues

I guarantee that all that is written here have been done and redone by yours truly.  
There is no issue with the process if you have followed the contract.

Any deviation from the contract changes the scope of the certainty I provide, and will thus void the warranty.


# File Structure (External)

**Made in Abyss: Binary Star Falling into Darkness** is a game developed with *Unreal Engine 4.25*, it uses *[.pak](https://docs.unrealengine.com/4.26/en-US/Basics/Projects/Packaging/)* files to store some of its *assets*.

[Unreal Engine](https://en.wikipedia.org/wiki/Unreal_Engine) uses .pak files to deliver assets outside of the main executable of an application.  
To do so, the assets are organized into chunks which are groups of asset files that are recognized by the *cooking process*.

Note: The [Content Cooking](https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/Deployment/Cooking/) process will not be explained as it falls outside the scope of this guide, the notion of organizing assets together is however very important and will be talked about later.

## Pak Location

The games .pak files are located under:
```
.\Steam\steamapps\common\MadeInAbyss-BSFD\MadeInAbyss-BSFD\Content\Paks
```

**Note**: the path before .\\Steam is entirely dependant on your system and is thus not detailed.

**Tip** : I recommend you create a *shortcut* to this directory, this will make it easier to navigate back to it.

If you have the latest game version (*1.0.4*) you will see this :
```
MadeInAbyss-BSFD-WindowsNoEditor.pak
MadeInAbyss-BSFD-WindowsNoEditor_0_P.pak
```

It is not an understatement to say that this is where your modding journey will start and end.

This is where you will start exploring the game structure as well as transfer your mod(s) for testing.  
One day perhaps, you will put down modding on this very window.


# Modding Organization

I highly recommend you setup a *dedicated folder* on your computer for *MiA Modding* (Mine is called exactly that), it will contain all the *tools*, *resources* and *references* necessary for modding and will grow as you get familiar with the material.

You are of course free to organize your workspace whichever way works best for you.  
For consistency sake however I will reference this dedicated folder and provide tips on how to expand it as we go.  
Just remember to adapt it in a way that works best for **you**.

For now I would recommend to create the following folders:
```
# Ideas
# Resources
Mod Reference
PAK Output
Work Directory
```

Add to the MiA Modding folder the shortcut to the \\Paks folder.
I called mine *Made in Abyss PAK location*.

You will thus have:
```
# Ideas
# Resources
Mod Reference
PAK Output
Work Directory
Made in Abyss PAK location - Shorcut
```


# Unpaking

Unpacking a .pak file is the process of "*opening*" the .pak to extract its content.  
To do so you will need a tool called **QuickBMS**.

## QuickBMS

**QuickBMS** is a tool that allows you (among other things) to unpack .pak files.

**Important** : Before you start unpacking, make sure you have at least 20 GB of free space.  
The output file will be **big**.

1. Download it from [here](https://aluigi.altervista.org/papers/quickbms.zip).

2. Extract the archive inside the *# Resources* folder (extract into a folder, do not extract the loose content directly).

The content of the extracted folder should be as follows:
```
changelog.txt
quickbms_4gb_files.exe
quickbms.exe
quickbms.txt
reimport_4gb_files.bat
reimport.bat
reimport2_4gb_files.bat
reimport2.bat
```

3. Double-click on *quickbms_4gb_files.exe*, this will open a command prompt.

    **Important** : Make sure to use *quickbms_4gb_files.exe* and not *quickbms.exe*.  
    I will judge you if you don't :)

5. The program will ask you to provide a *BMS script*, grab [this one](UnrealPak.zip).

    *Tip* : I recommend you put the BMS script inside the *# Resources* folder.

5. The program will ask you to select the *input archives/files* (The .pak).  
    Select *MadeInAbyss-BSFD-WindowsNoEditor.pak*.

    **Advanced** : *MadeInAbyss-BSFD-WindowsNoEditor_0_P* is the update to the base game, you can and should extract it as well, then compare the changes to make sure the files you are modding have not been updated by the devs in the 0 pak.  
    If yes, I recommend you use the 0 files as a base instead.  
    Unless you *want* to use original, in which case ignore me !

6. The program will ask you to select the *output folder* (Where it will unpack).

    **Tip** : Reads familiar right ? It's no coincidence :)  
    You guessed it, select the *PAK Output* folder.  
    I recommend you to create a sub-folder inside *PAK Output* called
    *MadeInAbyss-BSFD-WindowsNoEditor* and set it as the output folder.  
    Don't worry about the name for now, this is something for future you to learn.

7. If you see a binary ton of files flying at ludicrous speed on the terminal, it means the unpacking process has started !

    *Note* : There is a *LOT* to unpack so expect to wait a bit until it is done, this is normal.  
    You should also see your CPU and Disk usage spike, this too is normal.

    **Important** : If you get this error message :
    it means that you did not select *quickbms_4gb_files.exe* (like I asked you to).  
    You have been judged :)  
    Ok good judging, now go back to step 3.  
```
    the file is bigger than 4 gigabytes so it's NOT supported by quickbms.exe,
    I suggest you to answer 'n' to the following question and using
    quickbms_4gb_files.exe that doesn't have such limitation.
    are you sure you want to continue anyway (y/N)?
```

8. You are done !

    You should have these two folders inside.
```
    Engine
    MadeInAbyss-BSFD
```

If you do you are good to go !  
For comparison here are the final lines of my extraction :
```
- 94877 files (189754 logs) found in 357 seconds
  coverage file 0    99%   20593220244 20654694024 . offset 00000004cf1d9daa

Press ENTER or close the window to quit
```


If not, something went wrong at some point during the extraction, but I cannot tell you what as it is something specific to your system, try the following in no particular order :

+ Make sure none of the used files are in use (for example .pak opened by FModel).
+ Re-download QuickBMS and its BMS script.
+ Make sure you have write permission to the folder you are trying to output to.
+ Read the log to try to find any clues as to what might've happened,


# File Structure (Internal)

This is where you will truly start your dive into the game files, the game's PAK structure is open for you to explore !

Start by navigating to the following folder :
```
.\PAK Output\MadeInAbyss-BSFD-WindowsNoEditor\MadeInAbyss-BSFD\Content\Movies
```

You should see five (5) *.mp4* files :
```
logo_spikechun.mp4
op_STEAM_en.mp4
op_STEAM_zhcn.mp4
op_STEAM_zhtw.mp4
op_STEAM.mp4
```

Try opening one, does it look familiar ?

## Folder Structure

### Introduction

Remember when I talked about how important **organizing assets together** was ?  
Let's talk about it !

In a *.pak* file the folder structure is of utmost importance !  
This structure is how the game data is organized, and the game is hardcoded to find *specific* assets in *specific* location.  
If you move one asset from one location to another, the game will simply *not find* that asset anymore !

You can see it as looking for your keys.  
If you have an habit of dropping them in one place then one day, for some reason, absent-mindedly dropped them elsewhere, chances are you will first go to the usual spot before realizing that, they are not there ?  
Now as a sane human being, what do you do ?  
Well of course you curse your past self as you anxiously pace around your house looking for them, trying to piece together what that *idiot* did.

As the minutes go by, your anxiousness turns to agitation, the cursing into expletives.  
**WHERE did I put those keys, I swear to-** oh hey there they are.  
Seems familiar, no ? Just me ? OK...

Now let's examine what the game will do.
```
Loading files...
File number x missing from location y > skipping
Loading default file from MadeInAbyss-BSFD-WindowsNoEditor.pak instead
```

As you can see the game is not a *human*, you are capable to look for something if it has changed location, **the game is not**.  
If it is not there it will simply **not do anything else**, instead it will check in the base pak where it knows the file is then load that instead (Assuming you did not tamper with that too of course).

**Advanced** : This is not strictly true, rather the game will follow the PAK load order.  
For simplicity sake I assume there are no other PAKs with custom load orders present.

**Important** : I will repeat it again, the game will not load your modded assets if you did not respect the proper folder structure !  
This is one of the most common issue new modders will encounter.  
If your mod doesn't work and you know you changed the proper values, check the folder structure !

### Application

Now let's take a look at what it looks like.

Let's assume you wanted to change the localization file located under:
```
.\PAK Output\MadeInAbyss-BSFD-WindowsNoEditor\MadeInAbyss-BSFD\Content\Localization\Game\en\Game.locres
```

You would of course change the file but you need to keep the **folder structure** in mind.  
If you modify the file then simply it put into a new folder, let's say for example "*My Localization Mod*" then try to Pak it, you might be surprised to find that it doesn't work, this is normal.

Indeed, this is what I mean when I ask to respect the folder structure.  
The game doesn't have any references pointing to a asset named Game.locres located in :
```
.\My Localization Mod\Game.locres
```

So it will simply not load it !  
Instead you will need to do this:

1. Create a new folder and name it :

```
MadeInAbyss-BSFD-WindowsNoEditor_My Localization Mod_P
```

**Important** : The first level of the folder structure must respect the pak nomenclature.  
Remember during the unpaking when I asked you to create a folder named *MadeInAbyss-BSFD-WindowsNoEditor* ? This is the same concept.  
The game will look for a .pak file named *MadeInAbyss-BSFD-WindowsNoEditor_String_P*.

The *String* part is where you can put a name for your mod.

2. Create as many sub-folder as needed until your structure mimics the one from the original asset location.  
    So for example if we keep the .locres file from earlier, it is located under :
```
MadeInAbyss-BSFD-WindowsNoEditor\MadeInAbyss-BSFD\Content\Localization\Game\en\Game.locres
```

So your mod must have this structure :
```
MadeInAbyss-BSFD-WindowsNoEditor_My Localization Mod_P\MadeInAbyss-BSFD\Content\Localization\Game\en\Game.locres
```

**Important** : I repeat again, if your mod does not follow the same folder structure the file will not be loaded.  
This is the last time I will repeat it.

3.  Pak your mod and you are done !


# Paking

Packing a folder (Typically a mod) is the process of "*closing*" a folder containing modded assets and transforming it into a format the game can use.  
To do so you will need a tool called *UnrealPak*.

1. Download it from [here](unreal_tournament_4_0.4.25d.bms).

2. Extract the archive inside the *# Resources* folder.

The content of the extracted folder should be as follows:
```
list.txt
pakme.bat
UnrealPak-With-Compression.bat
UnrealPak-Without-Compression.bat
UnrealPak.exe
```

**Tip** : I recommend you create a *shortcut* for the pakme.bat file and put it into *# Resources* or even *MiA Modding*, this will make it faster to navigate to it to pak your mods (Something you will do a lot while testing).

3. Drag & Drop you mod folder into pakme.bat.

    This will open a terminal window, here is an example from one of my mods :
```
[REDACTED]\UnrealPak.exe "[REDACTED]\Psitegrad's Cooking Rebalance\MadeInAbyss-BSFD-WindowsNoEditor_Psitegrad's Cooking Rebalance241_P.pak" -create=list.txt
LogPakFile:Display: Loading response file list.txt
LogPakFile:Display: Added 1 entries to add to pak file.
LogPakFile:Display: Collecting files to add to pak file...
LogPakFile:Display: Collected 3 files in 0.00s.
LogPakFile:Display: Added 3 files, 764323 bytes total, time 0.01s.
```

**Note** : Your console output might be more *verbose* than mine, this was confirmed in another person's system and is considered normal.  
As long as the verification in step 4. is positive, all is good.

4. Confirm the number of files paked, if this corresponds to the content of your mod folder then the paking was successful, proceed to the next step.

    If you get an error, 0 files were added, or the generated .pak file is empty, then the paking failed.
    
    {To expand}
    Need to test multiple possible ways to mess up the config to see what kind of errors it will return, it's a bit hard to imagine what could go wrong}.

5. In the same folder as your mod folder, you should now see a new .pak file with the same name as your mod folder.

    Congratulation you paked your first mod !
