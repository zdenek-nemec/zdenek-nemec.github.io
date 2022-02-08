# Selenium

Sources

* [Selenium](https://www.selenium.dev/documentation/)
* [ChromeDriver](https://chromedriver.chromium.org/)

## Installation

1. Download the latest [Chrome Web Driver](https://chromedriver.storage.googleapis.com/index.html)
    or Web Driver for a browser of your choosing and save it locally, e.g. to
   `c:\Program Files\GoogleChromeWebDriver\`
2. Add the path to the Web Driver to the `PATH` variable

## Python

1. Install Selenium module via `pip install -U selenium`
2. Test the setup using code below

```python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("http://selenium.dev")
driver.quit()
```

## Java

1. Start IntelliJ IDEA and start new project
2. Use Maven
3. Add following dependencies to `pom.xml`

    ```xml
    <dependencies>
        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>4.0.0</version>
        </dependency>
    </dependencies>
    ```

4. Create new class and test the setup with the code below

    ```java
    import org.openqa.selenium.WebDriver;
    import org.openqa.selenium.chrome.ChromeDriver;

    public class JavaSelenium {
        public static void main(String[] args) {
            WebDriver driver = new ChromeDriver();
            driver.get("https://selenium.dev");
            String title = driver.getTitle();
            System.out.println("The title is " + title);
            driver.quit();
        }
    }
    ```
