# Investing Bulk Data Scraper

A web scraper developed to scrape historical data of any instrument listed on the website.
It is capable of scraping historical data of multiple instruments in a single run.

## Historical Data CSV file includes: 

- Price / Closing price
- Open
- High
- Low
- Volume
- Change percent

`Note: The get_categories_for_symbol.ipynb file can be used to extrat all possible instruments listed on investing.`

File Directory:-

`get_categories_for_symbol.ipynb`: Use it to extract all possible symbols of instrument listed on investing.

`get_historical_data.ipynb`: Main file to extract historical data of any instrument.

`user_agents.py`: Contains a list of user_agents to prevent from blocking.

## Installation

- Make sure you have python(version>=2.7) installed in your system.

- Install [Jupyter Notebook](https://jupyter.org/install) and start the server locally.

- OR, open the files, in any code editor and install the jupyter extension.

- `pip` install the initial cells i.e the first code cell, to get the dependencies.

- Run the notebook.

- User, will be prompted for 3 inputs:

    - List of symbols, that is the instruments you wish to extract.
    - Start Date: from which date, you wish the data to extract.
    - End Date: to the date, you want the data to extract.

- You will get all the csv, under a folder `historical_data_csv` in the same directory.

## Techincal Workflow

User can provide a single instrument input or a list of instruments as input, to extract historical data and save the csv format files. The input provided goes as a parameter for a post request, and extract the unique id that investing provides for each of it's instrument. Then, the unique_id, say the `investing_code` is passed as a parameter to the historical data api of investing. And the json formatted data of historical section is scrapped. Then, the data is saved to a csv format file with input as it's filename in a directory. For multiple input fields, the concept of multithreading is applied, to extract more data in less time.

`NOTE:  To get a better performance, add a buffer of 10-12 sec after extracting 1000 instruments.`

### Feel Free to find issues & Contribute.. !