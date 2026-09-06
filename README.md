# 🐢 Turtle Crossing Arcade Game

A fun **Turtle Crossing Arcade Game** built with **Python Turtle Graphics**.

The objective is simple: control the turtle, cross the road while avoiding moving cars, and reach the finish line. Every time you successfully cross the road, the level increases and the cars become faster.

This project is built using **Object-Oriented Programming (OOP)** and is divided into multiple Python modules to keep the code organized and maintainable.

---

## 🎮 Game Preview

> Cross the road, avoid the cars, and try to reach the highest level possible!

**Goal:** Reach the finish line without getting hit by a car.

---

## ✨ Features

* 🐢 Player-controlled turtle
* 🚗 Randomly generated cars
* 🎨 Cars have randomly selected colors
* 🛣️ Cars move continuously across the screen
* 📈 Level system
* ⚡ Increasing difficulty
* 💥 Collision detection
* 🏁 Finish-line detection
* 🔄 Player resets after successfully crossing
* 🎮 Keyboard controls
* 🏆 Game Over screen
* 🧩 Modular Object-Oriented Python code

---

## 🕹️ How to Play

### Controls

| Key         | Action                  |
| ----------- | ----------------------- |
| ⬆️ Up Arrow | Move the turtle forward |

### Objective

1. Start at the bottom of the screen.
2. Use the **Up Arrow** to move the turtle.
3. Avoid all incoming cars.
4. Reach the finish line.
5. Your level increases.
6. Cars become faster.
7. Keep playing until you get hit!

---

## 📈 Difficulty System

The game becomes progressively harder.

Whenever the player reaches the finish line:

```text
Level 1
   ↓
Level 2
   ↓
Level 3
   ↓
Level 4
   ↓
...
```

The car speed increases after every successful crossing.

This is handled by:

```python
def increase_speed(self):
    self.car_speed += MOVE_INCREMENT
```

---

## 🧠 How the Game Works

The game consists of four main Python modules.

### 1. `main.py`

This is the main game controller.

It:

* Creates the game window
* Creates the player
* Creates the car manager
* Creates the scoreboard
* Handles keyboard input
* Runs the game loop
* Detects collisions
* Detects when the player reaches the finish line

The main game loop continuously performs these tasks:

```text
Create Cars
     ↓
Move Cars
     ↓
Check Collision
     ↓
Check Finish Line
     ↓
Update Screen
     ↓
Repeat
```

---

### 2. `player.py`

This module controls the player's turtle.

The `Player` class inherits from Python's `Turtle` class:

```python
class Player(Turtle):
```

The player starts at:

```python
STARTING_POSITION = (0, -280)
```

and needs to reach:

```python
FINISH_LINE_Y = 280
```

The player can move upward using:

```python
def go_up(self):
    self.forward(MOVE_DISTANCE)
```

---

### 3. `car_manager.py`

This module manages all the cars in the game.

The `CarManager` class is responsible for:

* Creating cars
* Assigning random colors
* Assigning random vertical positions
* Moving cars
* Increasing car speed

Cars are randomly created using:

```python
random_chance = random.randint(1,6)
```

A new car is created when the random number equals `1`.

Cars are placed at different vertical positions:

```python
random_y = random.randint(-250,250)
```

This makes each game slightly different.

---

### 4. `scoreboard.py`

This module manages the level display and Game Over message.

The scoreboard starts at:

```python
self.level = 1
```

When the player successfully crosses the road:

```python
scoreboard.increase_level()
```

The level is updated on the screen.

If the player collides with a car:

```python
scoreboard.game_over()
```

displays:

```text
Game Over!
```

---

## 📁 Project Structure

```text
turtle-crossing-game/
│
├── main.py
├── player.py
├── car_manager.py
├── scoreboard.py
└── README.md
```

### File Descriptions

| File             | Description                   |
| ---------------- | ----------------------------- |
| `main.py`        | Main game loop and game logic |
| `player.py`      | Player/turtle movement        |
| `car_manager.py` | Car creation and movement     |
| `scoreboard.py`  | Level and Game Over display   |
| `README.md`      | Project documentation         |

---

## 🛠️ Technologies Used

* **Python 3**
* **Turtle Graphics**
* **Object-Oriented Programming**
* **Random Module**
* **Time Module**

### Python Modules

```python
import time
import random
from turtle import Turtle, Screen
```

---

## 🚀 Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/turtle-crossing-game.git
```

### 2. Navigate to the project directory

```bash
cd turtle-crossing-game
```

### 3. Run the game

```bash
python main.py
```

---

## 📋 Requirements

This project uses Python's built-in libraries, so no external packages are required.

You only need:

```text
Python 3.x
```

The game uses the built-in:

```text
turtle
random
time
```

modules.

---

## 💡 Concepts Practiced

This project helped practice several important Python programming concepts:

* Object-Oriented Programming
* Classes and inheritance
* Functions and methods
* Lists
* Loops
* Conditional statements
* Random number generation
* Event listeners
* Keyboard input
* Collision detection
* Game loops
* Modular programming
* Code organization

---

## 🎯 Learning Objective

The main purpose of this project is to practice **Object-Oriented Programming in Python** while building an interactive game.

Instead of putting the entire game into one file, the project separates different responsibilities into different classes:

```text
Player
   ↓
Handles player movement

CarManager
   ↓
Handles cars

Scoreboard
   ↓
Handles levels and game status

Main
   ↓
Controls the game
```

This makes the project easier to understand, maintain, and extend.

---

## 🔮 Future Improvements

Some possible improvements for future versions include:

* ❤️ Add multiple lives
* 🏆 Add a high-score system
* 🔊 Add sound effects
* 🎵 Add background music
* ⏸️ Add a pause button
* 🔄 Add a restart button
* 🚗 Add different car sizes
* 🌙 Add different game themes
* 💾 Save the highest level
* 🎨 Improve the road and game graphics
* 🎮 Add additional keyboard controls
* 🥇 Add a persistent leaderboard

---

## 🐛 Collision Detection

The game checks the distance between the player and every car:

```python
for car in car_manager.all_cars:
    if car.distance(player) < 20:
        game_is_on = False
        scoreboard.game_over()
```

If a car gets close enough to the turtle, the game ends.

---

## 🏁 Winning / Progression System

There isn't a traditional final winning condition.

Instead, the game uses a **level progression system**.

Every successful road crossing:

```text
Player reaches finish line
          ↓
Player returns to starting position
          ↓
Level increases
          ↓
Car speed increases
          ↓
Difficulty increases
```

The goal is to survive and achieve the highest level possible.

---

## 👨‍💻 Author

**Muhammad Taha Ahmad**

Computer Science Student | Python Developer | AI & Robotics Enthusiast

### Connect With Me

* GitHub: [github.com/NinjaVinja](https://github.com/NinjaVinja)
* LinkedIn: [linkedin.com/in/muhammad-taha-ahmad-391679262](https://www.linkedin.com/in/muhammad-taha-ahmad-391679262)

---

## ⭐ Support

If you found this project interesting or useful, consider giving the repository a ⭐ on GitHub!

---

## 📜 License

This project is open-source and available for educational and personal use.
