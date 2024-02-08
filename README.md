from bs4 import BeautifulSoup
import requests

product = input()

url = "https://www.avito.ru/rossiya?q" + product
request = request.get(url)
bs = BeautifulSoup(request.text, "html.parser")

all_links = bs.find_all("a", class_="styles-module-root-QmppR styles-module-root_noVisited-aFA10")

for link in all_links:
  print("https://www.avito.ru" + link["href"])
