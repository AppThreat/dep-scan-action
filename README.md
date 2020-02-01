# Introduction

This action wraps [dep-scan](https://github.com/AppThreat/dep-scan/), a fully open-source security audit tool for project dependencies based on known vulnerabilities and advisories. The output is fully compatible with [grafeas](https://github.com/grafeas/grafeas).

## Usage

With minimal configuration

```yaml
- uses: AppThreat/dep-scan-action@master
  env:
    VULNDB_HOME: ${{ github.workspace }}/db
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Upload reports to build artifacts

```yaml
- uses: AppThreat/dep-scan-action@master
  env:
    VULNDB_HOME: ${{ github.workspace }}/db
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
- uses: actions/upload-artifact@v1
  with:
    name: reports
    path: reports
```
