Yuhm Source Code
=================

Student Object
---------------

### Variables

	int index
	int x
	int y
	boolean alive
	char face
	int cookieCount

*	The index for Student corresponds to the appropriate png image
*	The x and y coordinates relate to the student's position on the board
*	alive relates to if the student is alive or dead
*	face relates to the orientation of the png
*	cookieCount relates to the amount of cookies collected

### Methods

*	Default Constructer which sets position and status (dead or alive) of the student

			public Student()

*	There is a method setPosition which sets the x and y coordinates of the student on the map

			public void setPosition(int x, int y)

*	The Kill method sets the alive variable to false (Kills the student)

			public void Kill()

*	The turn method rotates the student depending on user input

			public void turn(char direction)

*	The move method moves the student in the direction the user inputs

			public void move(char move)

Librarian Object
----------------------

### Variables

	int index
	int x
	int y
	boolean frozen

*	The index for Librarian corresponds to the appropriate png image
*	The x and y coordinates relate to the librarian's position on the board
*	frozen relates to the state of the librarian

### Methods

*	Default constructer which sets x, y, and frozen variables

			public Librarian()

*	There is a method setPosition which sets the x and y coordinates of the librarian on the map

			public void setPosition(int x, int y)

*	The move method moves the librarian on the map

			public void move(char move)

*	getIndex method returns the index of the corresponding librarian png

			public int getIndex()

Main Thread Object
------------------------------

### Variables

	static final int MAX_FPS = 30
	double average FPS
	SurfaceHolder surfaceHolder
	GamePanel gamePanel
	boolean running
	static Canvas canvas

*	FPS variables set and regulate framerate
*	GamePanel is a class which creates a new surface and redraws the screen every time it is updated
*	running is a variable which sets whether the thread is running or not

### Methods

*	The MainThread method initializes the thread to the game panel

			public MainThread(SurfaceHolder surfaceHolder, GamePanel, gamePanel)

*	setRunning sets the running variable to determine if the thread is running or not

			public void setRunning(boolean running)

*	The run method runs the thread at the expected fps and redraws the canvas

			public void run()

layer Object
--------------------

### Variables

	int index
	int x
	int y
	boolean isItem
	boolean crumbs = false

*	The index corresponds to the appropriate png image layered on top
*	The x and y coordinates relate to the position on the board
*	isItem identifies whether or not there is an item at the appropriate (x, y) coordinate
*	crumbs identifies if there are crumbs on that tile

### Methods

*	The layer method constructs the layer and sets the isItem to false

			public layer(int x, int y)

*	setCookie sets the layer to a cookie item

			public void setCookie()

*	setCrumbs sets the layer to a crumb item

			public void setCrumbs()

*	reSet indicates that there is no item on that layer (Sets isItem to false)

			public void reSet()

*	Returns the index of the corresponding png (cookie or crumb)

			public int getIndex()

MonsterThread Object
----------------------

###  Variables

	GamePanel gamepanel
	Librarian librarian[]
	char moveChar
	int sleeptime
	boolean running

*	librarian[] stores the three separate librians
*	moveChar indicates the direction of librarian movement
*	sleeptimer corresponds to the wait time between librarian movements
*	running indicates whether or not the monster thread is running

### Methods

*	The MonsterThread method sets the GamePanel variable to the proper screen

			public MonsterThread(GamePanel cv)

*	setRunning sets the running variable to determine if the thread is running or not

			public void setRunning()

*	getDirection returns an integer which corresponds to the cardinal direction in which the librarian needs to head to get to the player

			public int getDirection()

*	tryMove attempts to move the librarian in a singular ajacent direction based on the inputs

			public boolean tryMove(int try_x, int try_y, Librarian librarian)

*	findOrder finds the order in which the librarian must move to get to the player

			public void findOrder(int direction, Librarian librarian)

*	run refreshes the librarians position every 0.5 seconds

			public void run()

GamePanel Object
-------------------

### Variables

	MainThread thread
	MonsterThread monsterthread
	bitmap icons[]
	layer items[][]
	final int numRows = 11
	final int numColumns = 17;
	Student student
	char direction
	Librarian librarian[]
	boolean GameOver = false
	boolean isTouch = false
	int resetCount = 0
	long startTime
	long finalTime
	random rand
	boolean intersect
	boolean pause

*	thread relates to the main thread which redraws the screen 30 times per second
*	monsterthread keeps track of librarian movement every 0.5 seconds
*	icons stores all the png images
*	items stores all the layer objects for each grid position
*	numRows and numColumns corresponds to the size of the grid
*	student relates to the playable character
*	direction relates to the student's direction
*	librarian relates to the 3 librarians on the grid
*	GameOver determines if the student is alive or not
*	isTouch determines if the user is touching the screen
*	resetCount keeps track of the amount of times the board is reset
*	startTime and finalTime correspond to the start and end of the game
*	rand is a random object used to generate random board layouts
*	intersect determines whether new board layouts have any intersections with each other
*	pause determine whether the librarians are paused

### Methods

*	GamePanel makes the game panel and initializes variables

			public GamePanel(Context context)

*	on surface creation, generates png's and starts the game

			public void surfaceCreated(SurfaceHolder holder)

*	surfaceDestroyed stops the relevant threads when the surface is destroyed

			public void surfaceDestroyed(SurfaceHolder holder)

*	onTouchEvent handles touch input for player movement

			public boolean onTouchEvent(MotionEvent event)

*	checkCrumbs checks to see if there are cookie crumbs at the position given

			public boolean checkCrumbs(int x, int y)

*	This method returns whether or not the game is over

			public boolean getGameOver()

*	getScore calculates and returns the score based on time and cookie count

			public long getScore()

*		draw draws all of the surfaces onto the canvas

			public void draw(Canvas canvas)

Screen Activities
--------------------------

The following activities determine screen state:

*	HomeScreen
*	GameActivity
*	GameOver
*	ScoreBoard
