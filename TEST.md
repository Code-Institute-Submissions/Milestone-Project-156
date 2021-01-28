# Testing

## Table of Contents

 - [Encountered Issues](#encountered-issues)
 - [Testing User Stories](#testing-user-stories)
 - [Testing Functionality](#testing-functionality)
 - [Testing Compatibility](#testing-functionality)
 - [Testing Accessibility](#testing-accessibility)
 - [Testing Performance](#testing-performance)
 - [Code Validation](#code-validation)
 - [Further Testing](#furthertesting)

## Encountered Issues

### Issues found during the coding process:
 - background hero-image would resize on large or smaller devices:
    - **FIXED** by changing the css code from:
    ```
    background: url("../images/hero-image.jpg") no-repeat center center fixed;
    ```
    to:
    ```
    background: url("../images/hero-image.jpg") fixed;
    background-repeat: no-repeat;
    background-position-x: center;
    background-position-y: center;
    background-size: cover;
    ```

 - background hero-image would distort on large or smaller iOS devices:
    - **FIXED** by adding this attribute ```background-attachment: scroll;``` to the media-queries, according to this [Stack Overflow user's answer](https://stackoverflow.com/a/22866335/14692310)

 - collapsible menu wouldn't close when the navigation links were actioned; it required the user to tap three times to get to the desired section and explore comfortably:
    1. click on the "hamburger" button to expand;
    2. click on the desired section;
    3. and again click on the "hamburger" to close the menu that would cover the top of the section;
    - **FIXED** by adding the following code to the ```.nav-item``` list element: ``` data-toggle="collapse" data-target="#navbarNavDropdown"```. It's been added to the list element instead of the anchor, because it would otherwise disable the anchor's functionality.
 - used [W3C Validator](https://validator.w3.org/) to validate my code: CSS came out clean but HTML showed 8 issues:

 ![W3C Validator Results](https://github.com/alexandruvalentin/Milestone-Project-1/blob/master/readme-images/HTML-validator.jpg)

  - **FIXED** as follows:
  1. changed ```content="IE=7"``` to ```content="IE=edge"```
  2. changed ```<div class="vertical-bar d-none d-lg-block"></div>``` to ```<li class="vertical-bar d-none d-lg-block"></li>```
  3. changed the navigation from a ```section``` element to a ```div```
  4. removed the ```button``` element and transferred its classes to the ```anchor``` element
  5. inserted the missing ```alt``` attritube to the relevant ```img``` element
  6. changed ```area-describedby="emailHelp"``` to ```area-describedby="cta-input"``` to match the element's id, as per this [MDN Web Docs article](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute)
  7. changed ```area-labelledby="signUpModalLabel"``` to ```area-labelledby="signUpModal"``` to match the element's id, as per this [MDN Web Docs article](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)
  8. changed ```area-describedby="emailHelp"``` to ```area-describedby="email"``` to match the element's id, as per the same article as in number 6 of this list

## Testing User Stories
- ### As a user I need:
    - to easily understand the purpose and quality of your services.
    >As the user lands on the website, the hero banner shows a very big heading describing the website's purpose.
    - to navigate through your website to find content and information efficiently.
    >Navigation Bar is fixed to the top of the page, being available at all times and displaying shortcuts to each of section of the page.
    - to find the price range of your services, so I can quickly decide if it fits my budget.
    >The Explore section carousel show all offers available with detailed information about products and pricing.
    - to be able to sign up for the newsletter in order to receive relevant news and offers.
    >The footer section, which also provides all the contact information needed and can easily be navigated to from the navigation menu, provides a form that allows the user to sign up for the newsletter.
    - to follow your social media accounts in order to join the community.
    >Right underneath the newsletter form in the footer, the user can find external links towards the brand's social media accounts.
    - to find reviews from past clients regarding your products and services.
    >The Testimonials section is designated to that purpose specifically. Also accesible from the navigation bar, it shows detailed reviews from Butcher's Bundle users.
    - to be able to get in touch with customer support.
    >On the top right corner, right underneath the navigation bar, there's an alert container that's also available at all times throughout the page which provides the customer support phone number.
    - to access your website across a range of devices.
    >The website was built with a mobile-first approach and its responsiveness makes it available for all devices.

## Testing Functionality
 > ### Checking for broken links
 > From top to bottom, left to right, click every button, form and toggle to check for expected action.
 > - navigation bar is functional, including the brand logo.
 > - menu links are functional and will navigate to the relevant section.
 > - the navigation bar/hero banner Call To Action button opens the modal form and the **X** button/clicking outside of the form closes it.
 > - modal form: the submit button submits the required email address(the email field asks for email format with ```@```) and collects the data inserted.
 > - explore section: carousel prev/next button slide the content respectively and the CTA underneath opens the modal form.
 > - footer: modal form collects the data insterted if submitted(the email field asks for email format with ```@```) and social media buttons each open the expected link in a new tab.