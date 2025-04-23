
Justice for Otsego
=======

Justice for Otsego is a nonprofit organization dedicated to raising awareness about the health issues affecting Otsego County. Our mission is to use data science to showcase trends in the community. This repository contains resources, project updates, and data analysis to support our ongoing efforts. Thank you for your interest and support!

## Justice for Otsego Project Plan Video
[Watch on YouTube](https://www.youtube.com/watch?v=OEhunFWDuG8)

## Justice for Otsego Final Video
[Watch on YouTube](https://youtu.be/ujOQ5MFLI9w)

---


# Reproducibility: Quick start

To run the code, you can visit [Google Colab Notebook](https://colab.research.google.com/github/uzairname/OtsegoStoryProject/blob/main/experiments/reproducibility.ipynb)


# Reproducibility: Installation and Usage

Below are streamlined instructions for setting up the project in your local environment

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
3. **Create a conda environment**:
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

## Final Setup: Installing Chromedriver and Exporting Cookies

1. **Export Cookies Using Firefox**
2. Go to Facebook.com and sign into your account using Firefox
3. Install this browser extension, "Cookie-Editor", from the link below.
https://cookie-editor.com/
4. Open the cookie editor while in Facebook and click the button in the bottom right corner to export cookies to JSON.
5. Copy the cookies to your clipboard and go to your experiments folder inside the OtsegoStoryProject diretory.
6. Create a new text file and name is "fb_cookies.json"
7. Paste the cookie json data into text document and then you've completed that step.

8. **Download Chromedriver**
9. Chromedriver is an efficient way to automate the scraping process, and the installation is quite simple.
10. Make sure your current version of Google Chrome is up to date!
11. Go to the link below and download the Chromedriver for your system!
https://googlechromelabs.github.io/chrome-for-testing/
12. Be sure to extract the .zip in your DOWNLOADS folder! It will not work otherwise!
13. We are now done with the Chromedriver installation!

## Now, you can use our scraper!

## Usage

- **Facebook Scraper**: The main scraping functionality is currently in `experiments/fb-scraper.ipynb`. Open that notebook in Jupyter to scrape posts and gather data from the Facebook group.
- **Analysis & Visualization**: Our initial analysis and visualization steps are found within the same notebook. We will continue improving and expanding this pipeline to be more robust and user-friendly.
- **Data Directory**: If you have any raw data files (CSV, JSON, etc.), place them in the `data` folder. Make sure to update any file paths within the code or notebooks accordingly.

---

# Additional Resources and Support

If you run into any issues or have questions:
- Submit an issue on GitHub.
- Contact one of the repository maintainers directly.

---

# Contributing

We welcome contributions! Please follow these steps for a smooth collaboration process:
1. Fork this repository.
2. Create a new branch with a descriptive name (e.g. `feature-improved-scraper`).
3. Make your changes or additions.
4. Submit a pull request detailing your changes.

---

# Plot Reproducibility 

One of our goals is to ensure the reproducability of the project by making individual instructions that can be used to generate project figures. All figures we generate as part of our project should be able to be reproduced from the instructions. To run the code, you can visit [Google Colab Notebook](https://colab.research.google.com/github/uzairname/OtsegoStoryProject/blob/main/experiments/reproducibility.ipynb)


