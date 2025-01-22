``` mermaid
graph TD
   A[Welcome to the number guessing game! You only get 3 tries, so make them count. Numbers not within the parameters do not count as a guess.];
   A-->B[Select any number between 1-10]
   B-->|User guess between 1-10|C["Generating number..."
   code executes randomNumber]
   B-->|User guesses out of parameters|D[That number is NOT between 1-10! Try again!]
   D-->|Code resets|B
   C-->|User is correct|E[Wow! First try! Today is your lucky day!]
   C-->|User is incorrect|F[That number is incorrect. Try again!
   code generates new randomNumber]
   F-->|User is correct|G[Second try! Still pretty lucky!]
   F-->|User is incorrect,guesses 1-10|H[Incorrect! Only 1 more guess left.
   code generates randomNumber]
   F-->|User guesses number not between 1-10|I[That is NOT a number between 1-10! Try again!]
   I-->|Resets user guess|F
   H-->|User is correct|J[Wow! Last guess and you were right! Congrats!]
   H-->|User guesses number not between 1-10|K[That is NOT a number between 1-10! Try again!]
   K-->|Resets user guess|H
   H-->|User is incorrect|L[Unlucky, couldn't get it in 3 guesses. Feel free to try again!
   code displays options to reset or to quit]
   L-->|User resets the game|A
   L-->|User quits|M[See ya later!
   code terminates]
```
