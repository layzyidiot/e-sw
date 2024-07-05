# Fixing broken enemies
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

*Some enemies due to the extraction process via <span style="color:#FF00FF">Vanity</span> are broken. However, we can fix them via easy and somewhat simple solutions. Most commonly broken enemies are the `Sisyphean Insurrectionist` and the `Mindflayer`.*

# Fixing Sisyphean Insurrectionist
it has a broken IK (<i>Inverse Kinematics</i>) component so click on the Insurrectionist (<i>known as Sisyphus</i>) prefab and press `Open Prefab`. Find the missing script and remove it.

Then, scroll down and find the `Add Component` button, where you wanna search for `Fabric Solver 3D` and copy the following settings from the image below.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/sisyphus1.png?raw=true" alt="Fabrik Solver 3D" width="50%" height="50%">
	</figure>
</div>

You want to make sure hand.L.006 is the 2nd to last one, not the last one (Look at the below image).

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/sisyphus2.webp?raw=true" alt="Hand.L.006" width="30%" height="30%">
	</figure>
</div>

---

# Fixing Mindflayer

Mindflayer is different and somewhat harder to fix than the original Sisyphean Insurrectionist.

Mindflayer, similar to the [Checkpoint](https://layzyidiot.github.io/e-sw/#/checkpoints?id=fixing), requires fixing Asset GUIDs.

Start by going to `PrefabInstances` in your project and find `Mindflayer.prefab`. Open it with a text editor such as <i>Notepad++</i>, search for `deathExplosion` and copy the `m_AssetGUID`'s value. Now, search inside of `PrefabInstances` for `Explosion Mindflayer.prefab.meta` <b>META FILE, NOT PREFAB!</b> And paste in the GUID you copied from the Mindflayer prefab.

Now, go to `Assets\ULTRAKILL Assets\ExportedProject\Assets\Scripts\Assembly-CSharp` and find `Mindflayer.cs`. Open it with a text editor and delete the line containing `HideInInspector` above the active field.

From the image below, you're gonna want to copy every value you can to your version of the Mindflayer prefab. Most of these prefabs are from your project's assets except for `Model` , Everything under `Tentacles` , `Right Hand` , `Charge Particle` , `Original Glow` and `Enrage Glow`. You might notice the color down below `Enrage Glow`. The value for the blue color is **PLACEHOLDER**

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/mindflayer1.png?raw=true" alt="Mindflayer Script" width="35%" height="35%">
	</figure>
</div>

Now as for `Tentacles`, lock the inspector and drag as following into the `Tentacles` list -

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/mindflayer2.png?raw=true" alt="Mindflayer Hierarchy" width="50%" height="50%">
	</figure>
</div>

---

If theres any other enemies that need fixing, let us know in the [<b>discord server</b>](https://discord.gg/RY8J67neJ9).
