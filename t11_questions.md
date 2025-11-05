# T11: The Legend of Tuna: Breath of the Catnip

## Instructions

Please replace each `**Replace This Text With Your Response**` with your answer.

___

## SECTION 1

1.a. First, discuss with your team and assign yourselves roles. Try to pick the role you’ve had the least experience in.

```
    |                 | Monday | Wednesday | Friday |
    |-----------------|--------|-----------|--------|
    | Driver          |  Pier  |           |        |
    | Navigator       | Yoseph |           |        |
    | Quality Control |        |           |        |
```

___

## SECTION 2

2.a. Look at the three Python files in the repository. Identify below all of the classes, and a brief description of
    what each one represents:

```
    Class 1: Game
        Establishes game logic
    Class 2: NPC
        Initializes and sets the methods for NPCs
    Class 3: Good_NPC
        Inherits from the NPC class to create a good npc
    Class 4: Bad_NPC
        Inherits from the NPC class to create a bad npc
    Class 5: Player
        Initializes the player and defines how it can move
``` 

2.b. Look more closely at the **t11_game.py** file. There are 8 lines; identify if they are 
    a) instance parameters, 
    b) method calls within the class, or 
    c) method calls to another class

```
    self.size = 800, 600                              # Instance Parameters
    self.running = True                               # Instance Parameters
    pygame.init()                                     # Method call within the class
    self.screen = pygame.display.set_mode(self.size)  # Method call within the class
    self.clock = pygame.time.Clock()                  # Method call to another class
    self.player = Player(self.size)                   # Method call within the class
    self.good_npc = NPC(self.size)                    # Method calls to another class
    self.screen.fill('#9CBEBA')                       # Method calls to another class
```

2.c. Parse through the `run()` method of t11_game.py. In particular, note how the game handles 
    a) collisions between the player and NPC: if whiskers or tacocat collide with the player, the screen prints a text saying the game ended but doesn't kill the characters.
    b) moving the player and NPC around the screen: Tuna (the player) moves based on the key pressed, which runs in the else statement when the characters did not collide, and the following two lines move the NPCs
    c) redrawing the player and NPC after they move: The blit method is used to draw the characters in the else clause of the loop, and the display is updated right after before the frames are refreshed.
    d) how often the game updates the screen: The clock.tick() method is used on self to refresh 24 frames per second

In your own words, describe how the four items above are accomplished in the Game class:


```

_Return to the Google Doc to continue the assignment._

---

## SECTION 3

3.a: First, take a look at the **t11_player.py**. What class does the `Player` class inherit functionality from? 
    How do you know?

```
    For the player class, functionality is inherited from the Sprite class. We know this because it is passed as a parameter to the new Player class, then super(). is used
```

3.b. Sprites need two attributes to function: A surface and a rectangle. The surface (implemented in a `Surface` 
     class inside **pygame**) represents the drawing that will be rendered to the screen. The rectangle 
     (implemented in the `Rect` class in **pygame**) represents the area where the surface will be drawn on the screen, 
     including its width, height, and position. Find the lines of code that implement these two ideas, 
     and explain what each line does. 

```
self.screen.blit(self.tuna.surf, self.tuna.rect): This line sets the drawing for the player (surf) and then specifies where the surface will be drawn (rect)
self.screen.blit(self.tacocat.surf, self.tacocat.rect)
self.screen.blit(self.whiskers.surf, self.whiskers.rect)

The following two lines do the same thing, but for the NPC characters instead. 
```

3.c. The `Player` class has only one method so far. Parse that code and docstring, and describe what it does:

```
    It makes the player move on the screen when one of four keys is pressed. 
```

3.d. Similarly, the `NPC` class in **t11_NPC.py** also inherits the `Sprite` class from **pygame**, 
     but it does a little more than our `Player` class. Compare the two classes, and identify/describe the differences:

```
    The initial position for NPCs is set to 0,0, and the way that each moves is implemented differently. 
```

3.e. Of particular interest is how we keep the `NPC` on the screen. Describe how we're using 
    the `self.rect` attribute in the `get_direction()` method to keep the `NPC` visible.  

```
    **Replace This Text With Your Response**
```

_Return to the Google doc to continue the assignment._ 
---

## SECTION 4

Using **t11_NPC.py** as a starting point, create a new class called `Good_NPC` (you can do this in the **t11_NPC.py** 
file, or create a new file; your choice). Have the new class inherit from the `NPC` class that I gave you, 
including calling the parent class's initializer. Convert **t11_game.py** so that it spawns Taco Cat as a `Good_NPC` 
instead of an NPC. Debug any errors you get; the program should work, at this point. 

4.a. How hard was it to create the child class, given the parent?

```
    **Replace This Text With Your Response**
```

The parent class `NPC` currently holds attributes, like the image used, which are actually more specific to 
`Good_NPC` now. Refactor the code so that you can indicate the image for Good_NPCs and Evil NPCs (coming next)
inside the child classes, instead of the parent class. There are multiple ways to accomplish this; discuss with your 
partner first how you would like to approach this problem. 

Next, implement another new class called `Bad_NPC` (again, you can do this in the **t11_NPC.py** 
file, or create a new file; your choice). Our bad NPC (Whiskers) is going to march around the screen in a different way
than our friend Taco Cat; he should move like a Boustrophedon, working his way across the entire screen, before 
moving up or down. Because this NPCs movement is significantly different from the Good NPCs movement, we should 
make a design choice. We could:
    a) keep the `movement` method in NPC, and override it inside `Bad_NPC` with a new method.
    b) remove `movement` from NPC, and implement separate `movement` functions in each child class.
    c) refactor `movement` in NPC, so it can handle both child class options.

4.b. Discuss with your partner your design choice above, including their pros and cons. Document your 
     choice, and why, below: 

```
    **Replace This Text With Your Response**
```

Finally, we need to create our enemy, Whiskers. Update **t11_game.py** to:
    a) spawn `whiskers` at the beginning of the game
    b) make `whiskers` move around the screen
    c) handle collisions between Tuna and Whiskers, which ends the game
    d) (optional) handle collisions between Taco Cat and Whiskers, which kills Whiskers and spawns a new evil NPC

---

## SECTION 5

5.a. Inheritance allows us to produce special cases of a class, extending their functionality. Describe
    what challenges you faced while implementing the child classes that extended the `NPC` class. 
    How did you overcome them?

```
    **Replace This Text With Your Response**
```