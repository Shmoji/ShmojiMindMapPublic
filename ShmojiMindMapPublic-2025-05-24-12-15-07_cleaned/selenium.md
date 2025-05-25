  * NOTE: to start, i just wanna be able to order food using selenium
  * TODO soon
    * [ ] study how to make that food order for at least 1 hour
  * what is it?
    * GPT4: a suite of tools for automating web browsers. Selenium provides a way to programmatically interact with webpages by simulating user actions like clicking buttons, entering text, navigating through pages, and more. It supports multiple programming languages like Python, Java, C#, etc
    * me: you write code in any language to do browser automation. Selenium at some point when code being run - converts your code to webdriver protocol commands - which are HTTP requests. Then dey be ready for handling/executing in browser by a webdriver
  * noteworthy points
    * i noticed [[noosphere protocol]] tests didnt use selenium and that confused me, so i asked how code was getting converted to webdriver protocol commands
      * cdata: a lot of selenium was for jury rigging web browsers to be ran in scripted fashion. Nowadays, web browsers have debugging protocols for this purpose, and the selenium API-side has been factored into "webdrivers" that interface with these protocols. so if you have chrome and chromedriver installed, that is enough to "drive" chrome
        * me: sounds like he basically said dat shit built into webdrivers nowadays
  * related
    * [[webdriver, chromedriver]]
