# fixinator-github-action

Github Action to run a [Fixinator Security Scan](https://fixinator.app) on your ColdFusion / CFML source code (cfm, cfc files).

## Example Usage

Add the following to your Github Actions Workflow yaml file:

```
jobs:
  fixinator:
    runs-on: ubuntu-latest
    steps: 
    - uses: actions/checkout@v2
    - name: Fixinator Security Scan 
      uses: foundeo/fixinator-github-action@master
      with:
        fixinator_api_key: ${{ secrets.FIXINATOR_API_KEY }}
```

Note you will need to setup a _Secret_ containing your Fixinator API key in Github settings for your project.

## Inputs

The following inputs can be specified in the `with` node:

### `fixinator_api_key`

This should be a valid fixinator_api_key. To obtain a trail key, visit: <https://fixinator.app/try/>

### `path`

By default scans the entire repository. You can specify a folder path, a file path or a file globber pattern.

### `confidence`

Filter the results by the confidence level. By default it runs in `high` confidence mode, so only reports on issues it is highly confident are a security concern. You can set it to `low` or `medium` to see more results.

### `severity`

The minimum severity level to show in the results. By default it is set to `low` but if you only want to see `high` severity issues, then set it to `high`.

### `ignorePaths`

A file globber pattern of paths to ignore from the scan.

### `failOnIssues`

By default the action will fail if it finds any issues. You can set it to `false` to prevent it from failing when it finds issues.

