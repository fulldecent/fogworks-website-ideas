## How to run this application locally

### Setup environment

_In production (GitHub Actions), environment is setup by by workflows in [.github/workflows/](.github/workflows/)._

_For local testing (try VS Code + Dev Containers extension, Podman Desktop), these steps are performed by [.devcontainer/](.devcontainer/) when you run Reopen in Container._

1. Install Ruby (use version in [build-test-deploy.yml](https://github.com/fulldecent/github-pages-template/blob/main/.github/workflows/build-test-deploy.yml) in "Setup Ruby", (try rbenv)

1. Install Jekyll

   ```sh
   gem update --system
   gem install bundler
   bundle install
   ```

1. Install Node & yarn, use version in build-test-publish.yml in "Setup Node.js", (try nvm)

   ```sh
   nvm use 'lts/*'
   yarn install
   ```

Note: if you want to install GitHub Copilot, use this approach <https://code.visualstudio.com/docs/remote/ssh#_always-installed-extensions> for your configuration rather than adding to the site config.

### Build the site

Build the HTML website (see available localhost:#### port in the console output):

```sh
bundle exec jekyll build
```

### Serve/run the site

```sh
bundle exec jekyll serve
```

### Testing

All testing is performed using Node scripts:

```sh
yarn run test
```
