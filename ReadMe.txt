Basic Movements
Simple Functions to Control the Lambo

Arduino doesn't like namespaces for some reason. It hangs when compiling if I change the class to a namespace.
I have it being used as a class namespace at the moment with static functions. ex. BasicMovements::move();

shorten it with "typedef BasicMovements bm;"
ex.             "bm::move(1,1);"

----Use----

--move(double x,double y)--
Sets the speed of both motors. x and y need to be values -1 <= x&y <= 1
Think of it like a cortesian plot with vectors if the car were on the origin pointing up along the y-axis (looking from the top down).

                       y
                  move(0,1)
move(-1,1)           |                move(1,1)
                     |
                     |
                     |
                     |
                     |
                     |
-------------------------------------------x (only left-right translation impossible)
                     |
                     |
                     |
                     |
                     |
                     |
                     |
move(-1,-1)          |                 move(1, -1)
                 move(0,-1)


--turnRight(int len = 1)/turnLeft(int len = 1)--
Make the car turn roughly 90deg. the passed len is the number of iterations to go through. turnLeft(4) turns roughly 360deg.
Pauses after completion

--goForward(int len = 1)/goBackwards(int len = 1)--
Makes the car go forward/backward. The len is a multiplier for how far you want to go. Roughly 1 foot per len. Very Roughly
Pauses after completion

----Warnings----

-Try not to strain the motors. I haven't set any safety functionality yet so 
 if you go from full forward to full backward instantly it's gonna be hard on the motor.