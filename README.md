# PCO API Docs

Source for [PCO API docs](http://planningcenter.github.io/api-docs/) in the branch `gh-pages`.

## How to Build

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git
cd api-docs
bundle install
DEPLOY_ENV=development rake
```

## Publishing Docs

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git api-docs-gh-pages
cd api-docs-gh-pages
git checkout gh-pages
./update
git add .
git commit -m "commit message"
git push
```

## Adding an App

- Add the app's subdomain to the Rakefile. This will cause `rake` to pull docs from that app.
- Add the app's `include` file to `index.html`'s YAML frontmatter. This will cause the docs to be rendered on the page.
- Run "Publishing Docs" above
