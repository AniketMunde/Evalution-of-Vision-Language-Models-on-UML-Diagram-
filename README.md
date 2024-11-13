

# Evaluation of Vision Language Models on UML Diagrams

This project is focused on evaluating and benchmarking various Vision Language Models (VLMs) for their performance on UML (Unified Modeling Language) diagrams. It involves testing the models’ capabilities in interpreting and describing UML diagrams accurately, which is crucial for applications in software engineering, documentation, and automated system analysis. The models under evaluation include Kosmos-2, LLAVA 1.6, and Qwen-2.

## Table of Contents

- [Project Structure](#project-structure)
- [Objectives](#objectives)
- [Vision Language Models Evaluated](#vision-language-models-evaluated)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Benchmarking Methodology](#benchmarking-methodology)
- [Troubleshooting](#troubleshooting)

## Project Structure

The project is organized as follows:

- **`kosmos2.ipynb`**: Evaluation and analysis of the Kosmos-2 model on UML diagrams.
- **`llava1.6.ipynb`**: Benchmarking of the LLAVA 1.6 model, with insights into its performance on interpreting UML elements.
- **`qwen2.ipynb`**: Testing of the Qwen-2 model to assess its accuracy and relevance in interpreting UML diagram semantics.

Each notebook includes experiments designed to test the model's ability to identify UML components, relationships, and overall structure.

## Objectives

1. **Assess VLM Performance on UML Diagrams**: Analyze and compare each model’s ability to interpret and generate natural language descriptions of UML diagrams.
2. **Identify Strengths and Limitations**: Determine each model's accuracy, contextual understanding, and descriptive capabilities when analyzing UML diagrams.
3. **Provide Benchmarks**: Establish benchmarks for each VLM model to guide future research and applications involving UML diagram processing.

## Vision Language Models Evaluated

- **Kosmos-2**: A multimodal model aimed at interpreting complex visual inputs, which we test for UML understanding and natural language output quality.
- **LLAVA 1.6**: Known for generating detailed descriptions, tested here for its performance on recognizing UML structures and elements.
- **Qwen-2**: A model combining visual and linguistic understanding, evaluated for its ability to recognize UML components and relationships accurately.

## Requirements

- **Python 3.x**
- **Python Libraries**:
  - `transformers`
  - `torch`
  - `numpy`
  - `opencv-python-headless`
  - `matplotlib` (for visualization)
- **Vision Language Model Libraries**:
  - Hugging Face Transformers library (for model handling and testing)

## Installation

1. **Install Required Libraries**:

    ```bash
    pip install transformers torch numpy opencv-python-headless matplotlib
    ```

2. **Clone Project Repositories**:
   - For each model (Kosmos-2, LLAVA 1.6, Qwen-2), follow any additional setup instructions provided by the respective repositories.

## Configuration

1. **Set Up Model Paths**:
   - Configure paths to the model weights and tokenizer files within each notebook as needed.

2. **Add Sample UML Data**:
   - Load UML diagram images or data to be used in testing. Ensure these are in the appropriate directory for each notebook.

## Usage

1. **Run Evaluation Notebooks**:
   - Open each notebook (`kosmos2.ipynb`, `llava1.6.ipynb`, and `qwen2.ipynb`) and execute the cells to load models and run the UML diagram tests.

2. **Perform Benchmarking**:
   - Each notebook contains cells for testing and generating evaluation metrics. Follow the instructions within each notebook for specific tasks.

## Benchmarking Methodology

1. **Accuracy Evaluation**: Measure each model’s accuracy in identifying and describing UML elements like classes, attributes, and relationships.
2. **Contextual Analysis**: Analyze the contextual relevance of generated descriptions to evaluate the depth of understanding.
3. **Performance Metrics**: Record and compare metrics such as description accuracy, response time, and error rate across the models.

## Troubleshooting

- **Model Loading Errors**: Ensure that model weights and tokenizers are correctly configured and paths are accurate.
- **Library Compatibility Issues**: Use the recommended versions of libraries to avoid compatibility issues.
- **Data Loading Issues**: Ensure UML diagrams are correctly formatted and accessible from the notebooks.




