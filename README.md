# Unity NPC AI
This is a short project created on Unity focused on a smart enemy AI. It was made for a college assignment on a few days using **C# language**.
The enemies also use **Unity NavMesh** to create walking paths thru the map.

# Enemy behaviour
Here are all the enemy behaviours implemented on the game.

## Patrol State
The enemy default state is the **patrol state.** On this mode, he has to reach the current point declared on an array of **Vector3 positions.** The guard keep repeating the path until something changes his state.
// GIF DO INIMIGO ANDANDO

## Soft Search State
The player can throw a tuna can on the floor to get the guards attention. If any enemy is on the specified range when the object makes the sound, he enters in a **soft search state.** In this mode, he walks to the object, stop, and look around searching for any suspicious activity. If he doesn't find any, he goes back to the *patrol state.*
//GIF DO INIMIGO EM SOFT SEARCH

## Chase State
There are two situations that can trigger the **chase state:**
- The player is **seen by the guard.** This detection is made using Unity **Raycast.** With the raycast, the enemy keeps checking for collisions in front of him on a specified range.
- The player is **heard by the guard.** This happens when the player walks near to the enemy. Inside the guard script there is a specified distance that is considered for this to happen.
In the chase state, the enemy **destination** is set to the player current position.
//GIF DO INIMIGO EM CHASE STATE

## Hard Search State
If the player is out of enemy sight, the guards start enter in the **hard search state.** When chasing, the enemies store the *last player known position* every 0.2 seconds. With this information, he can go to that last position when he enters this new state. When the enemy reaches the last player known position, he starts to look around and walk near the spot trying to find the player.
When a guard enters this state, he also warn other guards near him about the situation, making them enter on a hard search state too.
//GIF DO INIMIGO EM HSS

# Prototype
This game prototype can be played on browser in itch.io: https://npcproductions.itch.io/sck981-demo
