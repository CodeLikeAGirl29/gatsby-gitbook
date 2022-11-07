# Gatsby with Hasura and Gatsby Cloud

Kick off your project with this starter to create a powerful/flexible docs/tutorial web apps.

![hasura](https://camo.githubusercontent.com/f0962e80927e9ab6d06f29fd45002d361374201ca98cf3898f3b8a926c35b79b/68747470733a2f2f696d672e736869656c64732e696f2f7374617469632f76313f7374796c653d666f722d7468652d6261646765266d6573736167653d48617375726126636f6c6f723d323232323232266c6f676f3d486173757261266c6f676f436f6c6f723d314542344434266c6162656c3d)

![gatsby](https://camo.githubusercontent.com/93727ff4cdd1483a8ec97f821094d4a5d4d2eb038841e5702aeb84da8a24b4bb/68747470733a2f2f696d672e736869656c64732e696f2f7374617469632f76313f7374796c653d666f722d7468652d6261646765266d6573736167653d47617473627926636f6c6f723d363633333939266c6f676f3d476174736279266c6f676f436f6c6f723d464646464646266c6162656c3d)

![react](https://camo.githubusercontent.com/67a01fa7cf337616274f39c070a11638f2e65720e414ef55b8dd3f9c2a803b2a/68747470733a2f2f696d672e736869656c64732e696f2f7374617469632f76313f7374796c653d666f722d7468652d6261646765266d6573736167653d526561637426636f6c6f723d323232323232266c6f676f3d5265616374266c6f676f436f6c6f723d363144414642266c6162656c3d)

![graphql](https://camo.githubusercontent.com/2e1f2dc091af830685d2057c2d4c797b639c7d1601a8d6019629272c210b707b/68747470733a2f2f696d672e736869656c64732e696f2f7374617469632f76313f7374796c653d666f722d7468652d6261646765266d6573736167653d4772617068514c26636f6c6f723d453130303938266c6f676f3d4772617068514c266c6f676f436f6c6f723d464646464646266c6162656c3d)

![gatsby-gitbook-starter](https://graphql-engine-cdn.hasura.io/learn-hasura/gatsby-gitbook-starter/assets/documentation_app_blog.png)

## Motivation

We wanted to create a [GraphQL tutorial](https://learn.hasura.io) series. The content would be written by developers for various languages/frameworks and what better than writing it in Markdown! And since this is a tutorial series we also needed rich embeds, syntax highlighting and more customisations.

We also wanted to serve these tutorials in sub paths of [learn.hasura.io](https://learn.hasura.io). To serve all these requirements, we decided to use Gatsby + MDX (Markdown + JSX) to extend markdown and used a neat consistent theme like the one at [GitBook](https://www.gitbook.com) and deployed as docker containers.

## 🔥 Features
- Write using Markdown / [MDX](https://github.com/mdx-js/mdx)
- GitBook style theme
- Syntax Highlighting using Prism [`Bonus`: Code diff highlighting]
- Search Integration with Algolia
- Progressive Web App, Works Offline
- Google Analytics Integration
- Automatically generated sidebar navigation, table of contents, previous/next
- Dark Mode toggle
- Edit on Github
- Fully customisable
- Rich embeds and live code editor using MDX
- Easy deployment: Deploy on Netlify / Now.sh / Docker

## 🔗 Live Demo

Here's a [live demo](https://gatsbygitbook39319.gatsbyjs.io/)

## 🚀 Quickstart

Get started by running the following commands:

```
$ git clone https://github.com/CodeLikeAGirl29/gatsby-gitbook.git
$ cd gatsby-gitbook
$ npm install
$ npm start
```

Visit `http://localhost:8000/` to view the app.

## 🔧 Configure

Write markdown files in `content` folder.

Open `config.js` for templating variables. Broadly configuration is available for `gatsby`, `header`, `sidebar` and `siteMetadata`.

- `gatsby` config for global configuration like 
    - `pathPrefix` - Gatsby Path Prefix
    - `siteUrl` - Gatsby Site URL
    - `gaTrackingId` - Google Analytics Tracking ID

- `header` config for site header configuration like
    - `title` - The title that appears on the top left
    - `githubUrl` - The Github URL for the docs website
    - `helpUrl` - Help URL for pointing to resources
    - `tweetText` - Tweet text
    - `links` - Links on the top right
    - `search` - Enable search and [configure Algolia](https://www.gatsbyjs.org/docs/adding-search-with-algolia/)

- `sidebar` config for navigation links configuration
    - `forcedNavOrder` for left sidebar navigation order. It should be in the format "/\<filename>"
    - `frontLine` - whether to show a front line at the beginning of a nested menu.(Collapsing capability would be turned of if this option is set to true)
    - `links` - Links on the bottom left of the sidebar
    - `ignoreIndex` - Set this to true if the index.md file shouldn't appear on the left sidebar navigation. Typically this can be used for landing pages.

- `siteMetadata` config for website related configuration
    - `title` - Title of the website
    - `description` - Description of the website
    - `ogImage` - Social Media share og:image tag
    - `docsLocation` - The Github URL for Edit on Github

- For sub nesting in left sidebar, create a folder with the same name as the top level `.md` filename and the sub navigation is auto-generated. The sub navigation is alphabetically ordered.

### Algolia Configuration

To setup Algolia, go to `config.js` and update the `search` object to look like the one below:

```...,
	"search": {
		"enabled": true,
		"indexName": "MY_INDEX_NAME",
		"algoliaAppId": process.env.GATSBY_ALGOLIA_APP_ID,
		"algoliaSearchKey": process.env.GATSBY_ALGOLIA_SEARCH_KEY,
		"algoliaAdminKey": process.env.ALGOLIA_ADMIN_KEY
	},
```

Values for Algolia App ID, Search Key, and Admin Key can be obtained from Algolia Dashboard with the right set of permissions. Replace `MY_INDEX_NAME` with the Algolia Index name of your choice. To build the Algolia index, you need to run `npm run build` which will do a gatsby build along with content indexing in Algolia.

### Progressive Web App, Offline

To enable PWA, go to `config.js` and update the `pwa` object to look like the one below:

```
   "pwa": {
        "enabled": false, // disabling this will also remove the existing service worker.
        "manifest": {
            "name": "Gatsby Gitbook Starter",
            "short_name": "GitbookStarter",
            "start_url": "/",
            "background_color": "#6b37bf",
            "theme_color": "#6b37bf",
            "display": "standalone",
            "crossOrigin": "use-credentials",
            icons: [
                {
                    src: "src/pwa-512.png",
                    sizes: `512x512`,
                    type: `image/png`,
                },
            ],
        },
    }
```

## Live Code Editor

To render react components for live editing, add the `react-live=true` to the code section. For example:

```javascript react-live=true
<button>Edit my text</button>
```

In the above code, just add `javascript react-live=true` after the triple quote ``` to start rendering react components that can be edited by users.

## 🤖 SEO friendly

This is a static site and comes with all the SEO benefits. Configure meta tags like title and description for each markdown file using MDX Frontmatter

```markdown
---
title: "Title of the page"
metaTitle: "Meta Title Tag for this page"
metaDescription: "Meta Description Tag for this page"
---
```

Canonical URLs are generated automatically.

## ☁️ Deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/hasura/gatsby-gitbook-starter)

