# Selenium

Sources

* [Selenium](https://www.selenium.dev/documentation/)
* [ChromeDriver](https://chromedriver.chromium.org/)

## Installation

1. Download the latest [Chrome Web Driver](https://chromedriver.storage.googleapis.com/index.html)
    or Web Driver for a browser of your choosing and save it locally, e.g. to
   `c:\Program Files\GoogleChromeWebDriver\`
2. Add the path to the Web Driver to the `PATH` variable

### Python

1. Install Selenium module via `pip install -U selenium`
2. Test the setup using code below

```python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("http://selenium.dev")
driver.quit()
```
