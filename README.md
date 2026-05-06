# Citum External Registry Prototype

This is a minimal prototype of an external Citum style registry. It demonstrates how institutional publishers or tool integrators can host their own styles independently of the Citum core registry.

## Registry Index

The index file `citum-registry.yaml` contains the mapping of style IDs to their local paths (or remote URLs).

## Styles

- `university-thesis`: A base institutional style for theses and dissertations, extending Chicago 18th Notes.
- `university-journal`: A journal-specific style that extends the `university-thesis` style.

## Usage

To use this registry locally, you can add it to your Citum configuration:

```yaml
registries:
  - name: internal-prototype
    url: path/to/citum-external-registry-prototype/citum-registry.yaml
    trusted: true
    priority: 80
```

Or reference a style directly by path:

```bash
citum render -s path/to/styles/university-thesis.yaml ...
```
