# Bazel `rules_python` issue with `pip_install`

This repository contains code to reporoduce issue of using `pytest-pylint` with Bazel rules

To reproduce the issue run:

```
bazel test :test
```

Output contains error:

<details>
<summary>Error</summary>
```
Error in fail: whl_library rules_python~0.20.0~pip~my_deps_lazy_object_proxy failed: Collecting lazy-object-proxy==1.9.0
  Using cached lazy-object-proxy-1.9.0.tar.gz (42 kB)
  Installing build dependencies: started
  Installing build dependencies: finished with status 'done'
  Getting requirements to build wheel: started
  Getting requirements to build wheel: finished with status 'done'
  Installing backend dependencies: started
  Installing backend dependencies: finished with status 'done'
  Preparing metadata (pyproject.toml): started
  Preparing metadata (pyproject.toml): finished with status 'done'
Discarding https://files.pythonhosted.org/packages/20/c0/8bab72a73607d186edad50d0168ca85bd2743cfc55560c9d721a94654b20/lazy-object-proxy-1.9.0.tar.gz (from https://pypi.org/simple/lazy-object-proxy/) (requires-python:>=3.7): Requested lazy-object-proxy==1.9.0 from https://files.pythonhosted.org/packages/20/c0/8bab72a73607d186edad50d0168ca85bd2743cfc55560c9d721a94654b20/lazy-object-proxy-1.9.0.tar.gz (from -r /var/folders/7g/r10t4ppn24l35xns5022ls10xz0438/T/tmpggvidjdy (line 1)) has inconsistent version: expected '1.9.0', but metadata has '0.0.0'
 (  WARNING: Requested lazy-object-proxy==1.9.0 from https://files.pythonhosted.org/packages/20/c0/8bab72a73607d186edad50d0168ca85bd2743cfc55560c9d721a94654b20/lazy-object-proxy-1.9.0.tar.gz (from -r /var/folders/7g/r10t4ppn24l35xns5022ls10xz0438/T/tmpggvidjdy (line 1)), but installing version 0.0.0
ERROR: Could not find a version that satisfies the requirement lazy-object-proxy==1.9.0 (from versions: 0.1.0, 1.0.0, 1.0.1, 1.0.2, 1.1.0, 1.2.0, 1.2.1, 1.2.2, 1.3.0, 1.3.1, 1.4.0, 1.4.1, 1.4.2, 1.4.3, 1.5.0, 1.5.1, 1.5.2, 1.6.0, 1.7.0, 1.7.1, 1.8.0, 1.9.0)
ERROR: No matching distribution found for lazy-object-proxy==1.9.0
```
</details>
