<h1> Setup a basic arena</h1>
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>


> [!CAUTION]
>Enemies spawn immediately when activated. You must deactivate the enemies before exporting the level, otherwise they will spawn immediately when the room loads, which in most cases, is not what you want.
>
>*You can also intentionally leave enemies activated*. *For example, `P-2` does this with idols, which are always present and don't have a spawn effect*.

> [!TIP]
>It is recommended to use [<span style="color:#ADD8E6">Megga__'s Room creator</span>](https://discord.com/channels/1227272001719111750/1227284829423271957/1243585525613592577) from the discord server as it automatically sets up the basic needed arena and waves.
><img src="https://github.com/layzyidiot/e-sw/blob/main/images/Room%20making.png?raw=true" alt="Megga's room maker" width="65%" height="65%">


# <b>Create a hierarchy like this:</b>

<img src="https://github.com/layzyidiot/e-sw/blob/main/images/1a76e3f8-5149-40c7-ae15-0881c45de244.png?raw=true" alt="Room Hierchy" width="30%" height="30%">

Create as many waves as you want in `Stuff` and add the `Activate Next Wave` component on all of them.

Place non movable/ non interactable stuff such as room geometry into `Non Stuff`

Place your enemies and put them in the wave you want them to be in. Then Disable em, because due to the first note in the page (<b>excluding <span style="color:grey">StatueFake</span> and <span style="color:#bb0200">MannequinPoserWithEnemy</span> Gameobjects </b>), set the wave count of that wave's `Activate Next Wave` to however many enemies there are in the wave. (<b>Note: Some enemies like <span style="color:red">V2</span> and <span style="color:#bb0200">Puppets</span> for some reason dont count as enemies, however you can make them spawn like normal, just dont include them in the enemy count</b>)

In the Trigger, assign the doors of your room to the `Doors` tab. This will automatically lock them when the trigger is passed. Then, assign the first wave's enemies to the `Enemies` tab.

<div style="text-align: center;">
    <img src="https://github.com/layzyidiot/e-sw/blob/main/images/wave.png?raw=true" alt="Trigger Example" width="90%" height="90%" >
</div>

> [!TIP]
>If you wanna see your triggers and whats behind them, set the material of your cube to Enemy trigger material, just be sure to set the gameobject's layer to `Invisible`
>
>Tired of manually assigning each enemy to the next enemy list? Try clicking on your current wave and hitting the hamburger button in the inspector window and pressing lock, Now you can select multiple enemys at once and drag them on top of the list (<b>Note: Drag them on the Next Enemies header, not the size one</b>)

For every wave until the last, set the `Next Enemies` tab of the `Activate Next Wave` to the next wave's enemies (<b>Note: For StatueFake, enable their activator which is a child of them, dont put the StatueFake itself</b>), and dont forget to also set the enemy count!

<div style="text-align: center;">
    <img src="https://github.com/layzyidiot/e-sw/blob/main/images/wave 1.png?raw=true" alt="Waves Middle Example" width="100%" height="100%" >
</div>

When you reach the last wave, leave the `Next Enemies` tab blank, and set the `Doors` tab with the doors you set previously on your Trigger. This will automatically unlock them when the last wave's enemies are killed.

<div style="text-align: center;">
    <img src="https://github.com/layzyidiot/e-sw/blob/main/images/wave 3.png?raw=true" alt="Waves Example" width="75%" height="75%">
</div>

---

# ADVANCED ARENAS

AKA, Waves that allow mutliple waves to exist and when one ends, the other one starts while the 1st one still goes on
As you can read from the above, it's a pretty complicated thing, which is why I'm just linking the Rude docs for them instead of explaining them here.

[Rude Docs](https://coolboi21.github.io/Rude-Docs/#/Tutorials/Beginner/Creating%20Arenas?id=arenastatus) for it.
and there's a [Youtube video](https://www.youtube.com/watch?v=7ZIXvQ0wgmU)