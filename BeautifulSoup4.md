https://www.crummy.com/software/BeautifulSoup/bs4/doc/

    from bs4 import BeautifulSoup
    soup = BeautifulSoup(html, 'html.parser')
    tags = soup.find_all('span')
