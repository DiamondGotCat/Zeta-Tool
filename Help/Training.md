Thank you for your interest in this project.  
This document explains one way to support Hinode-AI: contributing via pre-trained models.

### Requirements

Before proceeding, ensure you have the following:  
1. Time  
2. Electricity costs  
3. A basic understanding of Python  
4. A relatively powerful machine  
5. Familiarity with Hugging Face (for publishing)  

This approach requires a machine with at least **16GB of GPU memory (VRAM)**.  
The weaker your GPU, the longer the process will take.  

For reference, training using the Azuki-2n dataset on an M3 chip with 16GB of shared RAM takes at least 30 minutes and can take up to 2 hours.  
If you use the same machine for other tasks during training, it may take even longer.  
Thus, using a secondary PC is recommended.

---

### 1. Ensure Python Is Installed

If Python is not installed, the easiest method is to use **Anaconda** or **Miniconda**.  
For advanced users, **Pyenv** can also be used on Linux or macOS.  

We recommend Python versions **3.10** or **3.11** for stability.

---

### 2. Clone the GitHub Repository

Clone this repository using the **Git command**, **GitHub CLI**, or a GUI tool.

---

### 3. Training the Model

The most time-consuming step is training the model.  
To make this easier, a `training.py` script is located in the root directory.

#### Training Options

After launching `training.py`, you will be prompted to make a selection.

#### Dataset Path

Next, you will be asked to provide the path to the dataset. Hinode-AI uses a custom JSON format.  
We recommend selecting one of the provided templates.

Hinode-AI includes the following datasets as of this writing:  
- `data_templates/OpenO1-SFT.json`  
- `data_templates/azuki-2n.json`

Here is a table summarizing the characteristics of the included datasets:

| Dataset Name          | Characteristics                                                                                | Recommended Base Model | Estimated Training Time   | Notes                                                                                     | Dataset Path                     |
|-----------------------|------------------------------------------------------------------------------------------------|------------------------|---------------------------|------------------------------------------------------------------------------------------|-----------------------------------|
| **OpenO1**            | Published by the OpenO1 team on Hugging Face.<br> Includes reasoning processes for better answers.<br> High information density. | openai-community/gpt2 (GPT-2 Small) | Long (~12 hours)          | May yield high-quality answers.<br> Training time tends to be long due to high data volume. | `data_templates/OpenO1-SFT.json` |
| **Azuki 2n**          | Created for version 2n of the Azuki.ai project.<br> Lower answer quality than Hinode-AI.       | openai-community/gpt2-large (GPT-2 Large) | Moderate (~30 min–2 hrs)  | May lack information density, so v2-medium or higher is recommended.                     | `data_templates/azuki-2n.json`   |

---

### 4. Outputs

Intermediate results will be saved in the `results` folder.  
The final model will be saved in the `trained_model` folder.

---

### 5. Upload Your Model

Finally, upload the contents of the `trained_model` folder to your own account as a model.  
Include the following details in the description:  
- Information about Hinode-AI  
- The base model used  
- The name of the dataset used
