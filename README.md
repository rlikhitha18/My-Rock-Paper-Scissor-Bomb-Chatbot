Rock–Paper–Scissors–Plus Referee Bot

Overview
   
This project implements a minimal AI referee for a Rock–Paper–Scissors–Plus game, built as part of the upliance.ai AI Product Engineer assignment. The bot enforces game rules, validates user input, tracks state across rounds, and ends the game automatically after three rounds.
The game runs in a simple CLI-based conversational loop.

State Model
   
The game state is maintained as a persistent Python dictionary outside the prompt, containing:

•	Current round number

•	User score

•	Bot score

•	User bomb usage flag

•	Bot bomb usage flag

•	Game-over flag

This ensures state persistence across turns without relying on prompt memory.

Tool Design

The core game logic is implemented as explicit tools:

	validate_move: Validates user input and enforces bomb usage constraints.

	resolve_round: Determines the winner of each round based on game rules.

	update_game_state: Mutates the game state by updating scores, round count, and bomb usage.

These tools separate intent validation, game logic, and state mutation clearly.

Architecture

1.	Input handling and conversation flow are managed via a lightweight CLI loop.
   
2.	Game logic and state changes are handled exclusively by tools.
   
3.	Google ADK is used as the tool abstraction layer.
   
4.	No databases, external APIs, or UI frameworks are used.

Trade-offs
   
	The bot uses simple random move selection instead of strategic play to keep the implementation minimal and deterministic.

	A CLI-based interface was chosen over a graphical UI to comply with assignment constraints.

Future Improvements
   
With more time, the following enhancements could be added:

•	Smarter bot strategies

•	Replay or restart functionality

•	Expanded move sets or difficulty levels
                                               
                           
