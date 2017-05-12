/**********************************************************************


PARTNER 1 (whose PennKey would come first in alphabetical order)
Partner 1 Name: Ethan Terner
Partner 1 PennKey: eterner
Partner 1 Recitation #: 206

PARTNER 2 (whose PennKey would come second in alphabetical order)
(If you chose to do this project without a partner, write NONE in each spot below.)
Partner 2 Name: Max Grove
Partner 2 PennKey: maxgrove
Partner 2 Recitation #: 205

/**********************************************************************
 * Description of Project: Write a detailed description of your project,
 * describing how you *actually* implemented it.  Be sure to cover:
 * - overview (provide a high level overview of your project and its functionality)
 * - object-oriented design (how did you incorporate techniques we discussed in class 
          on proper object-oriented design, including class decomposition, how classes
          interacted, etc?)
 * - techniques (describe any algorithms/techniques you used in your project)
 * - efficiency (how is your implementation computationally efficient?)
 * - expandability (how does your design/implementation allow the program to be 
                    easily extended with new functionality in the future?)
 * - challenges (what parts of your project were especially challenging?)
 * - open problems (are there any open issues with your project?)
 * The overall length of this description should be approximately 1 page
 * of single-spaced text.
 **********************************************************************/

This PROJECT runs a modified version of Donkey Kong arcade. The user controls
    a character and the goal is to interact with other objects on screen
    to get to the top of the screen and collide with the princess. The character
    dies (game ends) if it collides with a barrel object or falls off bottom
    of the screen. Once the character reaches the third floor, it turns from
    mario to pikachu. Pikachu can destroy barrels directly above him by a
    certain keypress.

The OBJECTS included in this program include a barrel, a DonkeyKong, floors,
    ladders, a mario figure (which can be drawn as a pikachu), a peach figure,
    and the World (which is a static main function, not an object).
    DonkeyKong is the only object that does not interact with any other object.
    Most interactions are handled through the mario object. Mario checks
    if his location is the same as the ladders, barrels, and peach. The floors
    check if Mario is colliding with them. The floors also check if they are
    colliding
    with the barrels We attempted to break down the program into obvious
    different parts. 
    The  only part we were debating was whether to have pikachu as it's' own
    object
    or as a part of the Mario object. We decided to have it as part of the mario
    object because it uses the same functions and only changes the drawing.
    
    
    CLASSES/OBJECTS are broken down into necessary functions for that object.
        Mario can be drawn, be drawn as pikachu, check for collisions, fall,
        climb, and activate a lightning function if drawn as pikachu. He can check
        if he is touching a floor by calling the respective floor function.
        
        Peach, Ladder, and DonkeyKong only have draw functions and getter functions
        for their location. Their constructors set their x, y locations.
        
        The Barrel includes a falling function (which changes its floorlevel
                                                    variable), a stopping falling
        function, and various move functions. 
        
        The Floor includes draw and get functions and collision functions.
        The floor checks for collisions, because it has to interact
        with the barrels and mario so it is easier for the floor to check 
        both of them.
        
        The world function runs the game, combining all of the objects.

 Using objects for this project allows us to protect access control with private
    fields and public methods to allow for accessor methods and mutator methods
    when necessary. For example, the user cannot change donkeyKong’s location
    once it has been set once. We also are able to use static and final for
    fields, when we want a variable to be the same across all instances of an
    object, like with halfWidths and halfHeights. We are able to encapsulate
    fields and methods for readability and obvious differences in parts of
    the games. We also used the keyword this to make for obvious setting in 
    constructors.

The TECHNIQUES included are checking for collisions between various objects:
    The floor checks for collisions with barrels and mario since those objects
      will be "standing" on them. Collisions involve checking if the x and y
      location of one object is in a certain range on top of the floor.
    
    In the main World, we use nested while loops to wait for user input (for
      instructions and play again feature). The main World also loops through
      the barrels using the get() function. This will be elaborated on later
      in the section about LinkedLists.
    
    Mario is able to be drawn as Pikachu or Mario depending on his y Location.
    In order to remove barrels with pikachu's' lightning feature, we used a 
    true/false operator for if lightning is activated and if the x position
    matches within a certain small range.
    
    In order to account for imperfect numbers, we hardcoded a few
    "error-tolerance" values.
    
    We implemented a timer feature to keep track of what frame we are on -
    looping frames every 180 frames. This was to keep a constant creation
    time of barrels and drawing various donkey kong images.
    
We used ALGORITHMS such as finding the minimum of several values and looping
    through a linkedlist.
 
This code could be EXPANDED with more levels, like in the original game. It
    would only involve changing the code at the top of World’s main function
    involving the ladders and floors and original locations. Once the original
    locations and where to draw objects are changed, you have a whole new level.
    One could add more ladders, less ladders, more floors, different floor
    locations, and more.

This code is relatively EFFICIENT. It uses a linkedlist to get rid of unused
    barrels. (this is touched on later on how it is the most efficient method
    to use) It uses while loops to check things numerous times
    so may not be able to be run on an older computer, but this will not
    affect most users with relatively recent technology. The many while loops
    all have computational complexity of O(n), which is the fastest that it
    can be for this sort of program where many n objects have to be drawn. We
    don’t have to sort anything and combined various functions into one while
    loop to make more efficient. In addition, because PennDraw.enableAnimation()
    is used, the user doesn’t see changes until all changes for one frame have
    been made.


The CHALLENGES of this program included removing barrels when mario (pikachu)
    uses it’s lightning bolt ability. Making barrels fall down floor was
    difficult but we used collision detection and a falling function similar to
    mario’s jump function. The simple drawing was much easier.    

OPEN PROBLEMS: on some computers, if mario tries to jump onto a ladder,
    that is, he tries to jump up and then move over to a ladder, the code
    manually overrides his position and flashes him to the top.                                                     
   
    

/**********************************************************************
 *  Instructions for Running Your Project: 
 *  Provide DETAILED step-by-step instructions for running your project 
 *  and any notes on what the TAs should pay particular attention to when 
 *  grading.  If they can't run your project or didn't notice a particularly 
 *  cool aspect of it because you didn't provide thorough enough instructions, 
 *  then you won't receive credit for it.  It is your responsibility to make 
 *  sure these instructions are thorough and correct. 
 **********************************************************************/

Compile all files. Run the command: "java World" without quotes. An instructions pane will open
when you run the program, assuming you have the latest version of Java installed.
    The instructions included are: Press 'a' to move Mario character left,
    'd' to move right, 'w' to jump or climb ladders, and 's' to move down
    ladders. Once Mario character reaches the third floor Level, he will turn
    into Pikachu. While the pikachu character is activated, press 'f' to
    activate a lightning bolt that will destroy all barrels directly above 
    pikachu. 
    
    The goal of the game is to climb all the ladders to get to Princess Peach
    without dying. Character dies if it collides with a barrel or falls of the
    bottom of the screen.
    
    Once you win or die, a screen pops up displaying if you won or lost
    and asking if you wish to play again. Press 'y' to restart the game or
    'n' to terminate the program. Note, music will continue playing until you
    quit the Standard Draw window.
    
    Note, you cannot climb down a ladder once you have finished climbing it. You
    can only go down floors by falling off the side of a floor
    
    You will also notice that mario cannot go off the side of the screen,
    falls down floor levels if he is not standing on a floor, and that 
    nothing happens when he collides with DonkeyKong or the barrels to the left
    of donkey Kong.
    
    You will also notice background music plays throughout the game: there
    is a sound effect for jumping, a special tune that plays for winning, and 
    a special tune that plays for losing. Because StdAudio.java does not have a
    terminate function (that we could find/understand), the win/lose music may
    continue playing for a brief moment if you elect to play again. Background
    plays without stopping as soon as you have begun gameplay past the
    instructions pane.
    
    All in all, just play the game and explore and have fun!

/**********************************************************************
 *  How precisely did your project use the LinkedList you implemented?
 **********************************************************************/
    We used get functions, remove functions, add, etc. to 
    draw the barrels and add or remove from the head. We could not have
    used an array for this, as the head is frequently removed (when it falls
     off the screen) and barrels in the middle are often removed when Pikachu’s
    lightning function is activated. If an array was used
 We would have had to remove heads and middle Barrels (thus increasing
  computational complexity significantly - because the entire array would have
           to be shifted) and the array would have had to be extremely long as
    barrels are added to the end of the list.



/**********************************************************************
 *  List whatever help (if any) that you received
 **********************************************************************/

 All graphics were obtained from
    www.mariomayhem.com/downloads/sprites/donkey_kong_sprites.php and 
    www.spriters-resource.com/arcade/dk/sheet/45989/
    All audio was obtained from www.classicgaming.cc/classics/donkey-kong/sounds

    No other help was received. We did not receive any help outside of
    TA office hours. We did not collaborate with anyone, and we did not use any
    resources beyond the standard course materials and the graphics/audio.




/**********************************************************************
 *  Describe any serious problems you encountered.                    
 **********************************************************************/
Initially we struggled to check for collisions between mario and the floors 
    objects without causing problems other aspects of the game.
