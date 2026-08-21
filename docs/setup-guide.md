# Setup & Deployment Guide

Follow these steps to deploy the AI Content Strategy & Campaign Generator in your environment.

## Prerequisites

Ensure you have active accounts and API credentials for:
*   **OpenAI:** API Key with access to preferred models for the analyst and synthesizer nodes.
*   **Google Cloud Console:** OAuth credentials or Service Account for Google Drive (read access) and Gmail (send access).

## 1. Cloud Storage Setup
1. Create a dedicated folder in Google Drive named `Metrics_Ingestion`.
2. Ensure your raw export files (Audience, Video, Overview) follow a consistent naming convention so the automation can easily find them.

## 2. Importing the Workflow
1. Open your automation platform.
2. Import the workflow JSON file or replicate the node structure shown in the `assets/` diagram.
3. Authenticate the Google Drive, OpenAI, and Gmail nodes.

## 3. Configuring Prompts
1. Navigate to the `src/prompts/` directory.
2. Carefully paste the respective system instructions into the different LLM nodes. 
   * *Note: The "Instagram Analyst" prompt must be distinctly different from the "Strategic Synthesizer" prompt.*

## 4. Testing the Pipeline
1. Upload sample metrics files to your Google Drive folder.
2. Manually trigger the "Execute workflow" node.
3. Monitor the execution through the Normalization layer to ensure keys are mapping correctly.
4. Check the designated destination email inbox for the final generated campaign brief.
