# LLM fine-tuning

This project implements a healthcare-focused model fine-tuned on a dataset of doctor-patient conversations. The model uses a GPT-based architecture to provide empathetic and professional responses to health-related queries. The notebook contains all necessary steps for loading data, preprocessing and fine-tuning the model.


### Prerequisites
Ensure you have the following installed:

- Python (>= 3.7)
- PyTorch (with GPU support, if available)
- Hugging Face transformers and datasets
- Jupyter Notebook for running the code

Install dependencies using:

```
pip install transformers datasets torch pandas numpy
```

### Running the Notebook

Clone this repository:
```
git clone https://github.com/filipa131/LLM-fine-tuning.git
```

Open and execute the notebook:
```
jupyter notebook doctor-healthcare.ipynb
```

Output:
Fine-tuned GPT2 model saved to ./fine_tuned_model/.
