<h1> Optimization</h1>
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

Maps can be quite heavy for some PCs to run, especially if they are big and open. So you need to optimize them in order to create a smooth experience. Here you will learn how to do that.

## Disactivating rooms
All official ULTRAKILL maps use this way of optimization. It works by simply disactivating rooms and activating them only when the player enters neighboring rooms.

<img src="https://github.com/layzyidiot/e-sw/blob/main/images/0-2_disabled.png?raw=true" alt="0-2" width="70%" height="70%" >

'Door' component can act as an object activator. There are 2 tabs, for activating and disactivating rooms.

><p align="center">--IMPORTANT NOTE--</p>
>
>	For a smooth transition between rooms it's better to have 3 rooms activated at once (i.e. one behind the player, one in front of the player, and the room with the player). And the room that is disactivated must be the one that is 1 room behind the player. 
>
>Like this:
><p align="center"><img src="https://github.com/layzyidiot/e-sw/blob/main/images/door-with-rooms.png?raw=true" alt="door" width="50%" height="50%" ></p>

>[!CAUTION]
>
>Try not to create an excessive amount of faces, edges, and vertices as it will decrease the performance of the level.

Info and pictures were taken from the [Tundra Wiki](https://docs.tundra.pitr.dev/guides/optimization)


