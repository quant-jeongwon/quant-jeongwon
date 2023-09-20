- 👋 Hi, I’m @quant-jeongwon
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
quant-jeongwon/quant-jeongwon is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.

--->
# naver blog 검색
'''
##### 요청 URL를 작성, 요청결과를 json 형식으로 변환하여 return 한다. 
import requests
import json
import urllib.request
from urllib.parse import quote


client_id = "dZld5466VWxrKooDKlSX"
client_secret = "VOaxDMgBwa"


def call(keyword, start):
    encText = quote(keyword)
    url = "https://openapi.naver.com/v1/search/blog?query=" + encText +"&sort=sim&display=100&start="+str(start)
    result = requests.get(url=url, headers ={"X-Naver-Client-Id":client_id, "X-Naver-Client-Secret":client_secret} )
#     print(result)
    return result.json() 
call('김천',1)
D= call('김천',1)
D.keys()
D["items"][0]['description']
def search(keyword):
    lst = []
    for page in range(0,10):  # [0,1,2,3,4,5,6,7,8,9]
        lst = lst + call(keyword, page *100 +1)['items']
    return lst

'''
[네이브 블로그](http://blog.naver.com/5html)
