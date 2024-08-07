# Setting up a basic scene.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Getting started

An ultrakill scene has some nessesary stuff to be able to work properly for example: `StatsManager` , `Event System` and etc. 

Lets get started by first creating a new scene in <span style="color:red">Spite</span> and from there we will explain what each one of them does.

Start by pressing the <span style="color:red">Spite</span> button in the toolbar and hit `New Level` , Name the scene whatever you want and anywhere in the project (preferably in a folder inside the project specifically for it due to organization)

>[!TIP]
>
>Its better to open and modify the "DONOTDELETE" scene in the Assets/SPITE/scenes/DONOTDELETE. This way you will not have to do these steps every time you create a new level, because Spite just copies this scene every time you do so.
>***But you must follow this page to the letter if you decide to modify it.***
>-Spelar

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_001.png?raw=true" alt="Spite Tab" width="90%" height="90%" style="margin-bottom: 20px;" >
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_007.png?raw=true" alt="Scene Tab" width="30%" height="30%" >
</div>
 
You will see theres already a statsmanager in the scene, BUT its recommended to delete it, and search for the prefab in your project's assets

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_004.png?raw=true" alt="StatsManager Tab" width="45%" height="45%" >
</div>

See this? This is `StatsManager`. What does it do? Well, it basically gives ultrakill the needed info for a level such as the times and kills and style needed plus it has a child named `MusicManager` which from the name manages musics, All to know really about `StatsManager` is that its where you specify alot of things

> [!IMPORTANT]
>Set the level number to -1 to be able to open the tab menu to see rankings and time and etc.

---

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_006.png?raw=true" alt="StockMapInfo Tab" width="45%" height="45%" >
</div>

This is `StockMapInfo` , You can think of it as an extension of `StatsManager` , The key difference is its only used for visual information about the level such as level layer and level name that appear when coming out of the hellevator, It also shows the level name from the tab menu in the `Large Text` field, Another thing is the `Large Image` field which is used by the game's discord RPC system

Essentially, Using a image hosting website like https://imgbb.com/ , you can upload a 4:3 image of the level and copy its link and paste it in that field to make it so the level's image shows on discord when you play it.

![hhahahah](https://coolboi21.github.io/Rude-Docs/Tutorials/Intermediate/assets/discord-integration-tut-copyimage.webp)

---

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_008.png?raw=true" alt="Out of bounds Tab" width="45%" height="45%" >
</div>

This is `OUT OF BOUNDS` , As from the name, it teleports player to the first room or last checkpoint if the player manages to noclip/fall out of the map.

Very Useful In Open Maps.

---

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_009.png?raw=true" alt="First room Tab" width="45%" height="45%" >
</div>

This is by far the most important gameobject in the scene, As it actually contains the player, You may be inclined to use the direct prefab of the first room but it requires some tweaks before it can be used. As it contains missing scripts.

<details>

<summary>If you want to use the direct First Room:</summary>

1. Place the First Room prefab from ULTRAKILL assets and unpack it.

2. Create a gameobject "Player_2" as a child of the "Player" gameobject and with an 'addressable replacer' set to 'FirstRoom Player Only'. Uncheck the 'Destroy This' boolean. ***Make sure its rotation and position are equal to 0***.

3. Move the created gameobject outside of "Player" and delete the "Player".

4. Disable a 'GameController' gameobject.

</details>

---

## Final Door

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_010.png?raw=true" alt="Finaldoor Tab" width="100%" height="100%" >
</div>
The difference between final room and first room is the fact that final room allows you to use its direct prefab, which means you can easily add custom stuff there.

> [!NOTE]
> Do not be alarmed that the final room has no pit , Upon the activation of the gameobject `FinalDoorOpener` the door opens and the pit is activated.

---

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Image_003.png?raw=true" alt="Eventsystem Tab" width="45%" height="45%" >
</div>

Do not touch anything about this.
