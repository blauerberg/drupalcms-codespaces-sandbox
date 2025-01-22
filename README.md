# Drupal CMS Codespaces sandbox

This repository is a GitHub Codespaces sandbox for [Drupal CMS 1.0](https://www.drupal.org/blog/drupal-cms-1-0).

When you run this repository in GitHub Codespaces, it automatically sets up a fully functional Drupal environment, so you don’t need to install local dependencies or manage separate environments. 🚀

This setup is designed for quick exploration and isn’t optimized for high-level security or performance scenarios.

## 🚀 Getting started with GitHub Codespaces

To run this repository on GitHub Codespaces, simply select this repository and create a new Codespace.

Once your Codespace is ready, you have a complete Drupal environment running in your browser. You can open and edit files directly or connect via VSCode if you prefer.

![demo](https://github.com/blauerberg/drupalcms-codespaces-sandbox/blob/main/assets/demo.gif?raw=true)

### Database Connection Information

Use the following connection parameters in the Drupal installation wizard.

| Parameter         | Default value  |
|-------------------|----------------|
| Database name     | drupal         |
| Database username | drupal         |
| Database password | drupal         |
| Host              | db             |

These values can be found in [compose.yml](compose.yml). You can override them using a local .env file or [GitHub Codespaces secrets](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-your-account-specific-secrets-for-github-codespaces).

## 💻 Getting started with Devcontainer

If you want to use this repository via [Devcontainer](https://code.visualstudio.com/docs/devcontainers/containers), make sure VSCode and Docker Desktop are installed.

Then open VSCode, install the Remote-Containers extension, and choose “Dev Containers: Rebuild and Reopen in Container” from the Command Palette.

This approach ensures a consistent setup across different machines.

## Note

Please note that this repository is purely for sandbox purposes, and as such, its security and performance have not been thoroughly tested or optimized.

## License

[MIT](LICENSE)
