# Portfolio

## Summary of the project

This piece of work focuses on building a polished and responsive portfolio, which always showcases an updated view of my github projects.

## Deployed URL and GitHUb repository

Link to Deployed page : [https://am0031.github.io/portfolio/](https://am0031.github.io/portfolio/)

Link to Github repo : [https://github.com/Am0031/portfolio](https://github.com/Am0031/portfolio)

## Table of content

- [Why a Portfolio](#why-a-portfolio)
- [Development steps](#development-steps)
- [Technologies](#technologies)
- [Wireframe design](#wireframe-design)
- [HTML skeleton](#html-skeleton)
- [CSS for page structure](#css-for-page-structure)
- [CSS for page responsiveness](#css-for-page-responsiveness)
- [CSS for improved interactio ](#css-for-improved-interaction)
- [Upcoming features](#upcoming-features)

## Why a Portfolio

A portfolio is an important tool which can be very helpful when looking for work as a web developer. This is a great platform to showcase the different projects worked on and give access to the code to recruiters so they can have a feel of the person's coding style.
This can also help developers looking to set themselves up as freelance developers. Their potential clients can visit this page and have a feel of the styles and functionalities that the person can build for them.

This [article](https://www.codementor.io/learn-programming/12-important-things-to-include-in-web-dev-portfolios#:~:text=At%20the%20end%20of%20the,with%20bullet%20points%20would%20allow.) provides good tips on what's important to include in a web developer's portfolio.
There are also many websites with examples of portfolios, the two suggestions below are only provided as a starting point:

- [Code camp website](https://www.freecodecamp.org/news/15-web-developer-portfolios-to-inspire-you-137fb1743cae/)
- [Alvarotrigo website](https://alvarotrigo.com/blog/web-developer-portfolio-examples/)

## Development steps

The general steps that I followed to develop this templates are listed below in order:

- Developing the wireframe design for mobile display and desktop display
- Building the skeleton html structure and using the css flexbox properties to help set the correct positioning of each div
- Using the css media query property to ensure that the page is responsive depending on the size of the screen
- Using the github api to retrieve an updated list of my public repos and create the corresponding cards

This is a screenshot of the deployed portfolio :

Desktop view:

![deployed portfolio](/assets/images/desktop-portfolio-complete-view.png)

## Technologies

Some of the key technologies used here are:

- HTML: semantic elements, links, google fonts, fontawesome
- CSS: flexbox, media query, pseudo classes, root variables
- GIT: Github repo, deployed github pages
- API: GitHub api

## Wireframe design

See below the wireframes designed for this portfolio:

<details>
<summary>Screenshot of wireframe for mobile version</summary>

![screenshot of mobile wireframe](/assets/images/wireframe-mobile.png)

</details>

<details>
<summary>Screenshot of wireframe for desktop version</summary>

![screenshot of desktop wireframe](/assets/images/wireframe-desktop.png)

</details>

## CSS for page structure

With the html skeleton built to reflect the wireframe, the positioning of sections on the page and their responsiveness depends on the use flexbox container and properties, which I approached in the following way:

- I identified the main three behaviours of my containers:
  - my container needs to have its elements in a row and this is true for both mobile and desktop layouts
  - my container needs to have its elements in a column and this is true for both mobile and desktop layouts
  - my container needs to display elements as a row in the desktop version and as a column in the mobile version
- I also identified secondary display properties for the first two types of behaviours:
  - my container's content needs to centered along the main axis
  - my container's content needs to be centered along the cross axis

To cater for these needs, I created the following classes:

![flex container classes](/assets/images/screenshot-flexclasses.png)

These classes were then assigned to each container (alongside additional unique classes used for specific styling) so that the container can behave in the required way.

See below 3 examples of assignment of these classes:

<details>
<summary>Navlink container</summary>
This navlink container has an assigned class of "always-row" in the screenshot below. It ensures that the container always displays its content, the three navlinks, in a row, whether on a mobile or on a desktop.

![navlink container with flex class assigned](/assets/images/screenshot-flexclassassigned1.png)

</details>

<details>
<summary>Intro-skills container</summary>
Another example here show the skills list container has been assigned two flex classes to make sure its content is always in a column and is always vertically centered inside the skills list container (the white card):

![intro-skills container with flex class assigned](/assets/images/screenshot-flexclassassigned2.png)

</details>

<details>
<summary>Contact container</summary>
Our last example shows how the contact container is assigned the class "stackable", and as a result has its display changed depending on screen size:

![contact container with flex class assigned](/assets/images/screenshot-flexclassassigned3.png)

</details>

## CSS for Page responsiveness

In order for the flex containers to be responsive to a certain size of screen, a media query is used and certain items are redefined such as :

- the responsive class "stackable" goes from row on desktop to column on mobile, and the corresponding containers adjust their content display (possibly requiring a margin adjustment)
- the size of the card for the showcased project is reduced and responsive to the screen's size
- the size of the other project cards are reduced and adjusted to the screen size

For this portfolio, the two following media queries have been set:

- media query for phone screen under a width of 596px
- media query for phone screen under a width of 300px

## CSS for improved interaction

### Functional links

Another aspect to take into consideration when looking at accessibility and responsiveness is the availability of functioning links.

This portfolio presents several types of links:

- redirection links to a section of the page: these are the nav links in the header navbar, and are set by using an `href` referencing the id of the item to be redirected to. In this page, the relevant `id` have been placed on section titles. See below the code for the menu "Contact" as an example:

```html
<div class="navlinks-item">
  <a class="navlink-text" href="#contact">Contact</a>
</div>
```

- external links to deployed pages or github repositories. See below the code for a project card as an example:

```html
<div class="project-card" id="semantic" data-tag="html">
  <div class="project-card-img">
    <a
      href="https://am0031.github.io/HTML-Semantics-Refactoring/"
      target="_blank"
      ><img
        class="image"
        src="./assets/images/semantics.png"
        alt="semantics project card picture"
    /></a>
  </div>
  <div class="always-column centered-on-main project-card-text">
    <h4>Refactor for HTML semantics</h4>
    <div class="project-repo-link">
      <a
        class="link-text"
        href="https://github.com/Am0031/HTML-Semantics-Refactoring"
        target="_blank"
        ><i class="fa-brands fa-github"></i> Go to Github repository</a
      >
    </div>
  </div>
</div>
```

- external links to other personal pages (LinkedIn, google drive). See below the code for one of the Contact links as an example:

```html
<div class="contact-link-item">
  <a
    class="contact-link-text"
    href="https://www.linkedin.com/in/amelie-pira-b4079855/"
    target="_blank"
    ><i class="fa-brands fa-linkedin"></i> LinkedIn
  </a>
</div>
```

Alongside these links, the following two features have been added to the links:

- a link to the relevant font awesome icon for an improved visual aesthetic. See in code snippet above and their display in the desktop view below :

![font awesome icons](/assets/images/screenshot-fontawesome.png)

- the use of the `target` attribute to make sure that the links open in a new tab when clicked on. Seein code snippet above.

### Interactive look on card and links

For a better user experience, all the links and the project cards have been styled by using pseudo classes: their appearance changes on hover and attracts the eye of the user.

See the difference in the look of a project card with and without hover:

![project car with and without hover](/assets/images/screenshot-cardhover.png)

See the difference in the look of a project card with and without hover:

![project link with and without hover](/assets/images/screenshot-linkhover.png)

Navlinks and Contact links are also styled, and with a relevant colours depending on their container's background colour.

![navlink with and without hover](/assets/images/screenshot-navhover.png)

![contact link with and without hover](/assets/images/screenshot-contacthover.png)

## Upcoming features

Additional features that will be developed for the next update (with the use of javascript) are:

- A Language choice menu (for the 3 languages I can work in)
- A Filter option to filter the projects based on themes/groups which are still to be determined (use of data-tags)

Note: For this version of the portfolio, these buttons are present only for display purposes, but are not functional and do not have the right format.
