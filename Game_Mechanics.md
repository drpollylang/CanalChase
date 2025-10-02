* Motion \- the player controls a narrowboat using arrow keys that moves along a twisting canal route. Since damage is incurred when hitting the sides, the game can increase difficulty by moving the chase to twistier sections of the canal.  
* Physics \- the boat has some momentum in the water, so hard breaks and turning requires some dexterity.  
* Canal-side scenery \- although the canal is the only traversable space, there is a pastoral landscape visible alongside including (potentially) trees, paths, fields and pubs.   
* Damage \- damage increments over time regardless of what the player does, but increases more rapidly when hitting sides or obstacles. When damage reaches a limit, say 10, the player boat breaks down and they must stop for (say) 10 seconds and fix it. However the player may at any time stop for a smaller length of time, say 3 seconds, for maintenance, resetting the damage counter to 0\. The player could trigger this repair stop by pressing a key. The player thus needs to factor maintenance stops into their strategy to avoid taking a bigger time penalty at a time that is less of their choosing.  
* Locks \- locks are a natural hazard which periodically “open” and then shut for a while; while they are shut, neither player nor pursuer can pass them. Players are thus incentivised to time their arrival at locks so that they can get through, and the pursuer must wait on the other side. If the player enters the lock with the pursuer, they lose. (Does the water level rise and fall automatically at a constant rate, or is it triggered by input from the player e.g. pressing a key?)  
* Fuel and Chandleries \- your narrowboat runs out of fuel as you go (fuel remaining is represented by a bar). “Chandleries”, waterside supply shops, are places where you can stop and refuel. Stopping to refuel costs time, says, 3 seconds.   
* Pursuit \- the player's boat is pursued by an opponent boat. The speed, targeting accuracy and maneuverability of the opponent boat varies based on the level.  
* Levels \- the number of hazards (e.g. locks), damage sustained over time and by collisions, speed and maneuverability of the pursuing boat, and fuel efficiency vary based on the level. For example, level 1 might represent a ‘tutorial’ level in which there are no hazards, and damage accrued very slowly, in order to accustom to player to the game mechanics.

* Motion & Physics  
  * player controls a narrowboat using arrow keys   
  * the boat is on water and it has inertia  
    * the acceleration and deceleration   
      * must not be sharp  
      * must depend on the size/weight of the boat that the player selects	  
        * implies that there would be several different types of boats  
  * water may have current	  
    * current may hinder the controls/deflet the initial direction of the movement of the boat  
      * i.e. if the user does not provide any input, the model of the boat may move on its own along the direction of the current  
      * in other words, the base motion speed and direction  
  * inclement weather  
    * mechanic similar to the water current  
  * maneuvering ideas  
    * shooting ropes to hook up to a side road pillar or smt ot maneuver through tight corners  
    * releasing anchors to make a sharp and rapid U-turn  
* Boat damage  
  * When the playable model touches the side of the canal, HP is deducted from the player  
  * When the playable model touches other boat models, HP is deducted from the player and from the models that were hit  
    * Other models may include boats, rocks, sign posts, police boat that chases you  
  * The amount of HP that is deducted may depend on   
    * the speed at which the collision occurred (high/low)  
    * the trajectory of the boat during the collision (head on vs 45 degree angle vs scratching the side of the boat)  
  * Passive damage  
    * A relatively small amount of health points deducted at random point during the game play  
* Boat repair  
  * *When damage reaches a limit, say 10, the player boat breaks down and they must stop for (say) 10 seconds and fix it.*   
  * *However the player may at any time stop for a smaller length of time, say 3 seconds, for maintenance, resetting the damage counter to 0\.*   
  * *The player could trigger this repair stop by pressing a key.*   
  * *The player thus needs to factor maintenance stops into their strategy to avoid taking a bigger time penalty at a time that is less of their choosing.*  
* Checkpoints (in the form of locks)  
  * *locks are a natural hazard which periodically “open” and then shut for a while;*   
    * *while they are shut, neither player nor pursuer can pass them.*  
    * *Players are thus incentivised to time their arrival at locks so that they can get through, and the pursuer must wait on the other side.*  
    * *If the player enters the lock with the pursuer, they lose.*  
* The chaser boat (or figuring out the artificial intelligence)  
  * It should automatically   
    * be incentivised to chase the model boat of the player  
    * navigate through the canal  
      * I.e. avoid the borders and in canal objects (other boats signposts etc.)  
    * may replicate the repair behaviour (but that’s a good to have, not must have)  
    * when reaching the model of the player’s boat, should display the “catching” behaviour  
      * within a predetermined distance, start an animation of ropes being thrown at the players boat   
        * the more the ropes, the harder for the harder it is for the player to get away (the player slows down)  
      * When both boats come to a stop \-\> game over  
* Delivering and balancing the goods/containers   
  * A narrow boat may have container on the deck  
    * Striking the boat against obstacles throws the containers in the canal  
      * Can either retrieve them (spend time) or leave them and run away from the pursuer  
    * The more cargo you deliver, the more points/game currency you achieve  
      *  Therefore, next time you could spend it on something (e.g. more fuel/faster repairs)  
      * *Resource considerations tied to an economic score \- you might have money to spend on cargo, fuel, heating and food, and have to balance these.*  
* The boat fuel game mechanics  
  * ???  
* The map of the canal   
  * ???  
  * make it twisty?  
  * should it be randomly generated based on predetermined patterns (like in No Man's Sky)  
* The model of the boat  
  * The model of the boat should change depending on the direction of the voluntary movement (i.e. when the boat is affected by e.g. a current, then the model does not change)  
  * Should we add a pre-game/minigame to allow the user to design/modify the boat  
    * *Narrowboats of different length with different advantages \- longer ones may struggle more around corners but be able to carry more fuel or power-ups.*  
* Singleplayer vs multiplayer  
  * The multiplayer allows for the simultaneous input from 2 users  
    * The main challenge: figure our the best way to implement this  
      * 2 keyboards vs 1 keyboard vs 2 gamepads  
      * does p5.js even allow for this?  
  * Split screen vs 2 separate screens  
    * Is it possible?  
    * if split screen,  what are the hardware limitations?  
      * Playing on a small screen is probably not going to be viable 
