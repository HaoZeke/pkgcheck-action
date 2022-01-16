Example script:

```yaml
name: pkgcheck

concurrency:
  group: ${{ github.workflow }}-${{ github.head_ref }}
  cancel-in-progress: true

on: workflow_dispatch

runs-on: ubuntu-latest
steps:
    - uses: assignUser/pkgcheck-action@main
        with:
        cache-version: 1
```