<h1> Setup a basic arena</h1>
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>


>⚠ Warning
>
>Enemies spawn immediately when activated. You must deactivate the enemies before exporting the level, otherwise they will spawn immediately when the room loads, which in most cases, is not what you want.
>
>*You can also intentionally leave enemies activated*. *For example, `P-2` does this with idols, which are always present and don't have a spawn effect*.

<b>Create a hierarchy like this:</b>

- `Room`
- - `Nonstuff`
- - - Place level geometry, lights, and other static stuff such as decor in here.
- - `Stuff` (this should have a `GoreZone` component on it)
- - - `Trigger`
- - - `Wave 1`
- - - `Wave 2`
- - - `Wave 3`


Create as many waves as you want in `Stuff` and add the `Activate Next Wave` component on all of them.

Place your enemies, disable them (<b>excluding StatueFake and MannequinPoserWithEnemy Gameobjects </b>), and put them in the wave you want them to be in. Then, set the wave count of that wave's `Activate Next Wave` to however many enemies there are in the wave. (<b>Note: Some enemies like <span style="color:red">V2</span> and <span style="color:#bb0200
">Puppets</span> for some reason dont count as enemies, however you can make them spawn like normal, just dont include them in the enemy count</b>)

In the Trigger, assign the doors of your room to the `Doors` tab. This will automatically lock them when the trigger is passed. Then, assign the first wave's enemies to the `Enemies` tab. If you have only one wave, make sure to check `Only Wave`.

For every wave until the last, set the `Next Enemies` tab of the `Activate Next Wave` to the next wave's enemies. 

When you reach the last wave, leave the `Next Enemies` tab blank, enable `Last Wave`, and set the `Doors` tab with the doors you set previously on your Trigger. This will automatically unlock them when the last wave's enemies are killed.

<b>Example of a hierarchy:</b>

- `Room`
- - `Nonstuff`
- - - Level Geometry
- - `Stuff`
- - - `Door`
- - - `Door`
- - - `Enemies`
- - - - `Trigger`
- - - - `Wave 1`
- - - - - `Mindflayer`
- - - - `Wave 2`
- - - - - `Streetcleaner`
- - - - `Wave 3`
- - - - - `SwordsmachineNonboss`