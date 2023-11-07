# odo-backstage-golden-path-template

This is a Software Template for Backstage that allows users to pick a Devfile Stack from a configured Devfile Registry.
It then generates and publishes a starter project to a GitHub repository, and finally registers the new entity into the Backstage catalog.

It does so by leveraging both the `DevfileSelectorExtension` Custom Field extension and the `devfile:odo:*` Custom Actions available in https://github.com/rm3l/backstage-odo-devfile-plugin

## Demo

[Demo: odo Backstage Golden Path Template](https://github.com/rm3l/odo-backstage-golden-path-template/assets/593208/0e081e36-591c-4861-adfc-b567647ac04f)

## Usage

1. Follow the instructions to setup and register the `devfile-field-extension` Custom Field extension into your Backstage instance: https://github.com/rm3l/backstage-odo-devfile-plugin/blob/main/packages/devfile-field-extension/README.md
2. Follow the instructions to setup and register the `scaffolder-odo-actions` Custom Actions into your Backstage instance: https://github.com/rm3l/backstage-odo-devfile-plugin/blob/main/packages/scaffolder-odo-actions-backend/README.md
3. Register this Template into the `app-config.yaml` of your Backstage instance, and optionaly configure the `odo` plugin:

```yaml
# app-config.yaml

catalog:
  locations:
    # [...]
    - type: url
      target: https://github.com/rm3l/odo-backstage-golden-path-template/blob/main/template.yaml
      rules:
        - allow: [Template]

# Optional configuration for the odo plugin
odo:
  telemetry:
    # Disable the odo telemetry. False by default.
    disabled: false
```

4. Restart your Backstage instance, and you should see a new `Bootstrap application with Devfile` Template available if you click on the `Create` button.
