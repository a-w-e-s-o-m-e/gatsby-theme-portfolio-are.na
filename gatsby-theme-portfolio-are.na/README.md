# gatsby-theme-portfolio-are.na

![](https://img.shields.io/npm/l/gatsby-theme-portfolio-are.na)
![](https://img.shields.io/npm/v/gatsby-theme-portfolio-are.na)

A Gatsby theme for creating a portfolio with [are.na](https://are.na/).

**[View Live Demo](https://gatsby-theme-portfolio-arena.netlify.com/)**

## Features

- [are.na](https://are.na/) for hosting of projects. This is handled by [gatsby-source-are.na](https://github.com/jordanoverbye/gatsby-source-are.na)
- [Theme UI](https://theme-ui.com) for styling
- [MDX](https://mdxjs.com/) for non-project pages (`/about`, `/contact`) etc
- [Gatsby Image](https://www.gatsbyjs.org/packages/gatsby-image/) for optimised images
- [React Spring](https://github.com/react-spring/react-spring) for simple page transitions

## Getting started

### 1. Generate a personal access token

You will first need to generate an access token from [dev.are.na](https://dev.are.na/).

### 2. Make your are.na channel

You will need to create a **single** are.na channel which contains all projects as "inner" channels. You will then pass the slug of this single are.na channel to plugin config (details in the next step).

Example

```
my-awesome-arena-channel
  inner-channel-1
    image-1
    image-2
    ...
  inner-channel-2
    image-3
    image-4
    ...
```

3. Install `gatsby-theme-portfolio-are.na` as a dependency to your project.

```
yarn add gatsby-theme-portfolio-are.na
```

or 

```
npm install --save gatsby-theme-portfolio-are.na
```

### 4. Edit your `gatsby-config.js`

Add `gatsby-theme-portfolio-are.na` to your `plugins` in `gatsby-config.js` and update your `siteMetaData`.

```
module.exports = {
  siteMetadata: {
    indexTitle: "A Gatsby theme for creating a portfolio with are.na",
    indexDescription: "Gatsby + Are.na + Theme UI + MDX",
    social: [
      {
        name: "Github",
        url: "https://github.com",
      },
    ],
    navItems: [
      {
        name: "Contact",
        slug: "/contact",
      },
    ],
  },
  plugins: [
    {
      resolve: "gatsby-theme-portfolio-are.na",
      options: {
        accessToken: YOUR_PERSONAL_ACCESS_TOKEN,
        channelSlug: SLUG_OF_ARENA_CHANNEL,
      },
    },
  ],
}
```

> Note: You will need to substitute out `YOUR_PERSONAL_ACCESS_TOKEN` and `SLUG_OF_ARENA_CHANNEL`.

### 5. Adding non-project pages (`/about`, `/contact` etc)

Simply create a `.mdx` file in the your `/src/pages/` directory. For example `/src/pages/contact.mdx` will create the `/contact` page. 

If you would like specific pages to show in the navigation, you can edit `navItems` in the `gatsby-config.js` (see previous step). 

```
// /src/pages/contact.mdx

---
title: Contact
description: How to contact me
---

<div>

# Hello World

</div>

```

## Customising through Component Shadowing

You can override components from this theme using [Component Shadowing](https://www.gatsbyjs.org/blog/2019-04-29-component-shadowing/)


### Shadow Components

All of the files below are available for customising through shadow components.

#### `AnimatedContent.js`

#### `Button.js`

#### `Footer.js`

#### `Header.js`

#### `Layout.js`

#### `PageTitle.js`

#### `ProjectsGrid.js`

#### `ProjectsGridItem.js`

#### `SEO.js`

### Theme UI

Because this theme uses [Theme UI](https://theme-ui.com), you can customise colours, spacing, fonts, color modes, MDX styles and more by shadowing `gatsby-plugin-theme-ui`.
