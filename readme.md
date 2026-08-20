# Arcade game

Input handling

Plug the encoder board into the Pi via USB
Use pygame.joystick to detect it and read axis values (joystick position) and button states (shoot)
Arcade joysticks are often digital (4 or 8-direction) rather than true analog, so the axes may report as fixed values (-1, 0, 1) rather than smooth ranges — worth testing first with a simple script that prints joystick input so we know what we're working with

Crosshair

Track crosshair position as x/y coordinates, moved by joystick input each frame
Clamp it so it can't move off-screen

Enemies

Spawn enemies at random positions on a timer (e.g. one every 1-2 seconds), using a list to track active enemies
Move them toward the center or along a path each frame
Increase spawn rate over time to ramp difficulty

Shooting and collision

On button press, check if the crosshair position overlaps any enemy's hitbox
Remove hit enemies, add score
Track how many enemies are currently alive on screen

Lose condition

If the number of active enemies exceeds some threshold (or an enemy reaches the player/edge), trigger game over
