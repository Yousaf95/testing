# Example: Using Our yProv4SQA with the iTwinAI Repository

In this example, we demonstrate how to use our library by analyzing the the [iTwinAI GitHub repository](https://github.com/interTwin-eu/itwinai).  

This repository already utilizes SQAaaS and contains existing assessments. We will use it to  Showcase the capabilities of our library and Extract insights related to software quality and provenance.

## **Clone the repository and navigate to the directory:**
   ```bash
   git clone https://github.com/username/yProv4SQA.git
   cd yProv4SQA
   ```

## **Setup the environment and install dependencies:**

### 1. Create and activate a virtual environment (recommended)

   ```bash
   # Create a virtual environment
   python -m venv yProv4SQA_venv

   # Activate the virtual environment (Linux/macOS)
   source yProv4SQA_venv/bin/activate

   # Activate the virtual environment (Windows)
   yProv4SQA_venv\Scripts\activate
   ```
This ensures that all dependencies are installed in an isolated environment, preventing conflicts with other Python packages on your system.

### **2. Install the library and required dependencies:**
   ```bash
   pip install -e .
   pip install requests
   ```
This installs the library and also installs the requests library, which is required to run the examples.

## **Fetch SQA reports:**
   ```bash
   fetch-sqa-reports itwinai
   ```
This command fetches all SQAaaS assessments for the `itwinai` repository from the [EOSC-Synergy GitHub space](https://github.com/EOSC-synergy). The library then downloads all available reports, removes duplicates and outdated versions, and produces a final cleaned folder used to generate the provenance document. For this example, the output folder will be created as `./itwinai_SQAaaS_reports`.


**Generate provenance documents:**
   ```bash
   process-provenance ./itwinai_SQAaaS_reports
   ```
This command generates a provenance document using the yProv model based on the W3C PROV-DM standard.
It will produce a .json file named ./provenance.json.
