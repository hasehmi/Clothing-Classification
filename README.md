# Fashion MNIST — CNN Clothing Classifier

A convolutional neural network that classifies grayscale clothing images into 10 categories (T-shirt, trouser, pullover, dress, coat, sandal, shirt, sneaker, bag, ankle boot).

## Project structure

```
├── cloth_classifier.ipynb   # Full pipeline: preprocessing → CNN → training → evaluation
└── requirements.txt
```

## Dataset

[Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) — 70,000 28×28 grayscale clothing images, loaded directly via `tensorflow.keras.datasets` (no manual download needed, just an internet connection on first run).

## Approach

1. **Preprocessing** — reshape to add an explicit channel dimension, normalize pixel values to [0, 1], one-hot encode labels.
2. **Model** — a 2-block CNN (32 then 64 filters, each with max pooling) feeding into dense layers — sized appropriately for 28×28 grayscale images.
3. **Training** — 10 epochs with validation tracked each epoch.
4. **Evaluation** — test accuracy plus a visual check of individual predictions (correct vs. incorrect, color-coded).

## Results

| Metric | Value |
|---|---|
| Training accuracy (epoch 10) | 96.1% |
| Validation accuracy (epoch 10) | 90.9% |

The ~5-point gap between training and validation accuracy indicates mild overfitting — expected and unremarkable for a CNN trained this many epochs without dropout or augmentation. ~91% is a solid, credible result on Fashion-MNIST, which is intentionally harder than classic MNIST digits (several classes, like shirt/pullover/coat, are visually similar even to a human at 28×28 resolution).

## Running it locally

```bash
pip install -r requirements.txt
jupyter notebook cloth_classifier.ipynb
```

The final evaluation and prediction-visualization cells need to be run (they require downloading Fashion-MNIST, so they need an active internet connection) — they use the model trained in the cell above them.

## What I'd improve with more time

- Add dropout and/or light data augmentation (random shifts/flips) to close the training/validation accuracy gap.
- Try a slightly deeper architecture or batch normalization, compared against this baseline rather than assumed to be better.
- Look at a full confusion matrix specifically for the visually similar classes (shirt/coat/pullover) to see where most errors concentrate.

## Author

Ans Tanveer Hashmi — BS Data Science, MNS University of Agriculture, Multan.
[LinkedIn] · [GitHub]
