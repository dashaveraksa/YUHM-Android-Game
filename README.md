Yuhm: An Interactive Arcade Game
==========================

Installation Instructions
----------------------------

*	Download the YuhmGame.zip file
*	Extract the file to a location that can be accessed by Android Studio
*	In Android Studio, click on "Open Project" and click on YuhmGame
*	Run the program through an emulator in Android Studio

Instructions for Playing Yuhm
-----------------------------

### Goal:

*	To collect all of the cookies on each level while avoiding the angry librarians

### How to play:

*	To move your character, use the D-Pad in the lower left corner. Each arrow on the D-Pad corresponds to the same direction. Pressing the left arrow causes your character to move to the left, pressing the up arrow causes your character to move up, etc...

*	When you have collected 3 cookies, you can activate your special ability, Snack Break, by pressing the button in the upper left corner. This will freeze all of the librarians for 5 seconds, allowing you to move around the library unhindered

*	If all of the cookies on a level have been collected, you will continue on to the next level

*	The game ends when a librarian catches you

*	Your final score is based on amount of cookies collected and time spent alive

Test Cases
----------------

| Test Case | Expected Outcome |
|:---------:| :---------------:|
| Press scores button on home screen | View switches to scoreboard screen |
| Press play button on home screen | View switches to gameplay screen |
| Press left/right/up/down arrow | Moves main character left/right/up/down respectively |
| Press freeze button on left side of gameplay (after collecting at least 3 cookies) | Librarians freeze for 5 seconds |
| Move character onto cookie | Cookie is collected, 100 points added to score |
| Librarian and main character collide | Gameplay ends, view switches to game over screen |
| Press save score button on game over screen | User prompted to enter initials |
| User enter initials | Score is saved, view switches to scoreboard screen, score displayed on leaderboard if one of top 3 highest scores |
| Press main menu button on game over screen | View switches to home screen |