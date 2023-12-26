## selenium 爬虫

==不能直接pip install selenium 默认下载最新版本 会出现打开浏览器后自动关闭==

==下载版本4.1.1==

```
pip install selenium==4.1.1
```



### 定位方法

```python
#find_elements_by_xxx的形式是查找到多个元素（当前定位方法定位元素不唯一）
#结果为列表

browser.find_elements(by=By.ID,value="")# 通过标签id属性进行定位

browser.find_elements(by=By.NAME,value="")# 通过标签name属性进行定位

browser.find_elements(by=By.CLASS_NAME,value="")# 通过class名称进行定位

browser.find_elements(by=By.TAG_NAME,value="")# 通过标签名称进行定位

browser.find_elements(by=By.CSS_SELECTOR,value="")# 通过CSS查找方式进行定位

browser.find_elements(by=By.XPATH,value="")# 通过xpath方式定位
#在chrome中可以通过源代码目标元素右键--Copy--Copy XPath/Copy full XPath

browser.find_elements(by=By.LINK_TEXT,value="")# 通过搜索 页面中 链接进行定位

browser.find_elements(by=By.PARTIAL_LINK_TEXT,value="")# 通过搜索 页面中 链接进行定位 ，可以支持模糊匹配
```

or

```python
find_element(By.ID, "id")
find_element(By.NAME, "name")
find_element(By.XPATH, "xpath")
find_element(By.LINK_TEXT, "link text")
find_element(By.PARTIAL_LINK_TEXT, "partial link text")
find_element(By.TAG_NAME, "tag name")
find_element(By.CLASS_NAME, "class name")
find_element(By.CSS_SELECTOR, "css selector")
```

### 加快爬虫方法

为驱动添加选项options

```python
# 创建 ChromeOptions 对象
options = webdriver.ChromeOptions()

# 1. 以无头模式运行 Chrome 浏览器   不打开浏览器，直接在后台爬取浏览器的数据
options.add_argument('--headless')

# 2. 禁用 GPU 加速
options.add_argument('--disable-gpu')

# 3. 禁用信息栏
options.add_argument('--disable-infobars')

# 4. 禁用扩展
options.add_argument('--disable-extensions')

# 5. 禁用 dev-shm-usage
options.add_argument('--disable-dev-shm-usage')

# 6. 禁用沙盒模式
options.add_argument('--no-sandbox')

# 7. 以最大化窗口启动
options.add_argument('--start-maximized')

# 8. 设置窗口大小
options.add_argument('--window-size=1920,1080')

# 创建 WebDriver 时传入 ChromeOptions 对象
driver = webdriver.Chrome(options=options)
```

### 向输入框写入数据

```Python
# 获取输入框 使用driver.find_element(By,name="")方法
# 向输入框传递数据 使用send_keys("value")
ele = driver.find_element(By.CLASS_NAME, "nav-search-keyword")
ele.send_keys("圣诞星")
```

### 按钮点击事件

```python
# 按钮点击事件 click()函数
button = driver.find_element(By.CLASS_NAME, "nav-search-btn")
button.click()
```



## 练习

### 控制自己做的网站 InnoFood😛 

实现自动登录管理员窗口

```
from selenium import webdriver
from selenium.webdriver.common.by import By

# 创建 ChromeOptions 对象
options = webdriver.ChromeOptions()

localUrl = 'http://localhost:8080/adminLogin'
driver.get(localUrl)


button1 = driver.find_elements(By.CLASS_NAME, "el-input__inner")[0]
button2 = driver.find_elements(By.CLASS_NAME, "el-input__inner")[1]
log = driver.find_elements(By.CLASS_NAME, "el-button")[1]
button1.send_keys("admin")
button2.send_keys("admin")
log.click()
```

