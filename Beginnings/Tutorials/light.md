# Setting up lighting.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

<b>In this page we will be covering 2 important things about lights, The lights themselves and skyboxes</b>

But before that you must know a *few* things.

1. Different ultrakill shaders have different uses (suprising, i know)
2. Ultrakill's shaders are vertexlit, meaning they are lit in a way that simulates the way old games were made, which means the more vertices your object has, the more smoother the lighting will be but that leads to less performance.
3. Due to the previous point, What you see in the editor will never be the same in the game, you must see for yourself.
4. Due to how the shaders were coded, If a object is affected by more than 8 lights it will begin to flicker

<div style="text-align: center;">
	Heres how lighting looks like the in editor (left) vs in game (right)
	<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-vertexlit-example.png" alt="Lighting in game" width="90%" height="90%" >
</div>

> [!NOTE]
> Do note that when creating custom materials/textures, ALWAYS SET THEIR SHADER TO VERTEXLIT/VERTEXLIT! If you use the standard unity shader it will look bad.

# Creating light sources and their different use cases

To create a light source right click in the scene menu and hit light and choose what you need.

<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-creating-a-light.png" alt="Creating light" width="70%" height="70%" >

---

1. Point light

<div style="text-align: center;">
	<figure>
		<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-lightingtypes-point.png" alt="Point light" width="50%" height="50%">
		<figcaption>This bad boy right here lights up everything in a nice round circle, it is one of the most versatile and common lights used in almost every single ultrakill level</figcaption>
	</figure>
</div>

---

2. Spot light

<div style="text-align: center;">
	<figure>
		<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-lightingtypes-spot.png" alt="Spot light" width="50%" height="50%">
		<figcaption>Lights up a certain area like its real version.</figcaption>
	</figure>
</div>

---

3. Directional light

<div style="text-align: center;">
	<figure>
		<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-lightingtypes-directional.png" alt="Directional light" width="50%" height="50%">
		<figcaption>Simliar to the sun, it casts its light globally across the entire level, it can be used to light an entire level (might make it look bad) or a simulate a very strong light in one direction.</figcaption>
	</figure>
</div>

---

# SkyBoxes

<b>Ah, what a beautiful day, the birds are shining, the sun is singing... wait something is wrong?</b>

To add a skybox, right click in your assets and hit material and set its shader to one of the shaders in skyboxes tab or ultrakill's skybox shaders (if you can find them)

<div style="text-align: center;">
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/skybox.png?raw=true" alt="Shaders for skyboxes" width="30%" height="30%" >
	<img src="https://github.com/layzyidiot/e-sw/blob/main/images/skybox2.png?raw=true" alt="Shaders for skyboxes" width="32.5%" height="32.5%" >
</div>

After that, From the toolbar, Go to `Window > Rendering > Lighting Settings`

<div style="text-align: center;">
	<img src="https://coolboi21.github.io/Rude-Docs/Tutorials/Beginner/assets/lighting-101-scene-tab.png" alt="Creating light" width="70%" height="70%" >
</div>

Drag the material you created into the materials field

> [!TIP]
> You can change how the skybox affects the lighting in the level via `Intensity Multiplier`, setting to 0 disables the skybox from effecting the lighting, This field can be also used to create <b>Fog</b> in your level.
