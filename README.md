# Selenium_Guide
for help in automation with selenium

Launching a driver :- 
      IWebDriver driver = new ChromeDriver();

Navigating to a url :- 
      driver.Navigate().GoToUrl("https://www.example.com");

Finding Elements :-
                       By ID :- 
                      IWebElement elementById = driver.FindElement(By.Id("elementId"));
                      
                      By Name :-
                      IWebElement elementByName = driver.FindElement(By.Name("elementName"));
                      
                      // By XPath
                      IWebElement elementByXPath = driver.FindElement(By.XPath("//xpath"));
                      
                      // By CSS Selector
                      IWebElement elementByCss = driver.FindElement(By.CssSelector("cssSelector"));
                      
                      // By Class Name
                      IWebElement elementByClassName = driver.FindElement(By.ClassName("className"));
                      
                      // By Link Text
                      IWebElement elementByLinkText = driver.FindElement(By.LinkText("linkText"));
                      
                      // By Partial Link Text
                      IWebElement elementByPartialLinkText = driver.FindElement(By.PartialLinkText("partialLinkText"));


Performing actions :-
                      // Clicking an element
                      elementById.Click();
                      
                      // Typing text into an input field
                      elementByName.SendKeys("Hello, Selenium!");
                      
                      // Clearing an input field
                      elementByXPath.Clear();

Switching between frames and windows :-

                      // Switch to a frame by index
                      driver.SwitchTo().Frame(0);
                      
                      // Switch to the default content
                      driver.SwitchTo().DefaultContent();
                      
                      // Switch to a window by handle
                      string mainWindowHandle = driver.CurrentWindowHandle;
                      foreach (var handle in driver.WindowHandles)
                      {
                          if (handle != mainWindowHandle)
                          {
                              driver.SwitchTo().Window(handle);
                              break;
                          }
                      }

waiting for elemnents :- 

                      // Implicit wait
                      driver.Manage().Timeouts().ImplicitWait = TimeSpan.FromSeconds(10);
                      
                      // Explicit wait
                      WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(10));
                      IWebElement dynamicElement = wait.Until(ExpectedConditions.ElementIsVisible(By.Id("dynamicElement")));
                      
Taking screenshots :-  
                      
                      ITakesScreenshot screenshotDriver = (ITakesScreenshot)driver;
                      Screenshot screenshot = screenshotDriver.GetScreenshot();
                      screenshot.SaveAsFile("path/to/screenshot.png", ScreenshotImageFormat.Png);


Handling alerts :-  
                      IAlert alert = driver.SwitchTo().Alert();
                      
                      // Accepting the alert
                      alert.Accept();
                      
                      // Dismissing the alert
                      alert.Dismiss();



                      
