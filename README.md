# Starbucks Recommendation Engine
**1st Place, UCLA Anderson Data Challenge (January 2026)**

A natural language drink recommendation pipeline that takes free-text customer queries ("something sweet and cold but I'm avoiding dairy") and returns ranked Starbucks product recommendations. Achieved **NDCG of 0.8525** on held-out evaluation queries, winning the challenge.

## How It Works
Three-stage pipeline:

1. **Constraint Extraction (LLM):** Gemini parses each query into structured constraints (category, temperature, dietary restrictions, caffeine level) via a JSON-output prompt.
2. **Product Filtering:** Rule-based filtering of the product catalog against extracted constraints, with caffeine ranges and dietary logic.
3. **Relevance Ranking (Embeddings):** Remaining candidates are ranked by cosine similarity between query and product description embeddings.

## Tech
Python, Gemini API (generation + embeddings), pandas, scikit-learn

## Evaluation
NDCG@k computed against labeled relevance judgments on training queries, with a debugging harness for per-query error analysis.

## Data
Competition datasets (product catalog, labeled queries) were provided for the challenge and are not included in this repo.

## Usage
Open `final_starbucks_pipeline.ipynb`, add your Gemini API key, update the data paths, and run top to bottom.
