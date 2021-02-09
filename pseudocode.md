Pseudocode for an elevator.

Functionality: As a user, I want to be able to push a button for the floor I wish to arrive at, and be taken to that floor. 

Objects/Data Structures:
-The elevator itself
-The control panel

-Elevator
    -Control panel (in elevator)
        -Array of buttons 
        -Each button needs OnPress function
    -Display screen
        -Alert floor number
-Control panel (on floors)
    -One up, one down button
    -Each button needs OnPress function
-Control system (in control room)
    -Needs to recieve instructions from buttons (from interior panel and exterior panels)
    -If the instructions are from the interior panel, take the elevator to the floor the interior panel has indicated
    -Otherwise, if 

    
    

Source for how an elevator works: https://www.scientificamerican.com/article/how-do-elevators-work/#:~:text=A%20motor%20at%20the%20top,the%20sheave%20is%20coupled%20directly.

*Some modern elevator systems use a computer station in the lobby that directs passengers to specific elevators based on the floor they select. I've decided to use the standard "up-down" exterior control panel setup for simplicity. 