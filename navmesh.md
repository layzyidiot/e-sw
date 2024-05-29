# Setting and baking navmesh.
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

What is navmesh? A navmesh, short for navigation mesh, its commonly used in video games as a better path finding way instead of drawing a line going to the player or point A to point B performance wise, You could say its a representation of walkable Areas,  navmeshes divides the game's world into a mesh of interconnected quads and faces where the AI can understand where it goes to.

---

# HOW TO BAKE NAVMESH

Baking navmesh into the scene is pretty straight foward, To start, Click on the `Window` button in Unity's toolbar and go to `Window -> AI -> Navigation`

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/navmesh1.png" alt="Hand.L.006" width="90%" height="90%">
	</figure>
</div>

Afterwards you are gonna see this menu after clicking on `Navigation`.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/navmesh2.png" alt="Hand.L.006" width="40%" height="40%">
	</figure>
</div>

---

Make sure to select every place you plan your enemies to walk on, AND MAKE SURE TO MARK IT STATIC IN THE MENU! Oh and dont forget the important step of marking whether the gameobject is a floor or a wall + setting what layer it is, Such as enviroment for indoor gameobjects, and outdoors for outdoors gameobjects. 

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/navmesh3.png" alt="Hand.L.006" width="90%" height="90%">
	</figure>
</div>

Finally Once you are done, It is time to bake our navmesh, Head to the bake tab and hit bake.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/navmesh4.png" alt="Hand.L.006" width="40%" height="40%">
	</figure>
</div>

---

In conclusion, Navmesh is an important thing in a scene as it allows a enemy to know where it needs/wants to walk from place A to place B and without it, enemies become stupider than jupiter.