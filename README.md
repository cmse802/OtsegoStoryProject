
Justice for Otsego
=======
# Otsego

Justice for Otsego is a nonprofit organization dedicated to raising awareness about the health issues affecting Otsego County. Our mission is to use data science to showcase trends in the community. This repository contains resources, project updates, and data analysis to support our ongoing efforts. Thank you for your interest and support!

## Justice for Otsego Project Plan Video
[Watch on YouTube](https://www.youtube.com/watch?v=OEhunFWDuG8)

---

# Installation and Usage

Below are streamlined instructions for setting up the project.

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

**Installation for Intel Mac (Macbook Pro 2019 and before)**

Our installation above works for Windows users and M1 Mac users, but due to architectural struggles with the installation of Geckdriver, some users are unable to run the scraper on their machine.

Firstly, you will follow the first 4 steps of the quick instal guide.

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

5. **Verify your system architecture**
   ```bash
   uname -m
   ```
   If you get x86_64, you should follow from this point.
   You can also try:
   ```bash
   arch
   ```
   If you get i386, you have Intel, and follow ahead from this point.

6. **Locate facebook-page-scraper library in your system**
   We need to update our scraper to stop the autoinstallation and updates of Geckodriver for our systems, as facebook-page-scraper will download the update for M1 Mac, and not Intel Mac.
   Go to your terminal and paste:
   ```bash
   pip show facebook-page-scraper
   ```
   and copy everything from the "Location: ..." line.
   Now type:
   
   ```bash
   open LOCATION
   ```
   And open the folder labeled "facebook-page-scraper".

7. **Open and make changes to "driver_initialization.py"**
   The offending code is found in the "elif browser_name.lower() == "firefox":" loop.
   Change the entire loop to:
   ```python
   elif browser_name.lower() == "firefox":
            browser_option = FirefoxOptions()
            if self.proxy is not None:
                options = {
                    'https': 'https://{}'.format(self.proxy.replace(" ", "")),
                    'http': 'http://{}'.format(self.proxy.replace(" ", "")),
                    'no_proxy': 'localhost, 127.0.0.1'
                }
                logger.info("Using: {}".format(self.proxy))
                return webdriver.Firefox(executable_path="/usr/local/bin/geckodriver",
                                         options=self.set_properties(browser_option), seleniumwire_options=options)
            return webdriver.Firefox(executable_path="/usr/local/bin/geckodriver", options=self.set_properties(browser_option))
        else:
            raise Exception("Browser not supported!")
   ```
   
8. **Uninstall and then install the proper Geckodriver for our architecture**

  ```bash
  # Remove the old or auto-installed geckodriver
  sudo rm -f /usr/local/bin/geckodriver

  # Download the correct geckodriver release for macOS (v0.36.0)
  curl -LO https://github.com/mozilla/geckodriver/releases/download/v0.36.0/geckodriver-v0.36.0-macos.tar.gz

  # Extract the downloaded tar.gz file
  tar -xvzf geckodriver-v0.36.0-macos.tar.gz

  # Make the binary executable
  chmod +x geckodriver
  
  # Move it to a directory in your system PATH
  sudo mv geckodriver /usr/local/bin/
  ```
  Now, facebook-page-scraper will NOT try downloading the wrong version of geckodriver, as we have manually installed our proper version and removed the call to force update.

9. **Set up your environment variables**:
    ```bash
    cp .env.example .env
    ```
    Update the `.env` file with your own values.

10. **Open Jupyter Notebook**:
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

---

# Contributing

We welcome contributions! Please follow these steps for a smooth collaboration process:
1. Fork this repository.
2. Create a new branch with a descriptive name (e.g. `feature-improved-scraper`).
3. Make your changes or additions.
4. Submit a pull request detailing your changes.

---

# Plot Reproducibility 

One of our goals is to ensure the reproducability of the project by making individual instructions that can be used to generate project figures. All figures we generate as part of our project should be able to be reproduced from the instructions located in experiments/figure_reproducibility_instructions.ipynb. 


