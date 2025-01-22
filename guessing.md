``` mermaid
graph TD
   A[Welcome to the number guessing game! You only get 3 tries, so make them count. Numbers not within the parameters do not count as a guess. Once you guess a number, that number no longer becomes a possible choice.];
   A-->B[Select any number between 1-10]
   B-->|User guess between 1-10|C["Generating number..."
   code executes randomNumber]
   B-->|User guesses out of parameters|D[That number is NOT between 1-10! Try again!]
   D-->|Code resets|B
   C-->|User is correct|E[Wow! First try! Today is your lucky day!]
   C-->|User is incorrect|F[That number is incorrect. Try again!
   code generates new randomNumber excluding userGuess1]
   F-->|User is correct|G[Second try! Still pretty lucky!]
   F-->|User is incorrect,guesses 1-10|H[Incorrect! Only 1 more guess left.
   code generates randomNumber excluding userGuess1 and userGuess2]
   F-->|User guesses number not between set parameters|I[That is NOT a number between 1-10! Or maybe you already guessed that. Either way, try again!]
   I-->|Resets user guess|F
   H-->|User is correct|J[Wow! Last guess and you were right! Congrats!]
   H-->|User guesses number not between set parameters|K[That is NOT a number between 1-10! Or maybe you already guessed that. Either way, try again!]
   K-->|Resets user guess|H
   H-->|User is incorrect|L[Unlucky, couldn't get it in 3 guesses. Feel free to try again!
   code displays options to reset or to quit]
   L-->|User resets the game|A
   L-->|User quits|M[See ya later!
   code terminates]
```
## What this code accomplishes
* This code is an outline for a potential random number guessing game

### What each step does
1. Code introduces the game and waits for the user to select a number between 1 and 10
2. Code generates a number between 1-10.
* If the number is correct, the code generates a response to alert the user.
* If number is wrong, the user is notified and the code progresses to the next stage.
* If the user guesses a number outside the parameters, the user is prompted to guess again and returns to the first stage
3. Code waits for the user to guess another number. When a number is guessed, a random number is chosen, except the user's first guess is no longer an option
* If the number is right, the user is notified.
* If the number is wrong, the user is again notified and the code progresses to the next stage
* If the user guesses a number outside of the parameters, the user is set back to the beginning of the stage
4. Code waits for the user to guess. When a number is guessed, a random number excluding the users first 2 guesses is selected.
* If the number is right, the user is notified.
* If the user is wrong, they are told they lost the game and have a choice to leave or reset. If they reset, entire program resets. If they leave, program terminates
* If the user guesses a number outside of the parameters, the user is set back to the beginning of the stage

#### Tweaks to be considered
* I could add something in that tells the user whether their guess was too high or too low, but since the number resets every round, this currently isn't practical.
