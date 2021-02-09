Pseudocode for an elevator.

Functionality: As a user, I want to be able to push a button for the floor I wish to arrive at, and be taken to that floor in a reasonable amount of time. 

Objects/Data Structures:  
-The elevator car itself  
-The control panel in the elevator  
-The control panels outside the elevator  
-The main control mechanism in the elevator maintenance room  
-The wires, pulleys, gears, counterweight, etc that carry out the instructions of the control mechanism.  
-Elevator control algorithm  
-Passenger -- a person pressing the buttons and riding in the elevator car  


**Elevator car**  

    -Control panel (in elevator)  
        -Array of buttons   
        -Each button needs OnPress function  
        -OnPress, send the number selection from the array to the control mechanism  

    -Display screen  
        -Alert floor number using input from control mechanism.

    -Door opening mechanism
        -On arrival to its destination floor, the doors should open. 
        -Otherwise, the doors should never open
        -Need a safety feature to ensure the doors never open between floors

**Control panel (on floors)** 

    -One up, one down button  
    -Each button needs OnPress function  
    -OnPress, tell control system that the button's floor is requesting an elevator car, and indicate in which direction (up or down) they are requesting a car.
    -Also -- OnPress, the button should light up and stay lit until the elevator car arrives

**Control system (in control room)**  

    -Needs to recieve instructions from buttons (from interior panel and exterior panels)   
    -If the instructions are from the interior (car) panel, take the elevator to the floor the interior panel has indicated    
    -Otherwise, if the instructions are from one of the exterior panels, note which floor the panel is on and whether the request is for an elevator car going up or down.   
    -Then, utilize an algorithm to decide how to prioritize requests from the interior panel vs exterior panels, and send elevator to floors based on that algorithm.  
    -Needs to monitor which floor the elevator car is on, and send that information to the display screen in the elevator.  
    -Needs a mechanism for manual override by operators such as the fire department  
    -Needs specific emergency protocols. 

Source for how an elevator works: https://www.scientificamerican.com/article/how-do-elevators-work/#:~:text=A%20motor%20at%20the%20top,the%20sheave%20is%20coupled%20directly.

Source on elevator algorithms: 
https://www.popularmechanics.com/technology/infrastructure/a20986/the-hidden-science-of-elevators/

*Some modern elevator systems use a computer station in the lobby that directs passengers to specific elevators based on the floor they select. I've decided to use the standard "up-down" exterior control panel setup for simplicity. 

From *Popular Mechanics*:

"The...simplest reasonable approach to elevator dispatching is still surprisingly common. Known as “collective control,” or simply “the elevator algorithm,” it consists of two rules:  

1. As long as there’s someone inside or ahead of the elevator who wants to go in the current direction, keep heading in that direction.
2. Once the elevator has exhausted the requests in its current direction, switch directions if there’s a request in the other direction. Otherwise, stop and wait for a call."



**PSEUDO CODE**

//Begin program

INIT()

Passenger.inputsUpDown
Control.recievesUpDown
Control.runsMachinery

Passenger.inputsFloorNumber
Control.recievesFloorNumber
Control.runsMachinery 

// end program 

// Define Objects, Functions

Functions and Objects  

INIT function  
    -Create Elevator car  
    -Create elevator movement mechanisms (gears, pulleys, counterweight, power)  
    -Create control panels (interior and exterior)  
    -Create main control system  
    -Create passenger  

collectiveControl function
    -If passenger inside elevator or passenger at exterior control panel requests the elevator to keep moving in current direction, keep going that direction.  
    -Once elevator has completed all requests in current direction, switch to the other direction if there are requests to move that direction.  
    -Otherwise, stop and await further inputs. 

runsMachinery function
    -This just means that the control tells the machinery of the elevator to pull the elevator up or down according to collectiveControl function.

Passenger inputs  
    -Provides up/down button request on exterior panel  "providesUpDown"  
    -Provides floor number request on interior panel "providesFloorNumber"   
    -Rides in elevator car while it moves between floors "ridesCar"  

UpDown input
    -Passanger presses the up or down arrow on an exterior control panel

FloorNumber input
    -Passanger presses a number button on the interior control panel of the elevator
