# DevOpsQaPipelineShopware

This project is part of the **DevOps** learning path of the Shopware Academy.

It shows the finished reference project state for the practical lab **Building a Shopware QA Pipeline With GitHub Actions**.

It demonstrates how to:

- Start from a prepared Shopware project repository.
- Add QA tooling with PHPStan and PHPUnit.
- Include the Academy example plugin `AcademyPhpUnit` as testable plugin code.
- Build focused GitHub Actions workflow files for a Shopware QA pipeline.
- Keep local environment files and generated runtime files out of Git.

Tested for **Shopware 6.7**.

## Reference Project

This repository is an educational reference state for the Academy practical lab. It is meant for comparing your local result with a known finished project state after you create the GitHub Actions workflows.

The most important files and folders to compare are:

- `composer.json`
- `composer.lock`
- `.gitignore`
- `custom/plugins/AcademyPhpUnit/`
- `.github/workflows/qa-smoke-test.yml`
- `.github/workflows/phpstan.yml`
- `.github/workflows/unit-tests.yml`
- `.github/workflows/integration-tests.yml`

The learning unit creates the workflow files step by step. This repository contains the finished reference state with separate workflow files for the smoke test, PHPStan, unit tests, and the prepared integration-test layer.

This repository is not a production template. The project structure and credentials are intentionally simple for local learning.

## Environment Files

The generated `.env` file is not committed because it contains local values such as `APP_SECRET`, `INSTANCE_ID`, and `DATABASE_URL`.

## Academy Example Plugin

This reference project includes `AcademyPhpUnit` under:

```text
custom/plugins/AcademyPhpUnit
```

The plugin provides a `phpunit.xml` file and PHPUnit test code. This gives the QA workflow real plugin code to discover and execute during the unit-test job.

The plugin does not provide a `phpunit.integration.xml` file. Therefore the integration-test workflow prepares Shopware with MySQL and then prints `No plugin integration test configuration found.` This is expected for this reference project.

The standalone plugin also has its own GitHub Actions workflow. This reference project keeps the focus on the DevOps learning unit, so the QA workflows for this lab live at the Shopware project root.

## Optional: Run the Project Locally

This reference project is mainly intended for comparison. You do not need to run it locally to follow the GitHub Actions lab.

If you want to run it locally, install dependencies first:

```bash
composer install
```

You need to create your own local `.env` before running the project. You can then use the generated Shopware Docker development commands from this project, for example:

```bash
make up
make setup
```

The exact local runtime depends on your Docker setup and the generated Shopware development configuration.

## License

MIT License.

You may use this project in commercial and professional projects. It is provided as an educational example and comes without a warranty and without support.

## Contributing

This project is part of the Shopware Academy curriculum.
