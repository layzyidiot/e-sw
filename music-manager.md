# Setting up MusicManager
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

# Beginning

Every good ultrakill level has to have music, Other wise it would be very bland fighting enemies.

`MusicManager` Is a gameobject thats a child of `StatsManager` its job is very apparent from it's name, It manages music in the level, Specifically Clean music and Combat music and music for bosses.

If you used the statsmanager prefab from the [Basic Scene Setup](new-scene), it should be already set, and all you have to do is make `MusicChanger` triggers. But before that, Lets explain each field of `MusicManager`.

---

# Fields

* **Off** - Exactly what you think, just disabled or enables music in the level.

* **Volume** - Is a floating point variable where 1 is full blast and 0 is none, For example if i want the volume in my level to be half that of its original volume (maybe via a object activator) , I'd change the volume variable to `0.5`.

- **filtering** - is a variable declared in Update() — it's a high pass filter
- **arenamode** - is a variable representing the state of the arena — if it has enemies, a boss?, or if it's clean.
- **allThemes** - is an array of the following themes:
    - `cleanTheme`
    - `battleTheme`
    - `bossTheme`
    - *`targetTheme`*
        - Before any music is played, `targetTheme` is set to `None`, this is because none of the themes are actually played. Instead, they are copied to `targetTheme` when needed.
    - These are the 3 (*excluding targetTheme*) AudioClips declared in `MusicManager`.

- **allTheme** - is the variable used in the array `allThemes`.
- **forcedOff** - is a variable used in functions such as `ArenaMusicStart()`, `ForceStartMusic()`, `ForceStopMusic()`, etc.
- **dontMatch** - is a variable used in functions such as `PlayBattleMusic()`,  `PlayCleanMusic()`, etc.
- **requestedThemes** - is the variable used to represent the amount of themes are required to be changed in the functions `PlayBattleMusic()`, `PlayCleanMusic()`, and `ArenaMusicEnd`.

---

# Functions

The rude docs has way too many functions here so ill simplify it here by explaining at most what you would probably want to do with music in your level.

- `StartMusic()` - if the variable `forcedOff` is `true`, don't do anything. Start every declared theme at 0:00, turn the `off` variable to `false`, change cleanTheme's volume to the volume declared in `MusicManager`.

- `StopMusic()` - the variable `off` is set to `true` and using the allTheme array, the volume of each theme is set to 0, and then the `AudioSource(s)` are stopped.

- `PlayBossMusic()` 
    - If the `targetTheme` isn't equal to `bossTheme`, set `bossTheme's` time to `cleanTheme's` time.
    - Set the `targetTheme` to `bossTheme`.

---

# Actually Using Music Changer

Finally, We are gonna explain how to change and play music in your levels, I hope this section is way more comprehendable than the graph over at the rude wiki.

We are gonna start by creating an empty gameobject and then we'll add a box collider component to it and setting it to be a trigger, then we're going to hit `Add Component` and search for the `MusicChanger` component,

<div style="text-align: center;">
	<figure>
		<img src="https://github.com/layzyidiot/e-sw/blob/main/images/music.png?raw=true" alt="Music Changer" width="50%" height="50%">
		<figcaption>As you can see, there are 3 fields that we can add AudioClips to, Basically, Clean is for when no enemies are present, Combat is for when there is and Boss is for any enemy with a boss bar appears.</figcaption>
	</figure>
</div>	

Now you may realize that in the previous fields section, i havent talked about a few fields like `Match` or `OnEnable` well thats because i was saving them up for this section, Ill explain each purpose of each one.

- `Match` - is used if you already have music in your level playing and you want to switch to a different version on it **WHILE ALSO** matching the play time from the original song to the 2nd one, An example of this is a boss changing his music during him getting knocked down.

- `OnEnable` - is used for just, enabling stuff when the music starts. i really dont understand why this exists even?

- `OneTime` - makes the trigger only fire the music once, This is recommended to be turned on as having the music restart everytime you exit and enter the trigger isnt fun on the ears.