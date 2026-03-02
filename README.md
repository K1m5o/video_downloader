# video_downloader

import requests # getting content from the TED Talk page

from bs4 import BeautifulSoup # web scraping

import re # regular Expression pattern matching 

# for argument parsing

import sys #for argument parsing

# exception Handling

if len(sys.argv) > 1:
    url = sys.argv[1]
else:
    sys.exit("Error: Please enter teh TED Talk URL")

#Test URL = "https://www.ted.com/talks/sir_ken_robinson_do_schools_kill_creativity"

r = requests.get(url)

print("Download to start")
