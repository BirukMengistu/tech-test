# Technical assignment
The goal of this assignment is to complete as many tasks as possible listed below in the TODO list. 

## Scenario
A developer has built a landing page for a Live Video Shopping event, but there are still bugs to solve and improvements to make before the page can be used in production. We need you to update the code and fix the tasks listed in the TODO list further down on this page so everything is working as expected once launched. 

## Expectation
Here is the specification and high-level requirements for this landing page.

On this landing page, we are going to promote a Live Video Shopping show. 

The landing page consists of:
- **A countdown:** A graphical countdown. We should be able to set the date and time of the event. The countdown should disappear when done.
- **A header:** This header should have the value of 'We go live in' before the countdown is done. After the target time is passed, the value of the header should be 'We are live!'.
- **A CTA element:** A card including an image and a button. The whole card should be clickable and trigger the Bambuser Player with a recorded test show.

## Test the current behavior
### 1. Run the project
You are able to run the current project in either way below:
 - In the terminal, run `yarn start` within the project working directory 
 - Or, open the `src/index.html` in a browser

### 2. Modify the target time
In order to test the countdown on different occasions, in the `src/index.html`, you need to update the `data-date` and `data-time` to a closer time (e.g. current time + 1 min). So you can see how the count down behaves when it reaches the target time.
## TODO
  - [ ]  Make the countdown loop stop once it reaches the target time. Currently, the countdown continues with minus values. 
  - [ ]  Make the countdown element disappear after the target time is reached.
  - [ ]  The CTA element should show up when the countdown is done.
  - [ ]  The default font for the landing page is set to `Neue Haas Grotesk Display`, but the font is not applied. Investigate why and provide a solution.
  - [ ]  Center the `wrapper` element by modifying the CSS. The `wrapper` element is not fully centered (It is horizontally centered but not vertically). 
  - [ ]  The header text must be changed to 'We Are Live!' when the countdown is done.

## Questions
Once you have fixed the CTA button, you should be able to click it. On click, the Bambuser One-to-many player will be opened. When clicking a product in the player, you will see an error page. We need you to explain as much as possible in the field further down: 
   - What is the error?
   - Why does it happen, what is the reason for this error?
   - Potential solution(s)?

### Answer
      Place a brief explanation here. You can explain this further during the technical interview.
      answer 
      - What is the error?
       HTTP security headertype , refused to display 'www.xxx.com/shop''X-Frame-Options' to sameorigin
      - Why does it happen, what is the reason for this error?
       -  when we try to display or modify third party content on iframe.
      -   Reason being that they send an "X-Frame-Options: SAMEORIGIN" response header. This option prevents the browser from displaying iFrames that are not hosted on the same domain as the parent page. 
      -  Potential solution(s)?
       This is a security feature to prevent click-jacking.    
       
      apply X-Frame-Options directives 
           X-Frame-Options: deny
           The deny directive completely disables the loading of the page in a frame, regardless of what site is trying. Below is what the header request will look like if this is enabled.
           X-Frame-Options: sameorigin
           The sameorigin directive allows the page to be loaded in a frame on the same origin as the page itself. Below is what the header request will look like if this is enabled.
           X-Frame-Options: allow-from https://www.example.com/
           allow-from uri directive allows the page to only be loaded in a frame on the specified origin and or domain. Below is what the header request will look like if this is enabled.
           
           Content-Security-Policy header
            Content-Security-Policy header with the frame-ancestors 'self'; value to each outgoing response his CSP directive allows you to get the same result as the X-Frame-Options header with the sameorigin value.
            
           - frame-ancestors 'none'; : This prevents any attempt to include the page within a frame.
           - frame-ancestors https://www.authorized-website.com;: This directive allows you to specify which website is allowed to embed the page in a frame.
           
           
           
          
See how to reproduce the error: [Video](producing-iframe-error.mp4)




## How to deliver the assignment
- You will receive the assignment in a `.zip` file that you can unzip and start working on it.
- Make sure you read the README.md carefully before you start working on the tasks.
- *Would be nice* to use Git and commit your changes. You can use your local Git repository or a private remote repository.
- When you are done, make a zip archive of your project, including the .git directory *in case you chose to use Git*.
- There is no right or wrong, so, feel free to be creative while delivering the expectations.
- If you have any questions, reach out via email.