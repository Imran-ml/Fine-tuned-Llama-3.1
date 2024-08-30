<center>
    <img src="https://hyperight.com/wp-content/uploads/2024/07/Meta-Llama-31-1024x576.webp" width=4500">
</center>

# **Mental Health Chatbot: Fine-Tuning LLaMA 3.1**

## **Table of Contents**
- [Introduction](#introduction)
- [Environment Setup](#environment-setup)
- [Installation Instructions](#installation-instructions)
- [Usage](#usage)
- [Model Training](#model-training)
- [Inference](#inference)
- [Saving and Loading the Model](#saving-and-loading-the-model)
- [License](#license)
- [About Author](#about-author)

## **Introduction**
I explore the fine-tuning of LLaMA 3.1, a powerful open-source large language model, to build a chatbot tailored for mental health support. Leveraging advanced quantization techniques with Unsloth, the model is optimized to run efficiently even on hardware with limited resources. By training the model on a mental health dataset from Hugging Face, it is designed to recognize emotional distress and provide supportive responses. This initiative aims to make cutting-edge AI accessible and impactful in the field of mental health, providing a crucial tool for enhancing emotional well-being.

![Mental Health Chatbot](image-placeholder)

## **Environment Setup**

### **Prerequisites**
Ensure you have Python 3.6 or newer installed on your system.

### **Create a Virtual Environment**

1. **Install `virtualenv` (optional):**
   ```bash
   pip install virtualenv
   ```

2. **Create the environment:**
   - With `venv` (Python 3.3+):
     ```bash
     python -m venv env
     ```
   - Or, with `virtualenv`:
     ```bash
     virtualenv env
     ```

3. **Activate the environment:**
   - **Windows:** 
     ```bash
     env\Scripts\activate
     ```
   - **Unix/MacOS:** 
     ```bash
     source env/bin/activate
     ```

4. **To deactivate:**
   ```bash
   deactivate
   ```

### **Dependencies**
Ensure all dependencies are listed in `requirements.txt`. Install them using:
```bash
pip install -r requirements.txt
```

## **Installation Instructions**
To use this project, clone the repository and set up the environment as follows:

### **Clone the Repository**
```bash
git clone https://github.com/Imran-ml/Mental-Health-Chatbot-LLaMA3.1.git
```

### **Setup the Environment**
1. Navigate to the project directory:
   ```bash
   cd Mental-Health-Chatbot-LLaMA3.1
   ```

2. Activate the virtual environment and install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## **Usage**

To run the app, use the following command:
```bash
python -m streamlit run app.py
```

## **Model Training**

This project involves fine-tuning the LLaMA 3.1 model using a mental health dataset. The training script is included in the repository, and you can initiate training using:
```bash
python train_model.py
```

Ensure to adjust parameters as per your requirements within the script.

## **Inference**

To generate responses using the fine-tuned model, you can use the provided inference script:
```bash
python inference.py
```

This script will load the trained model and generate responses based on the provided input text.

## **Saving and Loading the Model**

To save the fine-tuned model:
```bash
python save_model.py
```

To load the saved model for further use:
```bash
python load_model.py
```

You can also push the model to the Hugging Face Hub using the provided script:
```bash
python push_to_hub.py
```

## **License**
This project is made available under the MIT License. See the LICENSE file for more details.

## **About Author**

**Name:** Muhammad Imran Zaman  
**Email:** imranzaman.ml@gmail.com

**Professional Links:**
- [Kaggle Profile](https://www.kaggle.com/imranzaman)
- [LinkedIn Profile](https://www.linkedin.com/in/muhammad-imran-zaman/)
- [Google Scholar Profile](https://scholar.google.com/citations?user=ImranZaman)
- [YouTube Channel](https://www.youtube.com/channel/UCImranZaman)
- [GitHub Repository](https://github.com/Imran-ml/Mental-Health-Chatbot-LLaMA3.1)

---

This README should now display correctly on GitHub or any Markdown viewer.
