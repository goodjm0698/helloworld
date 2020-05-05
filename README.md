from bs4 import BeautifulSoup
from urllib.request import urlopen

response = urlopen('https://zum.com') 
soup = BeautifulSoup(response, 'html.parser')
i = 1
f = open("새파일.txt", 'w')
for anchor in soup.select("span.d_keyword"):
  data = str(i) + "위 : " + anchor.get_text() + "\n"
  i = i + 1
  f.write(data)
f.close()
