# Justice for Otsego

Justice for Otsego is a nonprofit organization dedicated to raising awareness about the health issues affecting Otsego County. Our mission is to use data science to showcase trends in the community. This repository contains resources, project updates, and data analysis to support our ongoing efforts. Thank you for your interest and support!

## Storyboard Video
[Watch on YouTube](https://www.youtube.com/watch?v=OEhunFWDuG8)

---

# Installation and Usage

Below are streamlined instructions for setting up the project. If you need more detailed instructions or encounter any issues, please refer to our [INSTALL.md](./INSTALL.md) file for additional help and troubleshooting tips.

## Prerequisites

- **Python 3.10+**  
  Ensure that you have Python 3.10 or later installed. Check your version by running `python --version` or `python3 --version`.

- **Facebook Account**  
  You need a Facebook account (with a valid username and password) that has access to the “Justice for Otsego” Facebook group. This is required for scraping group data.

## Quick Installation (Using Python venv)

1. **Clone the repository** (or download the ZIP):
    ```bash
    git clone <PROJECT_URL>
    ```
    Alternatively, [download the ZIP](<PROJECT_URL>) and unzip it.

2. **Navigate into the project folder**:
    ```bash
    cd justice-for-otsego
    ```

3. **Create and activate a virtual environment**:
    ```bash
    python -m venv .venv
    ```
   - On Windows:
     ```bash
     .venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source .venv/bin/activate
     ```

4. **Install required packages**:
    ```bash
    pip install -r requirements.txt
    ```

5. **Set up your environment variables**:
    ```bash
    cp .env.example .env
    ```
   Then open `.env` in a text editor and fill in the placeholder values with your own (e.g., Facebook credentials).

6. **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
   After it opens in your browser, navigate to the relevant notebook (e.g., `experiments/fb-scraper.ipynb`).

## Alternative Installation (Using Conda)

If you prefer using Conda (highly recommended by some instructors), follow these steps:

1. **Clone the repository** (or download the ZIP):
    ```bash
    git clone <PROJECT_URL>
    ```
2. **Navigate to the project folder**:
    ```bash
    cd justice-for-otsego
    ```
3. **Create a conda environment** (using an existing `environment.yml` if provided, or manually install packages):
    ```bash
    conda env create --prefix ./envs --file environment.yml
    ```
    If you do not have an `environment.yml` file, you can still do:
    ```bash
    conda create --name justiceenv python=3.10
    conda activate justiceenv
    pip install -r requirements.txt
    ```
4. **Activate the environment**:
    ```bash
    conda activate ./envs
    ```
5. **Set up your environment variables**:
    ```bash
    cp .env.example .env
    ```
    Update the `.env` file with your own values.

6. **Open Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
    From here, open the notebook (e.g., `experiments/fb-scraper.ipynb`) and proceed.

## Usage

- **Facebook Scraper**: The main scraping functionality is currently in `experiments/fb-scraper.ipynb`. Open that notebook in Jupyter to scrape posts and gather data from the Facebook group.
- **Analysis & Visualization**: Our initial analysis and visualization steps are found within the same notebook. We will continue improving and expanding this pipeline to be more robust and user-friendly.
- **Data Directory**: If you have any raw data files (CSV, JSON, etc.), place them in the `data` folder. Make sure to update any file paths within the code or notebooks accordingly.

---

# Additional Resources and Support

If you run into any issues or have questions:
- Submit an issue on GitHub.
- Contact one of the repository maintainers directly.
- Consult the [INSTALL.md](./INSTALL.md) file for more in-depth help.

---

# Contributing

We welcome contributions! Please follow these steps for a smooth collaboration process:
1. Fork this repository.
2. Create a new branch with a descriptive name (e.g. `feature-improved-scraper`).
3. Make your changes or additions.
4. Submit a pull request detailing your changes.

---
