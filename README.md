# Rock-Paper-Scissors AI (with TensorFlow)

This is a Python-based Rock-Paper-Scissors game where you play against an AI bot that learns your behavior using machine learning! After every 10 rounds, the AI retrains itself based on your past moves and tries to outsmart you in future rounds.

---

## Features

- Classic Rock-Paper-Scissors gameplay
- AI bot that learns and adapts using TensorFlow
- Retrains the model after every 10 user inputs
- Keeps track of scores (User vs AI)
- Predicts next user move based on historical data and counters it

---

##  Requirements

Make sure you have Python 3.7+ installed, then install dependencies:

```bash
pip install tensorflow numpy
```

---

##  How It Works

###  Game Logic

- The user plays against the AI by entering one of: `rock`, `paper`, or `scissors`.
- The AI initially plays random moves.
- After every 10 rounds, it uses the sequence of user moves to train a neural network that predicts the **next** move the user might make.
- Based on this prediction, the AI chooses the counter-move:
  - Rock beats Scissors
  - Scissors beats Paper
  - Paper beats Rock

###  Model Details

- The AI model is a simple neural network using **TensorFlow Keras**:
  - Input: The last user move (as an integer)
  - Output: Probabilities of the user’s next move
  - Architecture:
    - Embedding layer (maps move IDs to vectors)
    - Flatten layer
    - Dense hidden layer (ReLU)
    - Output layer with softmax (for 3 class probabilities)

---

##  Project Structure

```
rock-paper-scissors-ai/
│
├── rps_ai.py            # Main game file (your script)
├── README.md            # You're reading this!
```

---

##  How to Play

Run the game with:

```bash
python rps_ai.py
```

Then, follow the prompt:

```
 Rock-Paper-Scissors (AI-Powered) — Type 'exit' to quit.

Your move (rock/paper/scissors):
```

Enter one of the valid moves. After every 10 rounds, you'll see:

```
retraining AI...
```

At any time, type `exit` to quit and see the final scores.

---

##  Limitations

- The model only considers the **last move** to predict the next one (for simplicity).
- Prediction accuracy improves as the number of rounds increases.
- AI adapts based on frequency and patterns in your inputs, but it's still quite a basic strategy.

---

## Example Output

```
Your move (rock/paper/scissors): rock
AI chose: paper
AI Wins

Your move (rock/paper/scissors): scissors
AI chose: rock
AI Wins

...

retraining AI...
```
