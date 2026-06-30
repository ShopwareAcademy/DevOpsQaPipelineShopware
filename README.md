# DevOpsQaPipelineShopware

This project is part of the **DevOps** learning path of the Shopware Academy.

It shows the prepared reference project state for the practical lab **Building a QA Pipeline With GitHub Actions**.

It demonstrates how to:

- Start from a prepared Shopware project repository.
- Add QA tooling with PHPStan and PHPUnit.
- Include the Academy example plugin `AcademyPhpUnit` as testable plugin code.
- Prepare the repository for a GitHub Actions QA pipeline.
- Keep local environment files and generated runtime files out of Git.

Tested for **Shopware 6.7**.

## Reference Project

This repository is an educational reference state for the Academy practical lab. It is meant for comparing your local result with a known project state before you add the GitHub Actions workflow.

The most important files and folders to compare are:

- `composer.json`
- `composer.lock`
- `.gitignore`
- `.env.example`
- `custom/plugins/AcademyPhpUnit/`

The GitHub Actions workflow file is intentionally not part of this initial setup state yet. In the learning unit, you create `.github/workflows/qa-pipeline.yml` step by step.

This repository is not a production template. The project structure and credentials are intentionally simple for local learning.

## Environment Files

The generated `.env` file is not committed because it contains local values such as `APP_SECRET`, `INSTANCE_ID`, and `DATABASE_URL`.

Use `.env.example` as a safe reference if you need to recreate local environment values.

## Academy Example Plugin

This reference project includes `AcademyPhpUnit` under:

```text
custom/plugins/AcademyPhpUnit
```

The plugin provides a `phpunit.xml` file and PHPUnit test code. This gives the QA workflow real plugin code to discover and execute during the unit-test job.

The standalone plugin also has its own GitHub Actions workflow. This reference project keeps the focus on the DevOps learning unit, so the workflow for this lab is created later at the project root.

## Optional: Run the Project Locally

This reference project is mainly intended for comparison. You do not need to run it locally to follow the GitHub Actions lab.

If you want to run it locally, install dependencies first:

```bash
composer install
```

Then create your own `.env` from the example file and adjust the values for your local setup:

```bash
cp .env.example .env
```

You can then use the generated Shopware Docker development commands from this project, for example:

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
