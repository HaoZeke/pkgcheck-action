Example workflow file:

```yaml
name: pkgcheck

concurrency:
  group: ${{ github.workflow }}-${{ github.head_ref }}
  cancel-in-progress: true

on: workflow_dispatch

jobs: 
  check:
    runs-on: ubuntu-latest
    container: mpadge/pkgcheck
    env:
      GITHUB_PAT: ${{ secrets.GITHUB_TOKEN }}
    steps:
      - uses: assignUser/pkgcheck-action@main
        with:
          cache-version: 1
        
```
