## Elevation data

This repository is an archive of the data prepared [during setup step 2](https://github.com/microsoft/Elevation#download-and-process-data-dependencies)
of the installation of the [Elevation](https://github.com/microsoft/Elevation) sgRNA design tool.  It includes:

 * Off-target data downloaded and processed by the [`CRISPR/data_download.sh`](https://github.com/microsoft/Elevation/CRISPR/data_download.sh) utility
 * GUIDE-Seq genome search data generated by the [`dsNickFury`](https://github.com/michael-weinstein/dsNickFury3PlusOrchid) utility

Clone this repository, then copy the files as described below.  After copying the
data to Elevation, this repository is no longer required and may be deleted.

 * The instructions below are for Linux. On OSX and Windows, `xz` is required.
 * The `.txt` related files are not required. Those files are from intermediary processing, and only archived here for completeness or debugging.

### Setup

1. For convenience, teach the shell about the location of the `Elevation/CRISPR` directory.

```
  export ELEVATION=/path/to/Elevation/CRISPR
```

2. For the *offtarget data*, instead of running the `download_data.sh` script, copy the files from the `offtarget/` directory.

```
  cp offtarget/* ${ELEVATION}/data/offtarget/
```

3. For the *GUIDE-Seq data*, instead of running the `dsNickFury` search utility, decompress and copy the file from the `guideseq/` directory.

```
  xz -dk guideseq/guideseq_unique_MM6_end0_lim999999999.hdf5.xz
  cp guideseq/guideseq_unique_MM6_end0_lim999999999.hdf5 ${ELEVATION}/guideseq/
```
