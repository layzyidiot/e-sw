# Setting up a checkpoint.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

<b>Checkpoints are usually over looked in levels However , They play an essential part in how levels are played, as dying and starting all over isnt fun.</b>

# Fixing

A problem with checkpoints in spite is their particles as they are an addressable asset, and <span style="color:#FF00FF">Vanity</span> generates a unique <span style="color:red">Spite</span> project everytime... So lets see how to fix them first before anything else.

Firstly locate in <b>FILE EXPLORER NOT UNITY</B> the file named `Checkpoint_0.prefab` and open it with notepad or some text editor and search for `activateEffect` and copy its "m_AssetGUID" field

<img src="https://github.com/layzyidiot/e-sw/blob/main/images/activate.png?raw=true" alt="guid" width="100%" height="100%" >

Go ahead now and find `CheckpointActivate.prefab.meta` now, and change its guid to the one from "m_AssetGUID" field

# Actual usage

<b>Alright lets explain 1 thing, Checkpoints can crash your game. Yes thats right folks! They can <i>if</i> you do it wrong just <i>if</i> you do them wrong.</b>

So lets firstly drag Checkpoint_0 into our scene and we can see some fields, Mainly `Rooms` and `Rooms to Inherit` , but what does this all mean? Well basically, `Rooms` is what gets saved when the scene is loaded, This isnt usually recommended but its there.

<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/creating-checkpoints-checkpoint-settings.png" alt="checkpoint settings" width="50%" height="50%" >

Now `Rooms to Inherit` is what you mainly want to be using, the stuff you assign to it will be saved once you HIT the checkpoint not during the start of the map, Additionally, if you are using this for encounters, Assign the `Stuff` gameobject here

Lastly `To activate` and `Doors To Unlock` , Lets explain `To activate` as it is the simplest , Basically hitting the checkpoint will activate this gameobject , This is useful for optimization if you want to have a massive area full of gameobjects to be disabled before you enter your room , Alright now time for `Doors To Unlock` , Its purpose is to unlock any doors once you enter and an arena and you die, Rememeber the door you assigned in the wave? Yeah, this unlocks it when you respawn so you can go back into the arena