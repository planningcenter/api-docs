
> For help using the Planning Center API, please open an issue in our developer support repo at
> https://github.com/planningcenter/developers

### Planning Center API Documentation

Source for [Planning Center API docs](http://planningcenter.github.io/api-docs/) in the branch `gh-pages`.

#### How to Build (Do this before publishing)

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git
cd api-docs
bundle install
DEPLOY_ENV=production rake
git add .
git commit -m "Updated Docs"
git push
```

#### Publishing Docs (Do this after building and pushing)

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git api-docs-gh-pages
cd api-docs-gh-pages
git checkout gh-pages
./update
git add .
git commit -m "Updated Docs"
git push
```

#### Adding an App

- Add the app's subdomain to the Rakefile. This will cause `rake` to pull docs from that app.
- Add the app's `include` file to `index.md`'s YAML frontmatter. This will cause the docs to be rendered on the page.
- Add a corresponding OAuth scope to `api.planningcenteronline.com` and add an entry to the "Scopes" table in `index.md`
- Run "Publishing Docs" above.
