This is the official repository for the CMSE 495 Justice for Otsego project.

This is the official repository for the CMSE 495 Justice for Otsego project. Justice for Otsego is a nonprofit organization dedicated to raising awareness about the health issues affecting Otsego County. Our mission is to use data science techniques and train models to showcase trends in the community. This repository contains resources, project updates, and data analysis to support our ongoing efforts. Thank you for your interest and support!

Link to our storyboard video:

https://www.youtube.com/watch?v=OEhunFWDuG8


# Installation and Usage

## Prerequisites

You need
- python installed. Any version later than 3.10 works.
- A facebook account with a username and password. Make sure that account has access to the "Justice for Otsego" facebook group.



## Installation

Clone the repo, and run 

```bash
python -m venv .venv
```

Activate the environment.

- On VS code: go to `select python interpreter` and choose .venv
- On windows, run `.venv/Scripts/activate`
- On mac/linux, run `source .venv/bin/activate`

Run the following

```bash
pip install -r requirements.txt
```

```bash
cp .env.example .env
```

And then fill in the values in the `.env` file created with your own.

You can now run the code in the jupyter notebooks. 

## Usage

Code for the facebook scraper is in experiments/fb-scraper.ipynb. The analysis and visualization is rudimentary and experimental right now, but we will develop a more thorough and user friendly pipeline later on.

