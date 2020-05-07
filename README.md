# fixinator-github-action

Github Action to run Fixinator Security Scan

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

