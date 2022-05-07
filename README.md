# SpinalHDL-Action

[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

## Changelog

* v1 support `SpinalHDL < 1.7.0`, and unsupport `Formal Verification` feature.

* v2 support `SpinalHDL >= 1.7.0`, and support `Formal Verification` feature now.

## Quick Usage

1. Create `.github/workflows/main.yml`
2. Paste it in `main.yml`

```yaml
name: ci

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: kazutoiris/spinalhdl-action@v2
        with:
          TopLevel: mylib.MyTopLevelVerilog
          TopLevelSim: mylib.MyTopLevelSim

      - uses: actions/upload-artifact@v3
        with:
          name: verilog
          path: "*.v"
        continue-on-error: true
```

3. Change `TopLevel` and `TopLevelSim` to your project.

## More Information

1. It will create `verilog.zip` and `all.zip` under the current directory, which contain only verilog code and whole folder. You can upload them to WeTransfer or Release. Upload to artifact maybe not enough space.
2. Refer to [kazutoiris/SpinalTemplateSbt](https://github.com/kazutoiris/SpinalTemplateSbt) for more examples.
