🤖 Many comments on a Facebook post with Selenium
===

1. Install:

* <a href="https://www.jetbrains.com/es-es/pycharm/download/#section=mac">PyCharm CE (free)</a>

* <a href="https://stackoverflow.com/questions/24333330/using-selenium-with-pycharm-ce">Selenium</a>


2. Download marionette or driver for your browser:


* <a href="https://sites.google.com/a/chromium.org/chromedriver/downloads">Chrome</a>

* <a href="https://github.com/mozilla/geckodriver/releases">Firefox</a>

3. Move it to:

```
/usr/local/bin
```

4. Code:

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from time import sleep
from selenium.common.exceptions import TimeoutException
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support.ui import Select
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions
from selenium.common.exceptions import NoSuchElementException

driver = webdriver.Firefox()
driver.get('https://www.facebook.com/')
print
"Opened facebook..."
a = driver.find_element_by_id('email')
a.send_keys('YOUR_EMAIL_HERE')
print
"Email Id entered..."
b = driver.find_element_by_id('pass')
b.send_keys('YOUR_PASSWORD_HERE')
print
"Password entered..."
c = driver.find_element_by_id('loginbutton')
c.click()
print
"Go to post..."
driver.get("https://m.facebook.com/RafAPacHukO/posts/3802972933077744")
sleep(3)

def comment():
    ins = driver.find_element_by_id('composerInput')
    ins.send_keys('YOUR_COMMENT_HERE')
    ins = driver.find_elements_by_tag_name('input')
    for x in ins:
        if 'Comentar' in x.get_attribute('value'):
            x.click()
            return

while True:
    comment()
    sleep(2)

```

PS: 

* Use mobile web facebook (m.facebook.com)
* Get the url with post id (https://m.facebook.com/RafAPacHukO/posts/3802972933077744)


