# HCV Labware Import

Docker image for processing the `Summary.csv` file produced by the [HCVTyper pipeline](https://github.com/folkehelseinstituttet/hcvtyper) into a format suitable for import into LabWare.

## Tools Included

- **R 4.4.1** (based on rocker/r-ver)
- **R packages:**
  - `dplyr` - data manipulation
  - `readr` - reading and writing data files
  - `stringr` - string operations
- **System libraries:**
  - libcurl4-openssl-dev
  - libssl-dev
  - libxml2-dev

## Download

Pull the image from Docker Hub:

```sh
docker pull ghcr.io/jonbra/hcv-labware-import:v1.0.1
```

## Usage

Run the container with your input CSV file:

```sh
docker run --rm \
  -v "$(pwd):/input" \
  -v "$(pwd):/output" \
  ghcr.io/jonbra/hcv-labware-import:v1.0.1 \
  /input/Summary.csv \
  /output/run_name
```

### Arguments

- First argument: Path to the input CSV file (Summary.csv)
- Second argument: Run name (used as prefix for the output file)

## Repository

Source code: https://github.com/jonbra/hcv-labware-import


