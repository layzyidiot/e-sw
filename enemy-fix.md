# Fixing some enemies.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

Sadly, Some enemies due to the extraction process via <span style="color:#FF00FF">Vanity</span> are broken, However, we can fix them via easy and somewhat simple solutions. Noteable examples of broken enemies are like `Sisyphiean Insurrectionist` , and `Mindflayer`

# FIXING SISYPHIEAN INSURRECTIONIST

Firsty, it has a broken script so click on Sisyphus prefab and hit `Open prefab`, Proceed to find the missing script and click the hamburger menu and click remove script

Secondly, scroll down and find the `Add component` button, where you wanna search for `Fabric Solver 3D` and copy the following settings from the image bellow.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/sisyphus1.png?raw=true" alt="Fabrik Solver 3D" width="50%" height="50%">
	</figure>
</div>

You want to make sure hand.L.006 is the 2nd to last one, not the last one (Look at the bellow image).

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/sisyphus2.webp?raw=true" alt="Hand.L.006" width="30%" height="30%">
	</figure>
</div>

---

# FIXING MINDFLAYER

Oh boy, Mindflayer is quite different and somewhat harder than the original Sisyphiean Insurrectionist, But Mindflayers are indeed important enemies, so we must fix them.

Remember [This](https://layzyidiot.github.io/e-sw/#/checkpoints?id=fixing) part in the wiki? Basically mindflayer has that too, Lets explain what to do.

Start by going to `PrefabInstances` in your project and find `Mindflayer.prefab` where you wanna open it with a text editor and search for `deathExplosion` and copy the `m_AssetGUID`'s value, Now search inside of `PrefabInstances` for `Explosion Mindflayer.prefab.meta` **IT MUST BE THE META!** And paste in the guid you copied from the mindflayer.

We're not done yet, Go to `Assets\ULTRAKILL Assets\ExportedProject\Assets\Scripts\Assembly-CSharp` and find `Mindflayer.cs` where we want to delete the line `HideInInspector` above the active field, Now we are done with the file editing, its time for asset assigning in the editor.

From the image bellow, you're gonna want to copy every value you can, Most of these prefabs are from your project's assets except for `Model` , Everything under `Tentacles` , `Right Hand` , `Charge Particle` , `Original Glow` and finally `Enrage Glow` , You might notice the color down below `Enrage Glow` The value for the blue color is **PLACEHOLDER**

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/mindflayer1.png?raw=true" alt="Mindflayer Script" width="35%" height="35%">
	</figure>
</div>

Now as for `Tentacles` , Lock the inspector and drag these into the `Tentacles` list.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/mindflayer2.png?raw=true" alt="Mindflayer Hierarchy" width="50%" height="50%">
	</figure>
</div>

---

In conclusion these enemies are needed in every ultrakill level but sadly <span style="color:#FF00FF">Vanity</span> breaks them. If theres any enemies that need fixing, let me know in the [<b>discord server</b>](https://discord.gg/RY8J67neJ9).