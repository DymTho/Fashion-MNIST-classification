# Fashion-MNIST Classification – Assignment 3

Machine Learning, NTNU – individual assignment on simple neural networks in Keras.

The whole assignment is in one runnable notebook: **[`Assignment3_Fashion_MNIST.ipynb`](Assignment3_Fashion_MNIST.ipynb)**

## Contents

| Part | What is done |
|---|---|
| Data | Fashion-MNIST loaded with Keras, normalized to 0–1, flattened to 784 features; 50,000 / 10,000 stratified train/validation split; test set kept separate |
| Part A | Baseline (32 ReLU, Adam) + 3 experiments changing one setting at a time; results table; model selected by validation accuracy and evaluated once on the test set |
| Part B | Answers to Q1–Q4 (parameter count, activation/loss, Keras functions and backpropagation, interpretation of the experiments) |
| Part C | Confusion matrix on the test set, per-class accuracy and the most confused class pairs |

All models: 10 epochs, batch size 64, sparse categorical cross-entropy, 10-neuron softmax output, default Keras optimizer settings.

## Results

| Model | Hidden neurons | Activation | Optimizer | Train acc. | Validation acc. |
|---|---|---|---|---|---|
| Baseline | 32 | ReLU | Adam | 0.8862 | 0.8736 |
| Experiment 1 | 64 | ReLU | Adam | 0.8978 | 0.8759 |
| **Experiment 2** | 32 | **tanh** | Adam | 0.8916 | **0.8842** |
| Experiment 3 | 32 | ReLU | SGD | 0.8476 | 0.8515 |

Selected model: **Experiment 2** – test accuracy **0.8671 (86.71 %)**.
The most confused pair is **Shirt ↔ T-shirt/top**.

Results are reproducible: the notebook sets a fixed random seed and enables deterministic TensorFlow operations.

## Declaration of AI use

I used an AI assistant (Claude) as a support tool in this assignment – to help write and structure the
Python code and to help formulate sentences in the explanations. I have run the notebook, checked the results and
answers, and I am able to explain the code and the results.

## How to run

Python 3.10–3.12.

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows  (macOS/Linux: source .venv/bin/activate)
pip install -r requirements.txt
jupyter notebook Assignment3_Fashion_MNIST.ipynb
```

In PyCharm: select `.venv` as the project interpreter and open the notebook. The notebook also runs in Google Colab without changes.
Training all four models takes about a minute on a CPU.
