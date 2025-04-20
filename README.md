# Image Classification with OpenAI's Contrastive Language-Image Pretraining (CLIP) model

CLIP (Contrastive Language-Image Pretraining) is a cutting-edge model from OpenAI that enables image classification without explicit training on specific categories.

Focus: This project focuses on implementing and fine-tuning OpenAI's model for practical applications.

- CLIP official link: [CLIP: Connecting text and images - Jan 5, 2021](https://openai.com/index/clip/)
- Paper: [Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020)
- Code: [CLIP - GitHub](https://github.com/openai/CLIP)

## Project Scope

- Use OpenAI’s CLIP model to classify images based on text descriptions.
- Implement a web app where users upload an image and describe what they want to classify.
- Compare CLIP’s performance against a traditional CNN trained on a subset of ImageNet.

## Skills Showcased

- Vision-Language models
- Transfer learning
- Model evaluation.

## Project Plan

### Phase 1: Traditional CNN Baseline Implementation

- Data: Subset of ImageNet as Dataset
- CNN Model: Pretrained ResNet18/VGGNet16
- Training and Evaluation

### Phase 2: Setup and Core CLIP Implementation (Zero-Shot)

- Setup .env: Install necessary libraries: torch, torchvision, ftfy, regex, tqdm, Pillow (PIL), numpy, and the official openai/clip library (pip install git+https://github.com/openai/CLIP.git)
- Pretrained CLIP Model (eg ViT-B/32)
- Develop Core Classification Script:
  - Write a Python script that:
  - Takes an image path and a list of text descriptions (potential classes) as input.
  - Loads and preprocesses the image using CLIP's image preprocessor.
  - Preprocesses and tokenizes the text descriptions using CLIP's tokenizer.
  - Encodes the image and text prompts into embeddings using the loaded CLIP model.
  - Calculates cosine similarity between the image embedding and each text embedding.
  - Computes probabilities using a softmax function over the similarities.
  - Outputs the predicted class(es) and their associated probabilities.
- Test and evaluate

### Phase 3: Comparison and Analysis

- Use exact same test set images for both models (baseline vs CLIP)
- Quantitative Analysis: Tables with accuracy, etc.
- Qualitative Analysis: Discuss the strengths and weaknesses observed:
  - CLIP: Flexibility (no retraining needed for new classes), robustness to phrasing (potentially), reliance on prompt quality.
  - CNN: High accuracy on trained classes, potential overfitting, inability to classify outside its known categories.

### Phase 4: Web Application Development

- Web Framework: Streamlit
- Design UI:
  - Upload image
  - Enter a comma-separated list of text descriptions (potential classes) they want to classify the image against.
  - Classify button!
- Backened:
  - Integrate trained CLIP classification script with web app backend
  - Handle image uploads, process user-provided text prompts
  - Call the CLIP model to get predictions
- Display results:
  - Show the uploaded image
  - Display the top N predicted classes (based on the user's text prompts) along with their probabilities.

### Phase 5: Documentation

- README.md
  - Project description and goals.
  - Setup instructions (environment, libraries).
  - How to run the web application.
  - How to run the CNN training and evaluation scripts.
  - How to run the comparison script.
  - Summary of results and comparison analysis.
