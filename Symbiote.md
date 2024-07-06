<h1>Dual Bosses (Symbiote)</h1>
<i><span style="color:FireBrick; font-size:10px;">Need help? Come to the Envy & Spite Discord server at <a href="https://discord.gg/RY8J67neJ9">https://discord.gg/RY8J67neJ9</a>!</span></i>

To start off, you'll first need 2 enemies with the `Machine` component. <i>This will not work if both enemies do not have the </i>`Machine`<i> component. </i>

# Linking the enemies


First, go to enemy 1's `Machine` component, find the `Symbiote` variable, and assign enemy 2's `Machine` component to that. Repeat the same but for enemy 2.

Example for Enemy 2:

<img src="https://github.com/layzyidiot/e-sw/blob/main/images/Screenshot%202024-06-10%20194055.png?raw=true" alt="Symbiote of Enemy 2">

For the enemies to heal, you require an animation in the enemy animation controller, named "Knockdown". You do not require any special events<span style="color:Grey;">*</span>, make sure it's at least 2 seconds in length. 







Activate them like you would normally, using `Activate Arena` and `Activate Next Wave`.




<span style="color:Grey;font-size:15px;">* I have no fucking clue if it works or not I havent tested it yet</span>

<!-- I couldnt find the "Knockdown" animation. So i cant test this. -Spelar -->