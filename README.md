# imdb-sentiment-eda
This is actually one of my first EDA projects... so please dont mind the blaring hints of naivety...

This project performs Exploratory Data Analysis (EDA) on the IMDB Movie Reviews dataset. The goal was to visualize the true sentiment drivers in positive vs. negative reviews.

The Problem Standard Word Cloud approaches failed because domain-specific stop words (like "movie", "film", "story") appeared frequently in both positive and negative reviews, drowning out the actual sentiment signals.

Hence to deal with this problem, I engineered a custom filtering pipeline:
  1) Preprocessing: Custom Regex cleaning to handle HTML tags (<br(break)>) and contractions.
  2) Noise Calculation: Used Set Theory (Intersection) to mathematically identify words that appeared in the Top 40 of both classes.
  3) Visualization: Filtered this "Common Noise" dynamically to reveal the hidden sentiment words.

Key Results:

Before: 
  The word "Movie" dominated both positive and negative charts.

After:
  - Positive Reviews are driven by: "Great", "Love", "Best".
  - Negative Reviews are driven by: "Bad", "Plot", "Acting", "Boring".

Visuals:

Positive Words:

<img width="515" height="268" alt="positivewordcloud" src="https://github.com/user-attachments/assets/062948b8-dcdf-4c54-b27d-67adf8205b17" />
<img width="589" height="484" alt="toppositivewords" src="https://github.com/user-attachments/assets/8e085641-07af-4c53-89c4-ab721f1bd310" />

Negative Words:

<img width="515" height="268" alt="negativewordcloud" src="https://github.com/user-attachments/assets/725312a4-9af5-433a-b3e9-ebaaebd39c36" />
<img width="589" height="502" alt="topnegativewords" src="https://github.com/user-attachments/assets/a869e290-3c4b-45dd-b05b-fffeb12d8037" />

Tech Stack:

1) Python
2) Pandas (Data Manipulation)
3) Matplotlib (Visualization)
4) WordCloud (Feature Visualization)
