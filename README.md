# Web-Crawler-note
Web Crawler  。网络爬虫。


网络爬虫 curl 请求。返回的数据进行分析。获取到想要的数据。  

python 。做的比较好。应该就是 个各种session 、cookie 、header ;对返回的各种形式的数据  解析做的非常好。  

任何人来做，都是这两部。  

Demo   参考 https://blog.csdn.net/csqazwsxedc/article/details/68498842  

1、touch test.py

2、在test.py 中写入
```
import requests
from lxml import html
url='https://movie.douban.com/' #需要爬数据的网址
page=requests.Session().get(url)
tree=html.fromstring(page.text)
result=tree.xpath('//td[@class="title"]//a/text()') #获取需要的数据
print(result)
```
3、执行此脚本
python test.py  

4、数据输出  
```
['迦百农', '绿皮书', '驯龙高手3', '速成家庭', '阿丽塔：战斗天使', '肤色', '死亡天使', '黎明墙', '小小巨人', '出·路']
```

OK !!！  到此成功！！！

然后开始抓取 脉脉数据，通过web端的 招聘页面。  
