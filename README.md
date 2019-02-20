<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250" align="right">

# Project Summary

In this project we will be recreating our portfolio page to use multiple pages.

This project will reuse a lot of the code you have already built but add in multiple pages and add some semantic HTML.

## Setup
Fork and clone this repository to have it under your GitHub profile and have it locally on your computer. Remember, we built our initial file structure to have some sort of organization so be sure to clone it down to the correct folder you want it to live.

## Step One
In this step we will be laying the ground work for the rest of our project. We will be restructuring a lot of the code and laying it out to be more reusable.

We first need to create two new folders, `styles` and `pages`. This can be done in VSCode or your terminal. Inside of the new `styles` folder, add four new files: `contact.css`, `projects.css`, `home.css` and `index.css`.

Instead of writing all of our CSS in one single `.css` file, we can break them out to separate files. This makes our code more maintainable as it grows.

Inside of the `pages` folder, create two new files: `contact.html` and `projects.html`. You should now have a pretty good idea of how we will be adjusting our code to be more maintainable and usable.

### Solution
<details>

  * Create `styles` folder
    * Add `contact.css`
    * Add `projets.css`
    * Add `home.css`
    * Add `index.css`
  * Create `pages` folder
    * Add `contact.html`
    * Add `projects.html`
  
</details>

## Step Two
Open the `index.html` files so we can get to cutting the code out and putting it into different files. Find the section of code for your projects. It should be something like this: 

```html
<div class="projects-container">
  <h1 class="title">Projects</h1>
  <div class="projects">
    <div class="project one"></div>
    <div class="project two"></div>
    <div class="project three"></div>
  </div>
</div>
```

We will want to change our outtermost `div` to be a `section` element. Remember, semantic elements provide meaning to our layout. In this case, `section` means a new section of content.

Create the basic structure to our `projects.html` page includeing the `html`, `head` and `body` elements and paste the projects code from `index.html` into the `body` element.

We will want to follow a similar pattern for our `contact.html` page.

### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Portfolio Site</title>
  </head>
  <body>
    <section class="hero">
      <h1 class="title">Bryan Smith</h1>
    </section>
    <section class="about">
      <h1 class="title">About</h1>
      <p>
        My name is Bryan Smith and I am an instructor at DevMountain. I have been
        developing for about 5 years now and absolutely love it. Do I have any other
        hobbies you ask? I sure do! You can see them below:
      </p>
      <ul>
        <li>Skateboarding</li>
        <li>Home Renovation</li>
        <li>Tattoos</li>
        <li>Lawn Care</li>
        <li>Hanging Out With My Family</li>
      </ul>
    </section>
  </body>
</html>
```
  
</details>
<details>
<summary><code>projects.html</code></summary>

```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <title>Projects</title>
    </head>
    <body>
      <section class="projects-container">
        <h1 class="title">Projects</h1>
        <div class="projects">
          <div class="project one"></div>
          <div class="project two"></div>
          <div class="project three"></div>
        </div>
      </section>
    </body>
  </html>
```
  
</details>

<details>
<summary><code>contact.html</code></summary>

```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <title>Contact Me</title>
    </head>
    <body>
      <section class="contact">
        <h1 class="title">Contact</h1>
        <div class="email">
          <p>Email: <a href="mailto: abc@example.com">bryan@devmtn.com</a></p>
        </div>
        <div class="phone">
          <p>Phone: <a href="tel:1-562-867-5309">1-562-867-5309</a></p>
        </div>
        <div class="github">
          <p>GitHub: <a href="github.com/bryansmith33">Check out my code!</a></p>
        </div>
      </section>
    </body>
  </html>
```
  
</details>

## Step Three
In this step we will add the styling to each of our new pages. One thing to consider though is that we have four `css` files but only have three pages. Think for a moment why we would do that?

We want to have an `index.css` file that we will include in all of our pages. The reason for this is that some styling needs to be included on all pages. 

We break our CSS out into separate files because there will be some style that is unnecessary for the page so there is no reason to load it if we don't need to.

In our `index.html` file, let's add two new `link` elements to link our styles. Create two links:

* One to link the `index.css` file
* One to link the `home.css` file

Follow this process for the `Projects` and `Contact` pages but with their correct CSS link below the `index.css` link. One thing to consider here is that our `index.html` file is not included in our `pages` folder but the `Projects` and `Contact` page are. Think about what changes you would have to make to your file path when referencing your CSS files.

### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<link rel="stylesheet" href="./styles/index.css" />
		<link rel="stylesheet" href="./styles/home.css" />
		<title>Portfolio Site</title>
	</head>
	<body>
    <!-- More HTML -->
  </body>
</html>
```
</details>

<details>
<summary><code>Projects.html</code></summary>

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<link rel="stylesheet" href="../styles/index.css" />
		<link rel="stylesheet" href="../styles/projects.css" />
		<title>Projects</title>
	</head>
	<body>
    <!-- More HTML -->
  </body>
</html>
```
</details>

<details>
<summary><code>contact.html</code></summary>

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<link rel="stylesheet" href="../styles/index.css" />
		<link rel="stylesheet" href="../styles/contact.css" />
		<title>Contact Me</title>
	</head>
	<body>
    <!-- More HTML -->
  </body>
</html>
```
</details>

## Step Four
We now want to start moving the CSS to their correct files so they aren't all inside of our sinlge `style.css` file. Looking in `style.css` file, what do you think could be included in our index.css file to applied to every page?

After a little  review, we an see that the `.title` selector is used on every page and the `.about, .contact` select is used for two pages so let's include both of those. We will also be adding a new selector to get rid of the white border around our page. That is a margin that is added to the `body` element. Add these styles to our `index.css` file inside of our `styles` folder.

<details>
<summary><code>index.css</code></summary>

```css
  body {
    margin: 0;
  }
  .title {
    margin: 0;
  }
  .about,
  .contact {
    max-width: 800px;
    margin: 15px auto;
  }
```
</details>

<br>

Let's go ahead and add styling to our `home.css` file. Looking back in the `index.css` file, what can we remove and add to `home.css`?

Looks like we can add the `.hero` and `.hero .title` selectors. Note that we will have to adjust the path to our hero image.
<details>
<summary><code>home.css</code></summary>

```css
.hero {
  height: 500px;
  background: url('../img/hawaii.jpg')
    center no-repeat;
  background-size: cover;
  clear: right;
}
.hero .title {
  text-align: center;
  font-size: 4em;
  font-family: sans-serif;
  font-weight: 100;
}
```
</details>

<br>

Next up we will look to add styling to our `projects.css` file. Follow the pattern above and see what should be added.

<details>
<summary><code>projects.css</code></summary>

```css
.projects-container {
  background: #111;
  color: #fff;
  padding: 50px 0;
  text-align: center;
}
.projects {
  margin: 0 auto;
}
.project {
  height: 300px;
  width: 300px;
  margin: 0 15px;
  display: inline-block;
}
.project.one {
  background: green;
}
.project.two {
  background: blue;
}
.project.three {
  background: aquamarine;
}
```
</details>

<br>

And finally we will do the same as above for our `contact.css` file.

<details>
<summary><code>contact.css</code></summary>

```css
.contact {
  margin: 50px auto;
  text-align: center;
}
```
</details>

## Step Five
Let's go ahead and load up our page in our browser to see hwo things are shaping up. Fantastic! We now have our site separated out into maintainable pieces. But there is just one problem...We can't navigate to any of our other pages. Let's go ahead and fix that by adding a `nav` element to each of our pages.

our `nav` element will need a class of `navbar`. While we could just target our `nav` element in our CSS, adding a class is a great way to make sure it is more specific should any pranksters come along and add a style to our `nav` element in any of our CSS files.

Inside of the `nav` let's add a `span` element with a class of `name` and an `h1` element inside of that that contains our name. The structure should look like this:

```html
<nav class="navbar">
  <span class="name">
    <h1>Bryan Smith</h1>
  </span>
</nav>
```

Next we want to actually add the ability to navigate to different pages. Thinking back to our first HTML/CSS project, what element will we use if we want to list things?

If you guessed a `ul` element, you are correct! Let's added that as a sibling of our `span` element and give it a class of `navlink`. Inside of the `ul`, we want to add three `li` elements that have a `a` element inside of them. 

Each `a` element should have three things:
  * A class of `link`
  * An `href` with the correct path to the page
  * Inner text with the name of the page you are navigating to.

The last thing we need to do is add our newly created `nav` element to each page. We need to add it to the top of each file because we want it to display at the top of our page. Think for a moment why we need to add it to every page? Because we want to be able to use our navigation on each page.

Remember, we will have to adjust the file path to our other pages in the `href` depending on which page we are currently viewing.

Before looking at the solution, push yourself to try and add these elements on your own.

### Solution
<details>
<summary><code>nav code</code></summary>

```html
<nav class="navbar">
  <span class="name">
    <h1>Bryan Smith</h1>
  </span>
  <ul class="navlinks">
    <li><a class="link" href="../index.html">Home</a></li>
    <li><a class="link" href="../pages/projects.html">Projects</a></li>
    <li><a class="link" href="../pages/contact.html">Contact</a></li>
  </ul>
</nav>
```
</details>

## Step Six

We should now have a functioning `nav` element that we can use to see our other pages. While it does function, it is ugly as sin and we should clean that up. Being that the `nav` element is included on every page, where do you think we should add the styling for it? In the `index.css` since it is on all pages.

We will want our name to be on the left side of the screen and have the links to the different pages on the right side. We want the background of our `nav` to be `#333` and the text to be `#fff`

Think how we will get our nav links over to the right side of the screen? We can float them! We will also want to remove the bullets to the left of each link and line the up side by side. Play around with the CSS and try to figure this out on your own

The last thing we will want to do is remove that awful blue color from the `a` tag and make them `#fff` all the time.

### Solution
<details>
<summary><code>index.css</code></summary>

```css
.navbar {
  padding: 0 16px;
  background: #333;
  color: #fff;
}
.navbar h1 {
  display: inline-block;
}
.navlinks {
  float: right;
  margin: 25px 0;
  padding: 0;
  list-style-type: none;
}
.navlinks li {
  display: inline;
  margin: 0 10px;
}
.link {
  color: #fff;
}
```
</details>

## Wrap Up

**Semantic HTML**: We should strive to use semantic HTML elements. These elements provide meaning to our webpage rather than just a sea of `div`'s with no meaning.

**`<a>` Element**: Stands for `anchor`. We use this element to link to different parts of our site or external sites. Must include an `href` to point where the link should take the user.

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2019. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>
