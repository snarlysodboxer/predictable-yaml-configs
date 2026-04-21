# predictable-yaml-configs

Default config files for [predictable-yaml](https://github.com/snarlysodboxer/predictable-yaml).

Each YAML file defines the expected key ordering for a Kubernetes (or other) object kind. These configs are used by `predictable-yaml` to lint and fix key order in YAML files.

## Usage

Point `predictable-yaml` at this repo by creating a `.predictable-yaml/.remote` file in your project:

```yaml
version: v1.0.0
```

Or to pin a specific commit:

```yaml
version: abc123def456
```

See the [predictable-yaml README](https://github.com/snarlysodboxer/predictable-yaml#remote-configs) for full details.

## Contributing

Add or update a config file for the relevant object kind. Each file should:

* Be named `{Kind}.yaml` (e.g., `Deployment.yaml`)
* Use `# predictable-yaml: kind={Kind}` or a `kind: {Kind}` field to declare the schema
* Use `# first`, `# required`, `# preferred`, and `# ditto=` comments to configure key behavior

PRs to add configs for new kinds are very welcome!

See existing files for examples, and the [predictable-yaml](https://github.com/snarlysodboxer/predictable-yaml) repo for documentation.

## Versioning

This repo uses git tags for versioning. Users pin a specific version in their `.predictable-yaml/.remote` file, so config changes only affect users when they explicitly bump their version.
