# Andrew Samountry's Personal Website


<img width="1440" alt="Screenshot 2024-02-28 at 12 22 43 PM" src="https://github.com/AndSam321/andrew-samountry-personal-website/assets/89934858/2c5c4915-4dc2-4f98-8d2e-96fe8e1a0286">


# Astrofy | Personal Portfolio Website Template

![Astrofy | Personal Porfolio Website Template](public/social_img.webp)

Astrofy is a free and open-source template for your Personal Portfolio Website built with Astro and TailwindCSS. Create in minutes a website with a CV, Project Section, and RSS Feed.

## Demo

View a live demo of [Astrofy](https://astrofy-template.netlify.app/)

## Installation

Run the following command in your terminal

```bash
pnpm install
```

Once the packages are installed you are ready to run astro. Astro comes with a built-in development server that has everything you need for project development. The astro dev command will start the local development server so that you can see your new website in action for the very first time.

```bash
pnpm run dev
```

## Tech Stack

- [Astro](https://astro.build)
- [tailwindcss](https://tailwindcss.com/)
- [DaisyUI](https://daisyui.com/)

## Project Structure

```php
├── src/
│   ├── components/
│   │   ├── cv/
│   │   │   ├── TimeLine
│   │   ├── BaseHead.astro
│   │   ├── Card.astro
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   └── HorizontalCard.astro
│   │   └── SideBar.astro
│   │   └── SideBarMenu.astro
│   │   └── SideBarFooter.astro
│   ├── layouts/
│   │   └── BaseLayout.astro
│   │   └── PostLayout.astro
│   └── pages/
│   │   └── cv.astro
│   │   └── index.astro
│   │   └── projects.astro
│   │   └── rss.xml.js
│   ├── styles/
│   │   └── global.css
│   └── config.ts
├── public/
│   ├── favicon.svg
│   └── profile.webp
│   └── social_img.webp
├── astro.config.mjs
├── tailwind.config.cjs
├── package.json
└── tsconfig.json
```

### Site config

You can change global site configuration on '/src/config.ts' file:

- **SITE_TITLE**: Default pages title.
- **SITE_DESCRIPTION**: Default pages title.
- **TRANSITION_API**: Enable and disable transition API

### Components usage

#### Layout Components

The `BaseHead`, `Footer`, `Header`, and `SideBar` components are already included in the layout system. To change the website content you can edit the content of these components.

##### SideBar

In the Sidebar you can change your profilePicture, links to all your website pages, and your social icons.

You can change your avatar shape using [mask classes](https://daisyui.com/components/mask/).

The used social-icons are SVG form [BoxIcons](https://boxicons.com/) pack. You can replace the icons in the `SideBarFooter` component

To add a new page in the sidebar go to the `SideBarMenu` component.

```
<li><a class="py-3 text-base" id="home" href="/">Home</a></li>

```

**Note**: In order to change the sidebar menu's active item, you need to setup the prop `sideBarActiveItemID` in the `BaseLayout` component of your new page and add that id to the link in the `SideBarMenu`

#### TimeLine

The timeline components are used to confirm the CV.

```html
<div class="time-line-container">
  <TimeLineElement title="Element Title" subtitle="Subtitle">
    Content that can contain
    <div>divs</div>
    and <span>anything else you want</span>.
  </TimeLineElement>
  ...
</div>
```

#### Adding a Custom Component

To add a custom component, you can create a .astro file in the components folder under the source folder. 

Components must follow this template. The ```---``` represents the code fence and uses Javascript and can be used for imports. 

The HTML component is the actual style of your new component. 

```html
---
// Component Script (JavaScript)
---
<!-- Component Template (HTML + JS Expressions) -->
```

For more details, see the [astro components](https://docs.astro.build/en/core-concepts/astro-components/) documentation here. 

### Layouts

Include `BaseLayout` in each page you add and `PostLayout` to your post pages.

The BaseLayout defines a general template for each new webpage you want to add. It imports constants SITE_TITLE and SITE_DESCRIPTION which can be modified in the ```../config``` folder. Data placed there can be imported anywhere using import. 

### Content

You can add a [content collection](https://docs.astro.build/en/guides/content-collections/) in `/content/' folder, you will need add it at config.ts.

#### config.ts

Where you need to define your content collections, we define our content schemas too.

#### Static pages

The other pages included in the template are static pages. The `index` page belongs to the root page. You can add your pages directly in the `/pages` folder and then add a link to those pages in the `sidebar` component.

Feel free to modify the content included in the pages that the template contains or add the ones you need.

### Theming

To change the template theme change the `data-theme` attribute of the `<html>` tag in `BaseLayout.astro` file.

You can choose among 30 themes available or create your custom theme. See themes available [here](https://daisyui.com/docs/themes/).

## Sitemap

The Sitemap is generated automatically when you build your website in the root of the domain. Please update the `robots.txt` file in the public folder with your site name URL for the Sitemap.

## Deploy

You can deploy your site on your favourite static hosting service such as Vercel, Netlify, GitHub Pages, etc.

The configuration for the deployment varies depending on the platform where you are going to do it. See the [official Astro information](https://docs.astro.build/en/guides/deploy/) to deploy your website.

# andrew-samountry-personal-website
