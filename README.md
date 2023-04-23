# Nbyula-Assignment---Software-test-Engineer
 For this assignment, I will be using the Cypress testing framework to automate the scenarios on the https://nbl.one website. Cypress is a popular JavaScript-based testing framework that allows you to write automated tests for web applications.

To start, I will be automating the following scenario:

Access https://nbl.one/feed, validate if there is at least 1 quest.

Here are the steps I will be taking:

Open the website https://nbl.one in the Cypress browser.
Click on the "Feed" link in the navigation menu.
Verify that at least one quest is displayed on the page.
Here's the code I wrote for this scenario:
describe('Test automation for NBL website', () => {
  it('Validates if there is at least 1 quest on the feed page', () => {
    // Open the website
    cy.visit('https://nbl.one')

    // Click on the "Feed" link in the navigation menu
    cy.get('[href="/feed"]').click()

    // Verify that at least one quest is displayed on the page
    cy.get('.card').should('exist')
  })
})
In this code, I've created a Cypress test that describes the scenario we're testing. In the test, I first use the cy.visit() command to open the website in the Cypress browser. Then, I use the cy.get() command to select the "Feed" link in the navigation menu, and the .click() command to click on it.

Finally, I use the cy.get() command again to select all the cards on the page (which correspond to the quests), and the .should() command to verify that at least one card exists.

Once I have this test code ready, I can run it using the Cypress Test Runner. To do this, I navigate to the project folder in the terminal and run the following command:

arduino
$ npx cypress open
This will open the Cypress Test Runner, where I can select the test I just wrote and run it. Cypress will automatically open a browser window and perform the test steps.

After the test is run, Cypress generates a detailed report that includes information about the test, any errors that occurred, and a video recording of the test run. This report can be found in the "cypress/results" folder.

Additionally, I can set up a pipeline to automatically run these tests whenever changes are made to the codebase. For this, I can use a tool like CircleCI or Jenkins to set up a continuous integration (CI) pipeline. In the pipeline, I can specify the commands to install dependencies, build the application, and run the Cypress tests. I can also configure the pipeline to notify me when tests fail or succeed.

Overall, Cypress is a powerful testing framework that makes it easy to write and run automated tests for web applications. With Cypress, you can quickly set up a testing environment, write tests, and generate detailed reports that help you identify and fix bugs in your application.
I will be using the Selenium C++ language binding to automate the scenarios on the https://nbl.one website. Selenium is a popular framework that allows you to automate web browsers.

To start, I will be automating the following scenario:

Access https://nbl.one/feed, validate if there is at least 1 quest.

Here are the steps I will be taking:

Open the website https://nbl.one in a Chrome browser.
Click on the "Feed" link in the navigation menu.
Verify that at least one quest is displayed on the page.
Here's the code I wrote for this scenario:

#include <iostream>
#include "include/selenium/CppDriver.hpp"
#include "include/selenium/keys.hpp"

using namespace selenium;
using namespace std;

int main()
{
    // Open a Chrome browser
    auto chrome = CppDriver::startChrome();

    // Navigate to the website
    chrome->get("https://nbl.one");

    // Click on the "Feed" link in the navigation menu
    auto feedLink = chrome->findElement(By::cssSelector("[href='/feed']"));
    feedLink->click();

    // Verify that at least one quest is displayed on the page
    auto questCards = chrome->findElements(By::className("card"));
    if (questCards.size() > 0) {
        cout << "At least one quest is displayed on the page" << endl;
    } else {
        cout << "No quests are displayed on the page" << endl;
    }

    // Quit the browser
    chrome->quit();

    return 0;
}
In this code, I've used the Selenium C++ language binding to automate the scenario we're testing. I've created a Chrome browser instance using the CppDriver::startChrome() method, and navigated to the website using the chrome->get() method.

Then, I've located the "Feed" link in the navigation menu using the chrome->findElement() method and clicked on it using the feedLink->click() method.

Finally, I've used the chrome->findElements() method to locate all the quest cards on the page (which have the class name "card"), and checked if there is at least one card using the questCards.size() method. Depending on the result, I've printed a message to the console.

Once I have this code ready, I can compile it using a C++ compiler and run the executable file. Selenium will automatically open a Chrome browser window and perform the test steps.

After the test is run, I can review the output in the console to see whether the test passed or failed.

Additionally, I can set up a pipeline to automatically build and run these tests whenever changes are made to the codebase. For this, I can use a tool like Jenkins or TeamCity to set up a continuous integration (CI) pipeline. In the pipeline, I can specify the commands to build the application and run the Selenium tests. I can also configure the pipeline to notify me when tests fail or succeed.

Overall, Selenium is a powerful framework that makes it easy to write and run automated tests for web applications in C++. With Selenium, you can quickly set up a testing environment, write tests, and generate detailed reports that help you identify and fix bugs in your application.





 I wrote for this scenario, which you can add to a C++ project in your own repository.

Here's the code:
 
#include <iostream>
#include "include/selenium/CppDriver.hpp"
#include "include/selenium/keys.hpp"

using namespace selenium;
using namespace std;

int main()
{
    // Open a Chrome browser
    auto chrome = CppDriver::startChrome();

    // Navigate to the website
    chrome->get("https://nbl.one");

    // Click on the "Feed" link in the navigation menu
    auto feedLink = chrome->findElement(By::cssSelector("[href='/feed']"));
    feedLink->click();

    // Verify that at least one quest is displayed on the page
    auto questCards = chrome->findElements(By::className("card"));
    if (questCards.size() > 0) {
        cout << "At least one quest is displayed on the page" << endl;
    } else {
        cout << "No quests are displayed on the page" << endl;
    }

    // Quit the browser
    chrome->quit();

    return 0;
}





