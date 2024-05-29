# Object activator and what they do.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

Howdy user! This is one of the most important tools under your belt of ultrakill scripts, it allows you to simpily activate a gameobject when the gameobject that has this script is activate (a chain) ***OR*** The most important part: Triggering stuff if you have a box collider thats set to a trigger within the same gameobject that has the script.
But thats not all! It has 2 overrideable methods, But what does that mean? It means you can go to the `OnActivate()` (<b>which gets called when the gameobject is fired (similarly, the `OnDisActivate` gets called after the gameobject is disabled or the player walks out of a trigger(?)) , such as walking into a trigger or it being active</b>) list, add a gameobject to it, and run a public method from one of the scripts of the gameobject, This is really useful in alot of scenarios where you want lets say for an example, a breakable to break during a wave but make it so the player cannot break it before then.

<div style="text-align: center;">
	<figure>
		<img src="https://coolboi21.github.io/Rude-Docs/Components/assets/obj-activator-component.png" alt="Object Activator" width="50%" height="50%">
		<figcaption>Example image of Object Activator script</figcaption>
	</figure>
</div>

---

# Behaviour

This script has 2 behaviours.

* If it has no Box Collider, Activate the objects and run the `OnActivate()` method.
* If there is, Activate the objects and run the `OnActivate()` **ONCE** the player enters the trigger.

---

# Fields

<h3>One Time</h3>

From the name, this means the gameobject can be activated only once, Further Reactivation of the gameobject (such as rewalking into trigger or activating it and disactivating it) Wont trigger anything else if this field is set to true.

<h3>Disable on Exit</h3>

This might seem complicated at first but its really easy, Basically reverses the statements once the player walks out of trigger or the gameobject getting disabled.

Example: `To Activate Object` has its objects disactivated once the player walks out of the trigger or the gameobject gets disabled and objects under `To Dis Activate Objects` become active, and On `Dis Activate()` events run.

<h3>Dont Activate On Enable</h3>

If this is enabled, events will not be activated when the object becomes active.

### Reactivate On Enable
This is required for non-trigger based Object Activators. If you want to run the events every time the Game Object becomes active, this has to be enabled, even if `One Time` is not ticked.

### Delay
Events will ran after specified amount of time in seconds. Can use decimal numbers. This can be cancelled if the Object Activator gets deactivated 

### OBAC 
Requires a Game Object that has an Object Activation Check component on it. Basically an "If" Statement, So if gameobject 1 is active, we run the activate method, if its not, dont run it until it becomes true.

### For Enemies
If the Game Object that has an Object Activator also has a trigger on it, it will only be able to be triggered by enemies. This is maybe useful for scenes.

---

This gameobject runs a [ULTRAKILL Event](ULTRAKILL-Event)