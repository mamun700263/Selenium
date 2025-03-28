### **🔹 Basic Selenium Questions and Answers**  

#### **1. What is Selenium, and how does it work?**  
Selenium is an open-source automation framework used for testing web applications. It allows interaction with web elements just like a human user would—clicking buttons, filling forms, and navigating pages. Selenium supports multiple programming languages (Python, Java, C#, etc.) and provides bindings for different browsers (Chrome, Firefox, Edge). It works by using WebDriver, which acts as a bridge between the browser and the automation script.  

#### **2. What are the limitations of Selenium?**  
- **Only for Web Applications** – Selenium cannot be used for testing desktop or mobile applications directly.  
- **No Built-in Reporting** – It lacks built-in reporting features for test results.  
- **Handling Captchas & OTPs** – Selenium cannot natively solve captchas or handle OTP-based logins.  
- **Dependency on Browser Drivers** – Each browser requires its own WebDriver, which must be updated regularly.  
- **Limited Support for Parallel Execution** – Running multiple tests in parallel requires additional frameworks like Selenium Grid.  

#### **3. How do you install Selenium and set up a WebDriver for Chrome?**  
1. Install Selenium:  
   ```bash
   pip install selenium
   ```  
2. Download the Chrome WebDriver (Chromium-based browsers require `chromedriver`).  
3. Place the WebDriver in a directory accessible by your system’s PATH.  
4. Use the following script to initialize Selenium with Chrome:  
   ```python
   from selenium import webdriver

   driver = webdriver.Chrome()  # Initialize Chrome WebDriver
   driver.get("https://www.example.com")  # Open a website
   ```  

#### **4. How does Selenium interact with a webpage? Explain how it finds and manipulates elements.**  
Selenium interacts with web elements using **locators** (selectors) like:  
- **ID**: `driver.find_element("id", "element_id")`  
- **Class Name**: `driver.find_element("class name", "class_name")`  
- **XPath**: `driver.find_element("xpath", "//tag[@attribute='value']")`  
- **CSS Selector**: `driver.find_element("css selector", "tag#id.class")`  

Once an element is found, Selenium can interact with it:  
- **Clicking:** `element.click()`  
- **Typing Input:** `element.send_keys("Hello, World!")`  
- **Extracting Text:** `text = element.text`  
- **Scrolling:** `driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")`  

#### **5. What are the different ways to launch a browser in Selenium?**  
- **Using Chrome:**  
  ```python
  driver = webdriver.Chrome()
  ```  
- **Using Firefox:**  
  ```python
  driver = webdriver.Firefox()
  ```  
- **Using Edge:**  
  ```python
  driver = webdriver.Edge()
  ```  
- **Using Headless Mode (No UI Display):**  
  ```python
  from selenium.webdriver.chrome.options import Options

  options = Options()
  options.add_argument("--headless")
  driver = webdriver.Chrome(options=options)
  ```  
- **Using Remote WebDriver (For Selenium Grid):**  
  ```python
  from selenium import webdriver

  driver = webdriver.Remote(
      command_executor="http://localhost:4444/wd/hub",
      options=webdriver.ChromeOptions()
  )
  ```  