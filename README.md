# personal_website_example
An example of an sphinx based personal website

The website is build iteratively, adding more elements every time, so the commit history is
both a guide and a log.

## Notes

### Base website
Commit [eabb1ca](https://github.com/OriolAbril/personal_website_example/commit/eabb1cad59f7cef0eac507acb576b610caa1ef24)
sets up the initial website, with a landing and an about page. It also add the basic sphinx
configuration and the GH action to publish the website. For the github action to work,
settings in "Build and Deployment" section of
https://github.com/OriolAbril/personal_website_example/settings/pages have to be updated.

### Custom domain
Commit [8c1f0c7](https://github.com/OriolAbril/personal_website_example/commit/8c1f0c7479591e4ecfb472b2fa9a8da0431727cc)
adds the not found page, and after that we will assume the website is being served on a custom
domain (i.e. not on `.github.io` one). For that to work the custom domain (without `https://`)
has to be added to the "Custom Domain" section of https://github.com/OriolAbril/personal_website_example/settings/pages.
This change is not dependent of this specific commit, but from here on, it is assumed it will happen.

### Internationalization
When setting translations up, the first step is updating `conf.py` and installing the new
requirements (that is `sphinx-intl`). Then run the two following commands:

```bash
sphinx-build . gettext -b gettext
sphinx-intl update -p gettext -l ca
```

Replacing `ca` with your target language abbreviation if necessary. Note that if you want
to target multiple languages, you can repeat the `-l` flat, for example `... -l ca -l es`
would generate the translatable sources for both Catalan and Spanish.

These two commands need to be executed every time you update your website.
