browser automation and web scraping :



  web driver is a tool let you automate and scrabe from the web

  driver = webdriver.Chrome


  options = webdriver.Chromeoptions()
  options.add_arguments("disable-infobars")
    #thats disable the informations bar so not the confuse with the script

  options.addarguments('start-maximized')
    #thats maximize the size of the page in order not to change the content of the page


  options.add_arguments('disable-dev-shm-usage')
    #thats restrict issuse mite happen with linux computer such as repple



  options.add_arguments ('no-sandbox')
    #some pages use sandboxing = conflict with our scraping




  options.add_experemental_features("excludeSwitches " , ["enable-automations"])

  options.add_arguments("disable-blink-features = AutomationControled")

      #allows selenium  not to be detected by  the web


driver.find_element(by = xpath' , value ="....")


example :
from selenium import webdriver

def get_drvier():
  # Set options to make browsing easier
  options = webdriver.ChromeOptions()
  options.add_argument("disable-infobars")
  options.add_argument("start-maximized")
  options.add_argument("disable-dev-shm-usage")
  options.add_argument("no-sandbox")
  options.add_experimental_option("excludeSwitches", ["enable-automation"])
  options.add_argument("disable-blink-features=AutomationControlled")

  driver = webdriver.Chrome(options=options)
  driver.get("http://automated.pythonanywhere.com")
  return driver

def main():
  driver = get_drvier()
  element = driver.find_element(by="xpath", value="/html/body/div[1]/div/h1[1]")
  return element.text

print(main())
