# Drupal CMS Codespaces sandbox

This repository is a GitHub Codespaces sandbox for [Drupal CMS 1.0](https://www.drupal.org/blog/drupal-cms-1-0).

When running in GitHub Codespaces, you can open this project in the Codespaces environment and automatically get a functional Drupal setup without having to install local dependencies or manage separate environments. 🚀

This setup is intended for quick exploration and is not optimized for rigorous security or performance scenarios.

## 🚀 Getting started with GitHub Codespaces

To run this repository on GitHub Codespaces, simply select this repository and create a new Codespace.

Once the environment is ready, you will have a complete Drupal environment running in your browser. You can then open and edit files directly in the browser or connect via VSCode if you prefer.

### Database Connection Information

Please specify the following connection parameters in the Drupal installation wizard.

| Parameter         | Default value  |
|-------------------|----------------|
| Database name     | drupal         |
| Database username | drupal         |
| Database password | drupal         |
| Host              | db             |

These values can be found in [compose.yml](compose.yml). You can override them using a local .env file or [GitHub Codespaces secrets](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-your-account-specific-secrets-for-github-codespaces).

## 💻 Getting started with Devcontainer

If you wish to run this repository via [Devcontainer](https://code.visualstudio.com/docs/devcontainers/containers), make sure your host operating system has both VSCode and Docker Desktop installed.

Then open VSCode, install the Remote-Containers extension, and choose Dev Containers: Rebuild and Reopen in Container” from the Command Palette.

This approach ensures a consistent setup across different machines.

## Note

Please note that this repository is purely for sandbox purposes, and as such, its security and performance have not been thoroughly tested or optimized.

## License

[MIT](LICENSE)
