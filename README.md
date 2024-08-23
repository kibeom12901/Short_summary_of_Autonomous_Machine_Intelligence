# Short_summary_of_-Autonomous_Machine_Intelligence
This repository explores Learned World Models (LWMs) in AI for decision-making in complex environments. It covers action generation, energy minimization, and the integration of cost, memory, and actor modules. It also compares LWMs with embodied AI, highlighting dynamic prediction, hierarchical learning, and non-contrastive methods.

## Importance of Learned World Models (LWMs)

LWMs are crucial for handling complex and uncertain situations, as they allow an AI system to make informed decisions based on learned representations of the world.

## Module Interactions in Action Generation

- **Cost Module**: Measures discomfort or cost, varying based on the situation, much like human responses to different scenarios.
- **Short-Term Memory Module**: Holds information about the past, present, and future to support decision-making.
- **Actor Module**: Plans and executes sequences of actions based on the current state and objectives.
- **Perception-Action Loop**: Directly uses short-term memory for simple, quick actions without complex reasoning.

## Reasoning through Energy Minimization

The system minimizes the total energy cost of action sequences through optimization, storing states and costs after each action (similar to Model Predictive Control - MPC). New skills are integrated as needed.

## Cost Module Details

- **Intrinsic Cost Module**: Drives basic, instinctual behaviors.
- **Trainable Cost Module**: Anticipates long-term outcomes and supports subgoal achievement.

## Self-Supervised Learning (SSL) and Energy-Based Models (EBM)

- **SSL**: The system learns by predicting parts of the data (e.g., future frames in a video) without needing labeled data, creating its own tasks from the input data.
- **EBM**: Assigns "energy" values to data pairs (e.g., two video clips). Low energy indicates compatibility; high energy suggests incompatibility. The model seeks to minimize energy for plausible predictions.

## Handling Multiple Predictions with Latent Variables

- **Latent Variables (z)**: Help the model represent multiple possible outcomes (e.g., a car turning left or right at a fork). The model finds the best latent variable value to minimize energy, making the prediction plausible.

## Avoiding Collapse in Model Training

Collapse occurs when the model fails to distinguish between different outcomes. Regularized Methods prevent this by minimizing the "volume" of low-energy regions, ensuring that only correct outputs have low energy.

## Joint Embedding Predictive Architecture (JEPA)

- **JEPA**: Captures the relationship between two variables (x and y) through learned representations (sx and sy). Instead of directly predicting y from x, JEPA focuses on understanding their relationship via representations.
- **Training JEPA**: Non-contrastive methods like VICReg are used to ensure that the representations are informative, efficient, and avoid collapse.

## Hierarchical JEPA (H-JEPA)

- **H-JEPA**: Extends JEPA to handle predictions at multiple time scales and abstraction levels, enabling both short-term detailed predictions and long-term abstract predictions.
- **Training and Application**: H-JEPA can be trained in stages or as a whole, using non-contrastive methods. It's particularly useful in complex tasks, such as driving, where both immediate and long-term predictions are necessary.

## Optimization and Search Methods for the Actor Module

- **Gradient-Based Optimization**: Used when the world model and cost function are predictable.
- **Alternative Search Methods**: Needed when gradient-based methods fail, such as in complex or unpredictable environments.

## Comparison

### Focus

- **Embodied AI Paper**: Explores how AI interacts with the physical world, focusing on multi-modal integration, tactile perception, and real-world applications like robotics and autonomous vehicles.
- **LWMs Paper**: Centers on how AI models learn and predict in complex, uncertain environments, emphasizing internal mechanisms like energy-based models and hierarchical prediction.

### Core Concepts

- **Embodied AI**: Covers embodied perception, sim-to-real transfer, and physical task planning.
- **LWMs**: Discusses learned representations, energy minimization, and avoiding model collapse.

### Applications

- **Embodied AI**: Practical, real-world tasks requiring interaction with the environment.
- **LWMs**: Theoretical focus on decision-making and prediction in dynamic settings.

### Training Methods

- **Embodied AI**: Multi-modal learning, reinforcement learning.
- **LWMs**: Non-contrastive methods like VICReg for efficient learning.

You can find more information in [this paper](https://openreview.net/pdf?id=BZ5a1r-kVsf).
