# spring-starter
spring starter project

from urllib.request import urlopen
from bs4 import BeautifulSoup
from selenium import webdriver

driver = webdriver.Chrome(executable_path=r'C:\dev\chromedriver_win32\chromedriver.exe')
driver.implicitly_wait(3)
# base_url='http://movie.daum.net/moviedb/grade?movieId=2725&type=netizen&page={}'
base_url='https://search.naver.com/search.naver?where=realtime&sm=tab_jum&query={}'

review_list=[]
# file = open('data1.txt','w', encoding='utf-8')
# for n in range(5):
url = base_url.format('vibe')
# webpage=urlopen(url)
driver.get(url)
webpage=driver.page_source
source=BeautifulSoup(webpage,'html5lib')
# driver.find_element_by_css_selector('p_more moreBtn').click()
# driver.find_element_by_xpath("//a/u[contains(text(),'더보기')]").click();
driver.find_element_by_css_selector("p_more._moreBtn").click();
# reviews=source.find_all('p',{'class':'desc_review'})
reviews = source.find_all('span', {'class': 'cmmt _twitter'})
for review in reviews:
    print(review.get_text().strip())
        # review_list.append(review.get_text().strip())


    # for review in review_list:
    #     file.write(str(review) + '\n')

# file.close()




