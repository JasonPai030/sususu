# sususu
import requests
from bs4 import BeautifulSoup


url = 'https://2023ntcu.ntcu.edu.tw/'
headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'}
response = requests.get(url, headers=headers)
response.encoding = 'utf-8'
soup = BeautifulSoup(response.text, 'html.parser')


keyword = '臺中'
count = 0

for text in soup.stripped_strings:  
    if keyword in text:
        count += 1

print(f'{keyword} found {count} times')
