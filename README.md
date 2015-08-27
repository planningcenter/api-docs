# PCO API Docs

Source for [PCO API docs](http://planningcenter.github.io/api-docs/) in the branch `gh-pages`.

## How to Build

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git
bundle install
DEPLOY_ENV=development rake
```

## Publishing Docs

```
cd ~/Code
git clone git@github.com:planningcenter/api-docs.git api-docs-gh-pages
git checkout gh-pages
./update
git add .
git commit -m "commit message"
git push
```
