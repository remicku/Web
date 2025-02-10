# Football Match Data Scraper

This project scrapes football match data from [FBref](https://fbref.com/) and compiles it into a structured dataset. It extracts team fixtures, match statistics, and shooting data for multiple seasons in the English Premier League.

## Features

-   **Web Scraping**: Automatically collects match details and statistics using BeautifulSoup and pandas.
-   **Historical Data**: Fetches data for multiple seasons from 2021 to 2024.
-   **Match Statistics**: Extracts key performance metrics such as shots, shots on target, free kicks, and penalties.
-   **CSV Export**: Saves the scraped data into `matches.csv` for further analysis.

## Installation

1.  Clone this repository:
    
    ```bash
    git clone https://github.com/yourusername/football-data-scraper.git
    ```
    
2.  Install required dependencies:
    
    ```bash
    pip install -r requirements.txt
    ```
    
3.  Ensure you have Python 3.8+ installed.

## Usage

Run the script to start scraping football match data:

```bash
python scraping.py
```

This will generate a `matches.csv` file containing the scraped data.

## Handling Website Rate Limits

The script includes a **`time.sleep(12)`** delay after each request to avoid being blocked by FBref. Websites often have request limits to prevent excessive traffic. By adding this delay:

-   We **reduce the risk of getting temporarily blocked** for making too many requests in a short time.
-   The script runs safely without triggering anti-scraping mechanisms.

If you want faster execution, you **may reduce the delay**, but be aware that setting it too low may result in the script being blocked.

## Data Structure

The output CSV file contains the following columns:

-   `date`: Match date
-   `team`: Name of the team
-   `opponent`: Opposing team
-   `comp`: Competition (Premier League)
-   `gf`: Goals for
-   `ga`: Goals against
-   `sh`: Shots
-   `sot`: Shots on target
-   `dist`: Average shot distance
-   `fk`: Free kicks
-   `pk`: Penalties scored
-   `pkatt`: Penalties attempted
-   `season`: The season the match belongs to

## File Overview

-   `scraping.py`: The main script that scrapes match and shooting data from FBref.
-   `matches.csv`: The generated dataset with structured football match statistics.

## Future Improvements

-   Extend scraping to other leagues and competitions.
-   Add player-specific statistics for deeper analysis.
-   Implement error handling to manage missing or changed data structures on FBref.