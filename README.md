# Presidente

## Introduction
**Presidente** is a Java-based project that simulates the popular card game *President*. This project focuses on AI-driven gameplay, where opponents learn and improve through training. It is designed for research and experimentation in **artificial intelligence and game strategy**.

This repository contains the **training source code** and **game rules**, which are used to generate intelligent agents—the AI that powers the bots in the [President Card Game App](https://github.com/marcosdizn/President_Card_Game_App) repository.

## Features
- 🃏 **Game Logic Implementation** – Faithfully replicates the President card game rules.
- 🧠 **AI-Powered Opponents** – Uses a **genetic algorithm**, an unsupervised machine learning approach, for decision-making.
- 🏋️‍♂️ **AI Training Scripts** – Includes tools for training and evaluating the neural network.

## Setup & Execution
1. Clone the repository:
 ```sh
  git clone https://github.com/marcosdizn/President_Card_Game_Intelligence/
  ```
2. Navigate to the project folder.
 ```sh
  cd President_Card_Game_Intelligence/
  ```
   
4. To train the AI (Windows):
 ```sh
  ejecutar.bat
  ```

4. To test AI training:
 ```sh
  verEntrenamiento.bat
  ```
## Considerations
Training can take a long time, especially with a large population.
Modifying training parameters in entrenar.java is not recommended unless you understand the impact.

## IA Explanation

### Layers
Our AI works with a neural network that consists of:
- **1 input layer**: 57 inputs and 57 outputs with ReLu activation functions.
- **4 intermediate layers**: Each with 57 inputs and 57 outputs using sigmoid activation functions.
- **1 final layer**: 57 inputs and 12 outputs with ReLu activation.

### Input Layer
- **Inputs 0-3**: Last cards played.
- **Inputs 4-13**: Player's hand.
- **Inputs 14-51**: Cards already played.
- **Inputs 52-54**: Number of cards each player has left.
- **Input 55**: Cards in play.
- **Input 56**: Number of passes in a round.

### Intermediate Layers
Four layers process the input using **sigmoid activation functions**.

### Output Layer
- **Outputs 0-9**: Weights assigned to each card.
- **Output 10**: Number of cards to play (values: 0-4).

The AI determines the best combination based on these outputs.

## Training
The AI is trained using a **genetic algorithm**:
1. **Random Neural Networks**: Generated with random weights and biases.
2. **Selection Process**: The best 3 networks from a set of 4 continue.
3. **Multiple Matches**: 20 games ensure strategic consistency.
4. **Recombination**: The top 3 networks create the next generation.
5. **Iteration**: The process continues until a stable strategy emerges.

### Recombination
- Each child inherits **50%** of traits from two parent networks.
- **Phenotypes**:
  - `w_matrix`: Rows of the weight matrix.
  - `vector bias`: Bias values.
- **Mutation**: Each gene has a probability of mutation.

### Verification
- The best neural network is logged periodically.
- Each network has a **unique ID** and **generation number**.
- A user interface allows visual verification of AI decision-making.

