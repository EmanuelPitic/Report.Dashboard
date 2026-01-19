# Fake News Detection: Data Insights Dashboard

* Course: 186.868 Visual Data Science (2025W), TU Wien 
* Author: Pitic Emanuel (e12505717)
* Live Demo: https://emanuelpitic.github.io/Report.Dashboard/index.html

## Overview

This interactive dashboard provides a visual analysis of linguistic patterns found in the ISOT Fake News Dataset. Rather than acting as a "black box" classifier, this tool focuses on interpretable features, such as punctuation usage, sentiment density, and title formatting, to help users understand how fake news differs stylistically from real journalism.

## Key Features

* Interactive Visualizations:
    * Feature Importance: Sorted bar chart showing which linguistic features most strongly predict fake news.
    * Distribution Analysis: Switchable Histogram, Violin, and Box plots to compare feature spread.
    * Sentiment Density: KDE (Kernel Density Estimation) plot using VADER sentiment scores.
    * Scatter Plots: Correlations between "shouting" (uppercase titles) and "us vs. them" language (pronouns).

* Brushing & Linking: Clicking a feature in the "Importance" chart automatically updates the distribution analysis.

* Data Quality Analysis: Visual breakdown of dataset duplication rates.

* Filtering: Filter by Fake/Real labels or specific linguistic features.

## Dataset & Methodology

* Source: ISOT Fake News Dataset (University of Victoria).
* Size: ~45,000 articles (Balanced between Real and Fake).
* Preprocessing: The raw text was processed to generate numerical features including:
    * Structure: Title/Body length, sentence counts.
    * Stylistic: Uppercase ratio, punctuation density (?!), and "shouting."
    * Sentiment: Compound scores via VADER.
    * Coherence: Title-Body alignment (Jaccard similarity).

## How to Run

This project is hosted via GitHub Pages and can be accessed directly in the browser:
https://emanuelpitic.github.io/Report.Dashboard/index.html

To run locally (due to CORS policies on local file access):

1. Clone the repository.
2. Run a local HTTP server in the project directory:
   
   # Python 3
   python -m http.server 8000

3. Navigate to http://localhost:8000/index.html

## Tech Stack

* Core: HTML5, CSS3, Vanilla JavaScript.
* Visualization: Chart.js (v4.4).
* Plugins:
    * chartjs-plugin-zoom (Pan/Zoom capabilities).
    * chartjs-plugin-annotation (Median lines and labels).
    * chartjs-plugin-datalabels (On-chart statistics).

## Key Insights

* Duplication: Fake news sources are highly repetitive (46.7% duplicates) compared to Real news (5.3%).
* Stylistics: Fake news relies heavily on "clickbait" tactics: high uppercase ratios in titles, excessive punctuation, and emotional/polarizing language.
* Complexity: Real news typically features longer body text, higher lexical diversity, and more "hedge words" (journalistic caution).

