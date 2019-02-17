# Hugo Whisper Theme

Whisper is a minimal documentation theme for Hugo. The design and functionality is intentionally minimal. We’re aiming for a similar feel to a Github readme.

[Live Demo](https://hugo-whisper.netlify.com/) |
[Zerostatic Themes](https://www.zerostatic.io/theme/hugo-whisper/)

![Hugo Whisper Theme screenshot](https://github.com/JugglerX/hugo-whisper-theme/blob/master/images/screenshot-full.jpg)

## Theme features

# Installation

To use this theme you will need to have Hugo installed. If you don't already have Hugo installed please follow the official [installation guide](https://gohugo.io/getting-started/installing/)

### Check Hugo Version

This theme uses [Hugo Pipes](https://gohugo.io/hugo-pipes/scss-sass/) to compile SCSS and minify assets. Please make sure you have the `Hugo Extended` version installed. If you are not using the extended version this theme will not not compile.

```
hugo version
```

### Create a new Hugo site

```
hugo new site mynewsite
```

This will create a fresh Hugo site in the folder `mynewsite`.

### Install theme

Copy or git clone this theme into the sites themes folder `mynewsite/themes`

#### Install with Git

```
cd mynewsite
cd themes
git clone https://github.com/jugglerx/hugo-hero-theme.git
```

#### Install from .zip file

You can download the .zip file located here https://github.com/JugglerX/hugo-hero-theme/archive/master.zip.

Extract the downloaded .zip inside the `themes` folder. Rename the extracted folder from `hugo-hero-theme-master` -> `hugo-hero-theme`. You should end up with the following folder structure `mynewsite/themes/hugo-hero-theme`

### Add example content

The fastest way to get started is to copy the example content. Copy the entire contents of the `exampleSite` folder to the root folder of your Hugo site (the folder with the README.md).

### Update config.toml

After you copy the `config.toml` into the root folder of your Hugo site you will need to update the `baseURL`, `themesDir` and `theme` values in the `config.toml`

```
baseURL = "/"
themesDir = "themes"
theme = "hugo-hero-theme"
```

### Run Hugo

After installing the theme for the first time, generate the Hugo site.

```
hugo
```

For local development run Hugo's built-in local server.

```
hugo server
```

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.

# Configuring theme features

### Homepage meta tags

Often a homepage requires special meta tags such as a meta description or og meta data for twitter, facebook etc. You can configure these values in the `config.toml`

```
// config.toml
[params]
  google_analytics_id=""

  [params.homepage_meta_tags]
    meta_description = "a description of your website."
    meta_og_title = "My Theme"
    meta_og_type = "website"
    meta_og_url = "https://www.mywebsite.com"
    meta_og_image = "https://www.mywebsite.com/images/tn.png"
    meta_og_description = "a description of your website."
    meta_twitter_card = "summary"
    meta_twitter_site = "@mytwitterhandle"
    meta_twitter_creator = "@mytwitterhandle"
```

### Set meta tags on a per template/page basis

You can set meta tags on a per template basis using a block. For example, you might want to write a custom meta description for the `/services` page. You can insert any valid HTML meta data inside the `{{ define "meta_tags }}` block at the top of a template.

```
// layouts/services/list.html
...

{{ define "meta_tags" }}
    <meta name="description" content="We offer a variety of services in the finance industry" />
{{ end }}

{{ define main }}
...
```

# Deploying to Netlify

This theme includes a `netlify.toml` which is configured to deploy to Netlify from the `exampleSite` folder. See this discussion on how to deploy your site on Netlify from the `exampleSite` folder - https://discourse.gohugo.io/t/deploy-your-theme-to-netlify/15508

Most likely if you are deploying to Netlify, you are including the entire Hugo site, so you can delete the `netlify.toml` file.
