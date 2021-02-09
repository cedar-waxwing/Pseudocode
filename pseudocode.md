Pseudocode for an elevator.

Functionality: As a user, I want to be able to push a button for the floor I wish to arrive at, and be taken to that floor. 

Objects/Data Structures:  
-The elevator itself  
-The control panel in the elevator  
-The control panels outside the elevator  
-The main control mechanism in the elevator maintenance room  
-The wires, pulleys, gears, counterweight, etc that carry out the instructions of the control mechanism.

**Elevator**  

    -Control panel (in elevator)  
        -Array of buttons   
        -Each button needs OnPress function  
        -OnPress, send the number selection from the array to the control mechanism

    -Display screen  
        -Alert floor number using input from control mechanism.

**Control panel (on floors)** 

    -One up, one down button  
    -Each button needs OnPress function  

**Control system (in control room)**  

    -Needs to recieve instructions from buttons (from interior panel and exterior panels)  
    -Needs to monitor which floor the elevator car is on, and send that information to the display screen in the elevator.
    -If the instructions are from the interior panel, take the elevator to the floor the interior panel has indicated  
    -Otherwise, if the instructions are from one of the exterior panels, note which floor the panel is on and whether the request is for an elevator car going up or down. 
    -Utilize an algorithm to decide how to prioritize requests from the interior panel vs exterior panels, and send elevator to floors based on that algorithm.

    
    

Source for how an elevator works: https://www.scientificamerican.com/article/how-do-elevators-work/#:~:text=A%20motor%20at%20the%20top,the%20sheave%20is%20coupled%20directly.

Source on elevator algorithms: 
https://www.popularmechanics.com/technology/infrastructure/a20986/the-hidden-science-of-elevators/

*Some modern elevator systems use a computer station in the lobby that directs passengers to specific elevators based on the floor they select. I've decided to use the standard "up-down" exterior control panel setup for simplicity. 