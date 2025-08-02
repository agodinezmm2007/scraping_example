# scraping_example

# New York State University Course Scraping

This repository contains two Jupyter notebooks for extracting university information and course data from New York State institutions.

## Contents

### 1. wikipedia uni links scraping.ipynb
Extracts university information from Wikipedia's list of New York State colleges and universities.

**Functionality:**
- Scrapes the Wikipedia page for NY institutions
- Focuses on public and private non-profit, non-sectarian institutions
- Extracts institution names, Wikipedia links, and official website URLs
- Outputs data to CSV format

**Dependencies:**
- requests
- BeautifulSoup4
- pandas
- logging

### 2. course scraper_parallelTS.ipynb
Searches for environmental health courses across university course catalogs.

**Functionality:**
- Takes university URLs from the first notebook's output
- Attempts to locate course catalog URLs using common subdomain patterns
- Uses Selenium WebDriver to perform automated course searches
- Searches specifically for "environmental health" courses
- Extracts course names and descriptions
- Implements parallel processing for efficiency
- Outputs course data and failed institutions to separate CSV files

**Dependencies:**
- requests
- BeautifulSoup4
- pandas
- selenium
- webdriver-manager
- concurrent.futures

## Usage

1. Run `wikipedia uni links scraping.ipynb` first to generate the list of NY institutions
2. Use the output CSV as input for `course scraper_parallelTS.ipynb` to extract course data

## Output Files

- `ny_institutions.csv` - List of NY universities with website URLs
- `environmental_health_courses_finalTS.csv` - Found environmental health courses
- `failed_institutions.csv` - Institutions where scraping failed

## Requirements

- Python 3.x
- Chrome browser (for Selenium WebDriver)
- Internet connection for web scraping

## Notes

- The course scraper is specifically configured for catalog systems that use `search_advanced.php` endpoints
- Parallel processing is limited to 10 concurrent threads
- Includes comprehensive logging for debugging and monitoring progress
- Some institutions may fail due to different catalog systems or access restrictions
