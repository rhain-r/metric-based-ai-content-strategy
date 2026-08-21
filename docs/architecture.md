# System Architecture

This document outlines the architecture of the Metric-Based AI Content Strategy pipeline. The system is designed as a sequential ETL (Extract, Transform, Load/Interpret) flow, passing data through distinct layers of refinement.

## Layer Definitions

1. **Data Ingestion Layer:** Connects to Google Drive to locate and download raw analytical reports (CSV/JSON).
2. **Data Partitioning Layer:** Splits the massive raw data payload into distinct, manageable streams (Audience, Video, Facebook metrics, Instagram metrics).
3. **Data Normalization Layer:** Standardizes the data. It renames disparate keys from different platforms into a unified format and calculates baseline metrics before handing them to the AI.
4. **Data Processing Layer:** The first tier of AI reasoning. Specialized OpenAI models are deployed here (e.g., "Instagram Analyst", "Video push analyst") to draw isolated insights from their specific data streams. 
5. **Data Interpretation Layer:** All isolated insights are merged. A 'Strategic Synthesizer' OpenAI model reviews the complete picture (TikTok + FB + IG) to identify overarching trends and correlations.
6. **Campaign Generator Layer:** The final execution phase. An OpenAI model takes the synthesized strategy, builds a prompt, generates a comprehensive marketing campaign, and formats the output to be emailed via Gmail.
