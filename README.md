# Introduction

This action wraps [OWASP-dep-scan](https://github.com/OWASP-dep-scan/dep-scan/), 
a fully open-source security audit tool for project dependencies based on known 
vulnerabilities and advisories. The output is fully compatible with 
[grafeas](https://github.com/grafeas/grafeas).

Please consider [making a monetary contribution](https://owasp.org/donate/?reponame=www-project-dep-scan&title=OWASP+depscan) to OWASP-dep-scan. We appreciate 
your support!

## Usage

### Inputs

With minimal configuration

```yaml
- uses: AppThreat/dep-scan-action@master
  with:
    # The target directory to be scanned. Optional.
    src: /github/workspace
    # Output file for the generated report. Optional.
    report_file: /github/workspace/reports/depscan.json
    # Must equal "I have sponsored OWASP-dep-scan" for action to run. Required.
    profile: generic
    thank_you: "I have not sponsored OWASP-dep-scan."
  env:
    VDB_HOME: ${{ github.workspace }}/db
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Upload reports to build artifacts

```yaml
- uses: AppThreat/dep-scan-action@master
  with:
      thank_you: "I have sponsored OWASP-dep-scan."
  env:
    VDB_HOME: ${{ github.workspace }}/db
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
- uses: actions/upload-artifact@v4
  with:
    name: reports
    path: reports
```

