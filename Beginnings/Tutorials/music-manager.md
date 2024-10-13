# Setting up MusicManager
<i><span style="color:FireBrick; font-size:20px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

Every good Ultrakill level has to have music, Otherwise it would leave levels bland and unexciting.

`MusicManager` Is a gameobject thats a child of `StatsManager` its job is very apparent from it's name, It manages music in the level, Specifically Clean music and Combat music and music for bosses.

If you used the statsmanager prefab from the [Basic Scene Setup](new-scene), it should be already set, and all you have to do is make `MusicChanger` triggers. But before that, let's explain each field of `MusicManager`.

---

# Fields

* **Off** - Exactly what you think. It disables or enables music in the level.

* **Volume** - is a floating point variable where 1 is full blast and 0 is none, For example if you want the volume in your level to be half that of it's original volume (commonly via an object activator), you'd change the volume variable to `0.5`.

- **filtering** - is a variable declared in Update() — it's a high-pass filter
- **arenamode** - is a variable representing the state of the arena — if it has enemies, a boss?, or if it's clean.
- **allThemes** - is an array of the following themes:
    - `cleanTheme`
    - `battleTheme`
    - `bossTheme`
    - *`targetTheme`*
        - Before any music is played, `targetTheme` is set to `None`. This is because none of the themes are actually played. Instead, they are copied to `targetTheme` when needed.
    - These are the 3 (*excluding targetTheme*) AudioClips declared in `MusicManager`.

- **allTheme** - is the variable used in the array `allThemes`.
- **forcedOff** - is a variable used in functions such as `ArenaMusicStart()`, `ForceStartMusic()`, `ForceStopMusic()`, etc.
- **dontMatch** - is a variable used in functions such as `PlayBattleMusic()`,  `PlayCleanMusic()`, etc.
- **requestedThemes** - is the variable used to represent the amount of themes are required to be changed in the functions `PlayBattleMusic()`, `PlayCleanMusic()`, and `ArenaMusicEnd`.

---

# Functions

*Note: This is a shortened list of all functions avalible to `MusicManager`.*

- `StartMusic()` - if the variable `forcedOff` is `true`, don't do anything. Start every declared theme at 0:00, turn the `off` variable to `false`, change cleanTheme's volume to the volume declared in `MusicManager`.

- `StopMusic()` - the variable `off` is set to `true` and using the allTheme array, the volume of each theme is set to 0, and then the `AudioSource(s)` are stopped.

- `PlayBossMusic()` 
    - If the `targetTheme` isn't equal to `bossTheme`, set `bossTheme's` time to `cleanTheme's` time.
    - Set the `targetTheme` to `bossTheme`.

---

# Actually Using Music Changer

Finally, we are going to explain how to change and play music in your levels, I hope this section is way more comprehendable than the graph over at the rude wiki.

Start by creating an empty gameobject and then add a box collider component to it and set it to be a trigger. Select `Add Component` and search for the `MusicChanger` component.

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/music.png?raw=true" alt="Music Changer" width="50%" height="50%">
		<figcaption>As you can see, there are 3 fields that we can add AudioClips to, Basically, Clean is for when no enemies are present, Combat is for when there is and Boss is for any enemy with a boss bar appears.</figcaption>
	</figure>
</div>	

You may realize that in the previous fields section, the fields like `Match` or `OnEnable` were missing. They are going to be discussion in this section.

- `Match` - is used if you already have music in your level playing and you want to switch to a different version on it **WHILE ALSO** matching the play time from the original song to the 2nd one. An example of this would be the music progression upon the second Cerberus' awakening in 0-5

- `OnEnable` - is used for just, enabling stuff when the music starts. i really dont understand why this exists even?

- `OneTime` - makes the trigger only start the music once. This option is recommended to be left on as music restarting upon each trigger activation is rarely desired.
