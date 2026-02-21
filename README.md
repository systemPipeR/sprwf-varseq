## VAR-Seq Workflow Template for systemPipeR WMS

<p align="right">
  <a href="https://systempipe.org/sprwf-varseq/systemPipeVARseq.html">
    <img src="https://img.shields.io/badge/TUTORIAL-blue?style=for-the-badge&logo=gitbook&logoColor=white" alt="Tutorial Badge">
  </a>
</p>

__Overview__

This is a versioned workflow template for conducting data analyses with the
[systemPipeR Workflow Management System](https://systempipe.org/about/project/)
(WMS). It ensures consistency through centrally maintained
[param](https://github.com/systemPipeR/sprwfcmp-param) and
[data](https://github.com/systemPipeR/sprwfcmp-data) packs, which are defined
in [`manifest.yml`](./manifest.yml) and downloaded and installed during the setup process.

Detailed information about this specific `sprwf-varseq` workflow is available 
[here](https://systempipe.org/sprwf-varseq/systemPipeVARseq.html).

> Note: The data pack includes sample data useful for testing certain workflows. Users who do not require this sample data can skip the download step under the `getData_gh` section below. 

__Documentation__

To design, set up, and run workflows using _systemPipeR_, please consult:
  + [systemPipeR Manual](https://bioconductor.org/packages/devel/bioc/html/systemPipeR.html)
  + [systemPipeRdata Manual](https://www.bioconductor.org/packages/devel/data/experiment/html/systemPipeRdata.html)

👉 A complete list of workflow templates and project information is available at [systempipe.org](https://systempipe.org/about/project/).


__Quick Start__

The following will:

  + Clone the workflow using `gert` internally, which eliminates the need to install the Git CLI
  + Enforce minimum package versions
  + Install the exact tagged `param/` and `data/` releases
  + Create a reproducible local workflow environment

```
library(systemPipeRdata)
genWorkenvir_gh(url = "https://github.com/systemPipeR/sprwf-varseq.git", mydirname = "sprwf-varseq")
setwd("sprwf-varseq")
getParam_gh()
getData_gh() # omit if sample data is not needed
```
> Note: `param/` and `data/` directories are protected by default. If they already exist, they are backed up before new files are installed. See `?getParam_gh` and `?getData_gh` for overwrite options.

The version enforcement can be overwritten (not recommended) via the `force_min_version` argument:

```
genWorkenvir_gh(..., force_min_version = TRUE)
```

For more information, consult the help pages: `?genWorkenvir_gh`, `?getParam_gh`, and `?getData_gh`.

__Additional Options__

To use other  `param` and `data` repos than the defaults, their URLs can be provided under the corresponding 
`*_repos` arguments. 

```
getParam_gh(param_repo="https://github.com/systemPipeR/sprwfcmp-param")
getData_gh(data_repo="https://github.com/systemPipeR/sprwfcmp-data")
```

__Git CLI Approach__

Alternatively, the workflow repos can be cloned with the standard `git clone`
command. Downloading the repos as a Zip file is another option. After this the
`param` and `data` directories need to be populated with the above `get*`
commands, or by manually copying the corresponding directories from the
`sprwfcmp-param` and `sprwfcmp-data` repositories.

