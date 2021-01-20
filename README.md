## DEPRECATED! Please use https://github.com/theNewDynamic/hugo-module-tnd-seo

# TND SEO

## Requirements

HUGO 0.54.0 and above.

## Install

```
git submodule add https://github.com/theNewDynamic/hugo-component-tnd-seo.git components/tnd-seo/
```

WARNING: Make sure the directory for the component is in your theme directory as `tnd-seo`

Drop the following where appropriate
```
{{ if templates.Exists "partials/tnd-seo/print.html" }}
  {{ partial "tnd-seo/print.html" . }}
{{ end }}
```

The above partials, will look for content information and build an Data object to be printed in SEO tags (og, twitter card etc...).
If you need to alternate the data model, you can do so by adding ot your project a `layouts/partials/tnd-seo/extend.html` partial and add to it as explained [here](/layouts/partials/tnd-seo/extend.html).

## Options

Options live in an `seo` object in your site params.

```
params:
  seo:
    # overides .Site.Title
    site_name: MyWebsite 
    # Used for articles without images
    default_image: "/images/default.jpg"
    # if true will use the SEO data object to output an json+ld script tag.
    jsonld: true
    # if true will display a human readable overlay on everypage to monitor SEO data object (only if dev != production)
    debug: true
```

## Front Matter

The following can be overriden just for SEO within the Front Matter:

```
---
title: What a post
description: That's dull!
seo:
  image: /uploads/way-better-that-this-post-featured.png
  description: Content marketing 101
```

## TODOS

- [ ] Allow title override from Front Matter
- [ ] Isolate title tag from og, twitter tag.
