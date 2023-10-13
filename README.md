# odo-backstage-golden-path-template

This is a Software Template for Backstage that allows users to pick a Devfile Stack from a configured Devfile Registry.
It then generates and publishes a starter project to a GitHub repository, and finally registers the new entity into the Backstage catalog.

It does so by leveraging both the `DevfileSelectorExtension` Custom Field extension and the `devfile:odo:*` Custom Actions available in https://github.com/rm3l/backstage-odo-devfile-plugin

## Demo

[Screencast from 2023-10-13 13-59-23.webm](https://github.com/rm3l/odo-backstage-golden-path-template/assets/593208/56b22434-555c-4ede-8809-2777f98924e5)

## Usage

1. Follow the instructions to setup and register the `devfile-field-extension` Custom Field extension into your Backstage instance: https://github.com/rm3l/backstage-odo-devfile-plugin/blob/main/packages/devfile-field-extension/README.md
2. Follow the instructions to setup and register the `scaffolder-odo-actions` Custom Actions into your Backstage instance: https://github.com/rm3l/backstage-odo-devfile-plugin/blob/main/packages/scaffolder-odo-actions-backend/README.md
3. Register this Template into the `app-config.yaml` of your Backstage instance:

```yaml
# app-config.yaml

catalog:
  locations:
    # [...]
    - type: url
      target: https://github.com/rm3l/odo-backstage-golden-path-template/blob/main/template.yaml
      rules:
        - allow: [Template]
```

4. Restart your Backstage instance, and you should see a new `Boostrap application with Devfile` Template available if you click on the `Create` button.
