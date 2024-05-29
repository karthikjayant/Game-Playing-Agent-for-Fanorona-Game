# Game-Playing-Agent-for-Fanorona-Game
This project focuses on the development of an AI agent for the traditional Malagasy board game Fanorona-Tsivy. Fanorona, a popular strategy game in Madagascar, involves capturing all the opponent's pieces on a 5x9 board. The AI agent was developed using two primary methodologies: a table-driven approach and the Minimax algorithm.

## Problem Statement:

The objective of this project is to create an intelligent agent capable of playing Fanorona-Tsivy strategically against human opponents. The AI should demonstrate proficiency in decision-making, evaluated based on its effectiveness and efficiency. The project details the implementation and results of both approaches.

## Methodology:

### Table-Driven Approach:

The table-driven approach simplifies decision-making by using a pre-defined table that maps specific percepts (observations or states) to corresponding actions. This approach is particularly useful for scenarios with a limited and well-defined set of percepts and actions.

Percepts:

* Can Move (Percept 1): Identifies pieces that can move in the current state, checked by the get_pieces_that_have_free_space_around() function.
* Can Attack (Percept 2): Determines if any movable pieces can make an attacking move using the check_if_pieces_that_can_move_can_attack() function.
* Can Make Both Types of Attacks (Percept 3): Evaluated within the get_possible_moves_for_piece() function, determining possible moves including different attack types.
* Chance for Another Attack from New Position (Percept 4): Checked by the check_if_more_moves() function, which verifies if the moved piece has additional attacking options from its new position.

Actions:

Make an Attacking Move: Executed by the select_random_attack_move() function when attacking options are available.
Make an Available Move: Implemented in the select_random_move() function when no attacking options are available.
Select an Attack Type: Handled by the move_piece() function to choose between different attack types.
Make Another Attacking Move: Determined by the check_if_more_moves() function after an attack.
Change Turn: Switched at the end of the AI's actions within the player_AI() function.
Percept to Action Mapping:

The AI operates using a rule-based approach to simplify decision-making. At the start of its turn, the AI assesses the game board to determine if any pieces can move or attack. Depending on the available options, the AI decides whether to execute a simple move or an attacking move. If an attack is executed, the AI re-evaluates the board to check for further attacks, ensuring it maximizes its advantage. The turn ends with the AI handing over control to the next player.

### Minimax Algorithm:

The Minimax algorithm evaluates all possible moves in a two-player, zero-sum game, aiming to determine the optimal move by considering the opponent's potential responses. This algorithm explores the game's decision tree, representing possible sequences of moves and their outcomes.

Implementation:

The Minimax code for Fanorona integrates a graphical user interface (GUI) using Tkinter. The game board is represented by a two-dimensional list called "pieces," tracking the state of each cell. Functions like create_to_movables and create_to_paika manage possible moves and new game situations, creating a tree of potential moves and outcomes. The depth variable controls how far ahead the AI looks into the future.

Evaluation Function:

The evaluation function assesses the current board state, assigning scores based on the number of pieces each player has. This function guides the AI by indicating how favorable a specific board setup is. The AI uses these scores to navigate the decision tree, seeking the highest score move.

Handling Turns and Randomness:

The AI switches between players using "turn" and "not turn" variables, adhering to the Minimax algorithm's principles. In case of multiple moves with the same score, the AI introduces randomness by picking one move randomly, adding unpredictability to its strategy.

## Technology Stack:

Table-Driven Approach:

Python: Core language for implementation.
Random Library: Generates random numbers for AI decisions.
Class-Based OOP: Defines game entities like the board and pieces.
Standard I/O: Manages user interaction through the console.
Control Structures and Data Structures: Implements game logic using loops, conditionals, lists, and dictionaries.
Command-Line Interface (CLI): Runs the game in a text-based environment.

Minimax Algorithm:

Python: Core programming language.
Tkinter Library: Creates the game's graphical interface.
Canvas Widget: Draws the game board and pieces.
Event Handling: Manages user interactions.
Messagebox Module: Displays pop-up messages.
Random Library: Adds unpredictability to AI decisions.
Time Module: Implements delays for realism.
Copy Module: Manages deep and shallow copies of game states.
Complex Algorithms and Data Structures: Handles game logic and AI strategies.
CLI and GUI: Offers versatile interaction modes.

## Conclusion:

This project explored the Fanorona game using two AI techniques: a table-driven approach and the Minimax algorithm. The table-driven approach, being straightforward and rule-based, effectively guided the AI in simpler decision-making scenarios. The Minimax algorithm, employing deeper strategic thinking, provided better results. Each method enhanced the gameplay experience, showcasing the flexibility of AI for board games and demonstrating how various AI approaches can cater to different gaming styles. The project highlights the potential for further development, such as incorporating alpha-beta pruning to optimize the Minimax algorithm's performance. Overall, this investigation provided valuable insights into the strengths and applications of different AI approaches in traditional games.
