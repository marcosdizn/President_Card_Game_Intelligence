# 🎩 President Intelligence

## Introduction
**President Intelligence** is a Java-based project that simulates the popular card game *President*. This project focuses on **AI-driven gameplay**, where opponents learn and improve through training. It is designed for **research and experimentation** in **artificial intelligence and game strategy**.  

This repository contains the **training source code** and **game rules**, which are used to generate intelligent agents—the AI that powers the bots in the [President Card Game App](https://github.com/marcosdizn/President_Card_Game_App) repository.

---

## ✨ Features
- 🃏 **Game Logic Implementation** – Faithfully replicates the President card game rules.
- 🤖 **AI-Powered Opponents** – Uses a **genetic algorithm**, an unsupervised machine learning approach, for decision-making.
- 🏋️‍♂️ **AI Training Scripts** – Includes tools for training and evaluating the neural network.

## ⚙️ Setup & Execution
1. Clone the repository:
   ```sh
   git clone https://github.com/marcosdizn/President_Card_Game_Intelligence/
   ```
2. Navigate to the project folder:
   ```sh
   cd President_Card_Game_Intelligence/
   ```
3. To train the AI (Windows):
   ```sh
   ejecutar.bat
   ```
4. To test AI training:
   ```sh
   verEntrenamiento.bat
   ```

> ⚠️ **Training Considerations:** Training can take a long time, especially with a large population. Modifying parameters in `entrenar.java` is not recommended unless you understand the impact.

## 🧠 AI Explanation
![AI Schema](https://github.com/marcosdizn/President_Card_Game_Intelligence/blob/main/AI_Schema.png?raw=true)

### 🔍 Neural Network Structure
Our AI works with a **neural network** structured as follows:
- 🔴 **1 Input Layer**: 57 inputs, 57 outputs (ReLU activation)
- 🔵 **4 Intermediate Layers**: 57 inputs, 57 outputs (Sigmoid activation)
- 🟢 **1 Output Layer**: 57 inputs, 12 outputs (ReLU activation)

### 📥 Input Layer
- 🎴 **Inputs 0-3**: Last cards played.
- 🃏 **Inputs 4-13**: Player's hand.
- 🗃️ **Inputs 14-51**: Cards already played.
- ⏳ **Inputs 52-54**: Number of cards each player has left.
- 🔥 **Input 55**: Cards in play.
- 🚫 **Input 56**: Number of passes in a round.

### 🏗️ Intermediate Layers
- **4 Layers** process inputs using **Sigmoid activation functions**.

### 📤 Output Layer
- 🔢 **Outputs 0-9**: Weights assigned to each card.
- 🎮 **Output 10**: Number of cards to play (0-4).

The AI determines the best combination based on these outputs.

## 🏋️‍♂️ Training the AI
Our AI is trained using a **genetic algorithm**:
1. 🎲 **Random Neural Networks** – Initial networks have random weights and biases.
2. 🏆 **Selection Process** – The best **3 networks** from a set of **4** continue.
3. 🎭 **Multiple Matches** – 20 games ensure strategic consistency.
4. 🔄 **Recombination** – The top 3 networks create the next generation.
5. 🔁 **Iteration** – The process continues until a stable strategy emerges.

### 🧬 Recombination Process
- Each child inherits **50%** of traits from two parent networks.
- **Phenotypes**:
  - 🏗️ `w_matrix`: Rows of the weight matrix.
  - 🎛️ `vector bias`: Bias values.
- ⚡ **Mutation**: Each gene has a probability of mutation.

### ✅ Verification
- The **best neural network** is logged periodically.
- Each network has a **unique ID** and **generation number**.
- A **user interface** allows visual verification of AI decision-making.

## 🤝 Contributing  
We welcome contributions to enhance functionality and optimize performance. To contribute:  
1. Fork this repository.  
2. Create a new branch for your feature.  
3. Submit a pull request with a detailed description of changes.  
