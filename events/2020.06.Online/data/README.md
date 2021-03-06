# WoT Testing - June 2020 Online Plugfest 
## Data Capture

During the plugfest, data should be captured in CSV files so that we can
generate a report.  The following types of data should be captured.  Each
type of data has a CSV template which should be used and a subdirectory to
collect contributions.  To avoid merge conflicts, each organization should
set up a subdirectory for their own contributions during the plugfest, then
these will be merged into a single CSV file after the plugfest.

* [TD validation](validation): Validation data for each TD will be recorded
  here. This combines both automatic and manual validation data.
  Manual assertions should be provided using the 
  [provided template](validation/manual/template.csv) in a subdirectory and
  file with the same name as the corresponding TD in 
  [validation/manual](validation/manual).
* [Implementations](impl): Information on each implementation should be
  recorded here, using the [provided template](impl/template.csv).
  Multiple subdirectories may be used, the CSV files will all be concatenated.
* [Interoperability tests](interop): When it has been confirmed that
  two implementations work together, that fact should be noted
  here using the [provided template](interop/template.csv).
  Multiple subdirectories may be used, the CSV files will all be 
  concatenated.
  
Note: To discuss, it might be more convenient to place some of the above
input files, eg the manual assertions and maybe also the interop and impl files,
adjacent to the TD input files.  For now let's use this structure, later the scripts
may be updated to allow that.
  
## Scripts
* **validate.sh**: (WIP) 
  Run to validate all TDs in the [TD archive](../TDs) and generate CSV data
  for feature support.  Output CSVs listing supported features for each TD 
  will be in [inputs/results](inputs/results/README.md).  See 
  [TDs/README.md](../TDs/README.md) for instructions on how to arrange and
  name TDs.  Manual assertions for each TD may optionally be placed in 
  a CSV file with the same name as the TD in the same directory as that TD.
  Use [TDs/manual.csv](../TDs/manual.csv) as a template.
* **report.sh**: (WIP) After running validation, run this script to generate
  the plugfest implementation report. The output report will be placed in
  [report.html](report.html).  Do not edit this file manually, as it will be
  overwritten each time the script is run.  If you need to edit the text,
  modify the [report template](inputs/templates/report.html).
