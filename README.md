# Introduction

This action wraps the [dep-scan](https://github.com/AppThreat/dep-scan/), a fully open-source security audit tool for project dependencies based on known vulnerabilities and advisories. The output is fully compatible with [grafeas](https://github.com/grafeas/grafeas).

## Usage

With minimal configuration

```yaml
- uses: AppThreat/dep-scan-action@master
```

Upload reports to build artifacts

```yaml
- uses: AppThreat/dep-scan-action@master

- uses: actions/upload-artifact@v1
  with:
    name: reports
    path: reports
```
