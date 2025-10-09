# Webapp-vue-pack

An other pack to install on top of the default Symfony skeleton. Include webpack-encore-bundle and necessary things for Vue single-file component (i.e. .vue)

It's a similar pack to symfony/webapp-pack but for persons would like to continue to use webpack and .vue files (Single-file component), instead of AssetMapper.

## Installation

After [creating Symfony Applications](https://symfony.com/doc/current/setup.html#creating-symfony-applications), in your project directory:

```
composer remove symfony/asset-mapper symfony/stimulus-bundle symfony/ux-turbo
composer require fastfony/webapp-vue-pack
npm install -D vue-loader --force

```

Then, start your project as usual (with Symfony CLI, Docker, etc.) and don't forget to enable watch mode with ```npm run watch``` for compile assets and automatically re-compile when files change.

## Keep Going!

### Optional configuration

With this command you can configure webpack for silence the recommandation about "To create a smaller (and CSP-compliant) build" and for only use Vue Single-file component (see also: [Runtime Compiler Build](https://symfony.com/doc/current/frontend/encore/vuejs.html#runtime-compiler-build)):

```
sed -i '' 's/\.enableVueLoader()/.enableVueLoader(() => {}, { runtimeCompilerBuild: false })/' webpack.config.js
```

### Informations

With webpack-encore-bundle and **without AssetMapper** you can still use [Stimulus & Symfony UX](https://symfony.com/doc/current/frontend/encore/simple-example.html#stimulus-symfony-ux) and [Turbo](https://symfony.com/doc/current/frontend/encore/simple-example.html#turbo-lightning-fast-single-page-application-experience)!
