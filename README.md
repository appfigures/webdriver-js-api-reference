### API documentation for Selenium WebDriver JS

One day we were writing integration tests using [Protractor](https://github.com/angular/protractor) or [WebDriverJS](https://code.google.com/p/selenium/wiki/WebDriverJs) and simply couldn't find a proper API reference so we generated it: http://appfigures.github.io/webdriver-js-api-reference.

#### Not sure where to start? Try these areas of interest:
- [webdriver.WebDriver](http://appfigures.github.io/webdriver-js-api-reference/symbols/webdriver.WebDriver.html) - The object exposed by `webdriver` (for documentation on methods like `webdriver.get()`, `webdriver.findElement()`, `webdriver.controlFlow()`)
- [webdriver.WebElement](http://appfigures.github.io/webdriver-js-api-reference/symbols/webdriver.WebElement.html) - Represents an element in the DOM such as the return value of `webdriver.findElement()`.
- Here is the definition for all the available locators available on `driver.By` (eg `driver.By.css('#item1')`).

Extracted from `locators.js`:

    webdriver.Locator.Strategy = {
        'className': webdriver.Locator.factory_('class name'),
        'class name': webdriver.Locator.factory_('class name'),
        'css': webdriver.Locator.factory_('css selector'),
        'id': webdriver.Locator.factory_('id'),
        'js': webdriver.Locator.factory_('js'),
        'linkText': webdriver.Locator.factory_('link text'),
        'link text': webdriver.Locator.factory_('link text'),
        'name': webdriver.Locator.factory_('name'),
        'partialLinkText': webdriver.Locator.factory_('partial link text'),
        'partial link text': webdriver.Locator.factory_('partial link text'),
        'tagName': webdriver.Locator.factory_('tag name'),
        'tag name': webdriver.Locator.factory_('tag name'),
        'xpath': webdriver.Locator.factory_('xpath')
    }

### Generating the documentation

Generated using [jsdoc-toolkit](https://code.google.com/p/jsdoc-toolkit/) v2.4.0 (This version of jsdoc toolkit is deprecated, but v3.0 doesn't fully parse the API).

    java -jar jsrun.jar app/run.js -a -t=templates/jsdoc /selenium-webdriver/**/**/*.js
