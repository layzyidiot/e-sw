# Checkpoint Setup

<i><span style="color:FireBrick; font-size:20px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>
# Functionality
<img align="right" src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/creating-checkpoints-checkpoint-settings.png" alt="checkpoint settings" width="50%" height="50%" >

* Force Off
	* Forcefully turns the checkpoint off.
	* Ideal to use this over just deactivating the checkpoint, as it can break checkpoints otherwise if 2 reset the same object.
   	* Use the `SetForceOff()` event to turn this on/off on runtime.
* Rooms
	* List of objects to be reset <i><b>on the level being loaded</b></i>.
* Rooms To Inherit
	* List of objects to be reset <i><b>on the checkpoint being hit</b></i>.
>[!TIP]
>Wrong placement of an object between `Rooms` and `Rooms To Inherit` is an easy way to cause a <b>Sequence Break</b> in a level, where you can trigger certain events under conditions that aren't intended. Think about what you're resetting and how it can be abused by passing through the checkpoint at the wrong time(or not at all).
>[!CAUTION]
>References to objects in `Rooms` and `Rooms To Inherit` will break because the checkpoint activates clones of them on runtime. The `Arena Status`  script can solve issues between static/nonstuff -> gorezone.
* Doors To Unlock
	* List of objects with `Door` script to be unlocked <i><b>on respawn</b></i>.
* Multi Use
	* Regenerates the checkpoint after going through it (Use the `CheckpointReusable` prefab).
* Dont Auto Reset
	* Prevents the checkpoint from immediately activating(in cases where you'd want to call the `ResetRoom()` and `InheritRoom()` events manually).
* Start Off
	* Checkpoint object is deactivated on scene load.
* Unteleportable
	* Removes checkpoint from list of checkpoints to teleport to in the cheats menu.
* Invisible
	* Hides checkpoint graphic.
	* Can be toggled on runtime with `SetForceOff()` event.
* On Restart()
	* List of UnityEvents to be called when the player respawns.
>[!CAUTION]
>Checkpoints can only be parented to empty objects at `0,0,0` position.

# Pitfalls
Checkpoints can break if they dont have the following:
* Object in `To Activate:
	* There must be a gorezone on your object.
* Object in `Rooms` <b>OR</b> `Rooms to Inherit`:
	* There must be gorezones on each of your objects in `Rooms` or `Rooms to Inherit`.
 	* Objects cannot contain other checkpoints in them.
>[!WARNING]
>In some cases, having <a href="https://docs.unity3d.com/Manual/StaticObjects.html">static flags</a> on an object that gets reset can cause issues with the checkpoint. Generally, if an object has static flags, it shouldn't be changing and need to be reset in the first place.
