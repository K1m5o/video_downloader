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

soup = BeautifulSoup(r.content, features="lxml")

for val in soup.findALL("script"):
    if(re.search("talkPage.init",str(val))) is not None:
        result = str(val)

result_mp4 = re.search("(?P<url>https?://[^\s]+)(mp4)", result).group("url")

result_mp4.split("")[0]

print("downloading video from ....." + mp4_url)

file_name = mp4_url.split("/")[len(mp4_url.split("/"))-1].split('?')[0]

print("sorting video in ....." + file_name)
