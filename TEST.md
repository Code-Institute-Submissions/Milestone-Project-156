# Testing

## Table of Contents

 - [Encountered Issues](#encounteredissues)
 - [Testing User Stories](#testinguserstories)
 - [Testing Functionality](#testingfunctionality)
 - [Testing Compatibility](#testingfunctionality)
 - [Testing Accessibility](#testingaccessibility)
 - [Testing Performance](#testingperformance)
 - [Code Validation](#codevalidation)
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