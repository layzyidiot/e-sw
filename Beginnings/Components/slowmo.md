# Setting up Slowmos.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

Slowmos are such cool things in ultrakill, but they can be sometimes complicated, We will simplify how they work on this page.

# Behaviour 

They work on unity's timescale system where once the component becomes active, it sets it to the value specified and speeds up the game after a bit

* When it is set to one, The game runs normal.
* When it is set to 0.5, The game runs at half speeds
* When it is set to 0.25, the game runs at quarter of its speed, This is usually a sweet spot when using Slowmos

# Setup

We will create a trigger that when the player enters, slows the game down, First start by creating an empty gameobject in the scene by `CTRL + SHIFT + N`.

Select it and add the `SlowMo` component to it, Set the amount field to the amount you want to slow down the game to, 0.25 is usually a sweet spot

<img src="https://coolboi21.github.io/Rude-Docs/Components/assets/slomo-component.png" alt="slowmo settings" width="100%" height="100%" >

Alright now drag this gameobject into your assets window.

---

Now we will create the trigger to activate it, Add a box collider and make sure its set to a trigger, then we add a `Object Spawner` component to it where we set the spawnables list to 1 and drag in the previously created slow mo gameobject FROM ASSETS! NOT THE SCENE! 

And attach a `Object Activator` component to it and in the `OnActivate` method, we select the same gameobject that has these 2 scripts, where we click on "No Function" and set it to `ObjectSpawner.SpawnObject(int)` leaving the int as 0.

<img src="https://coolboi21.github.io/Rude-Docs/Components/assets/obj-activator-slomo-tut.png" alt="activator slowmo" width="75%" height="75%" >


It isnt recommended to do this but you can also add this to waves (they already slow down the game on finish) by removing the box collider trigger and adding it to the last wave's "To activate" list

--- 

Credits to eternalunion and luka for the images from the rude wiki
