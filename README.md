# VIP Seminar Scheduler

This script automatically generates a seminar schedule from a list of names and roles.

## Requirements
- Python
- NumPy
- Pandas

## Installation
- Open a bash terminal and run
```
    git clone https://github.com/kvdomingo/vip-seminar-scheduler
```
- `cd` inside the folder
- Make sure you have `numpy` and `pandas` available in your Python installation. If not, simply run
```
    pip install -f requirements.txt
```

## Usage
- In the same directory, create a file named `mems.txt` and, on separate lines, provide a [nick]name and tag for each speaker, delimited by a comma. A tag of `Senior` indicates that person will only speak once, while a tag of `Junior` indicates the person may speak multiple times. Example:
```
    Matthew,Senior
    Mark,Senior
    Luke,Junior
    John,Junior
```
- Create a file named `roles.txt` and provide a comma-separated list of roles surrounded by single-quotes. Example:
```
    'Speaker1','Speaker2','Evaluator1','Evaluator2'
```
- In the terminal, run the program as follows:
```
    python name_gen.py --start-date [START_DATE] --end-date [END_DATE] --random-seed [RANDOM_SEED] --filename [FILENAME]
```
- where `START_DATE` and `END_DATE` are dates in Python `datetime` format YYYY-M-D (e.g. 2020-1-20), and can be any day. The scheduler will automatically pick out the Mondays within the range, inclusive; `RANDOM_SEED` is an integer for seeding the PRNG; `FILENAME` is the name of the file (in `csv` format) to save to. Examples of running the program are as follows:
```
    python name_gen.py --start-date 2020-1-20 --end-date 2020-5-13 --random-seed 69 --filename schedule.csv
    python name_gen.py -sdl 2020-1-20 -edl 2020-5-13 -rs 69 -f schedule.csv
```
- where `-sdl`, `-edl`, `-rs`, and `-f` are the shorhand argument notations.
