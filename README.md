# geo_Cancer_Prognostic_Datasets_Retriever
GEO Cancer Prognostic Datasets Retriever is a Bioinformatics tool for cancer prognostic dataset retrieval from the GEO database.
## Summary
<p>Gene Expression Omnibus (GEO) Cancer Prognostic Datasets Retriever is a Bioinformatics tool for cancer prognostic dataset retrieval from the GEO database. It requires a GeoDatasets input file listing all GSE dataset entries for a specific cancer (ex. Bladder cancer), obtained as a download from the GEO database. This Bioinformatics tool functions by applying two heuristic filters to examine individual GSE dataset entries listed in a GEO DataSets input file. The Prognostic Text filter flags for prognostic keywords (ex. “prognosis” or “survival”) used by clinical scientists and present in the title/abstract entries of a GSE dataset. If found, this tool retrieves those flagged datasets. Next, the second filter (Prognostic Signature filter) filters these datasets further by applying prognostic signature pattern matching (Perl regular expression signatures) to identify if the GSE dataset is a likely prognostic dataset.</p>

## Installation
geo_Cancer_Prognostic_Datasets_Retriever can be used on any Linux or macOS machines. To run the prgram, you need to have the following programs installed on your computer:

<p><ul><li><b>Perl</b> (version 5.30.0 or later)</li></ul></p>
<p><ul><li><b>cURL</b> (version 7.68.0 or later)</li></ul></p>
By default, Perl is installed on all Linux or macOS operating systems. Likewise, cURL is installed on all macOS versions. cURL may not be installed on Linux and would need to be manually installed through a Linux distribution’s software centre. It will be installed automatically on Ubuntu linux by geo_Cancer_Prognostic_Datasets_Retriever.

## Data file
The required input file is a GEO DataSets file obtainable as a download, upon querying for any particular cancer (ex. “Bladder cancer”), from the <a href="https://www.ncbi.nlm.nih.gov/gds/">GEO DataSets</a>.

<b>Steps to manually download a GeoDatasets cancer input file:</b>

<b>1. Visit the GeoDatasets database and type "bladder cancer" in the search box and hit enter</b>
![alt text](https://github.com/AbbasAlameer/geo_Cancer_Prognostic_Datasets_Retriever/blob/a3ffb536a60efdf96f8d495d2863136896f62f87/images/Page_1.png?raw=true)
<b>2. From the results page click on "Send to", then select "File" in the "Choose Destination" section of the drop-down menu. Finally, click on "Create file" of the same drop-down menu</b>
![alt text](https://github.com/AbbasAlameer/geo_Cancer_Prognostic_Datasets_Retriever/blob/a3ffb536a60efdf96f8d495d2863136896f62f87/images/Page_3.png?raw=true)
<b>3. When prompted, save the file</b>
![alt text](https://github.com/AbbasAlameer/geo_Cancer_Prognostic_Datasets_Retriever/blob/a3ffb536a60efdf96f8d495d2863136896f62f87/images/Page_4.png?raw=true)
<b>4. The downloaded GeoDatasets input file can be renamed into something more descriptive (ex. bladder_cancer_GEO.txt)</b>

## Execution instructions
Obtain a GeoDatasets input file for a specific cancer (for example using the search query “Bladder cancer”) and save it in the '/data/' directory. Next, navigate to the '/bin/' in which geo_Cancer_Prognostic_Datasets_Retriever is found and run it with the following command:

```diff
`geo_Cancer_Prognostic_Datasets_Retriever -h [-f or -d INPUT_GEO_FILE] [-p PLATFORM_CODES] [-c CANCER_TYPE] [-o OUTPUT_FILE]`
```

If a GeoDatasets input file for a cancer is present, run this command:

```diff
./geo_Cancer_Prognostic_Datasets_Retriever -f bladder_cancer_GEO.txt -p "GPL570 GPL97 GPL96" -c bladder_cancer -o bladder_cancer.out
```
Alternatively, If downloading a GeoDatasets input file for a cancer, run this command:

```diff
./geo_Cancer_Prognostic_Datasets_Retriever -d "bladder cancer" -p "GPL570 GPL97 GPL96" -c bladder_cancer -o bladder_cancer.out
```

The output file of geo_Cancer_Prognostic_Datasets_Retriever will be found in the '/results/' directory.

<p>Help information can be read by typing the following command:</p>  

```diff
./geo_Cancer_Prognostic_Datasets_Retriever --help
```

<p>This command will print the following instructions:</p>

```diff
Usage: geo_Cancer_Prognostic_Datasets_Retriever -h [-f or -d INPUT_GEO_FILE] [-p PLATFORM_CODES] [-c CANCER_TYPE] [-o OUTPUT_FILE]

Mandatory arguments:
  INPUT_GEO_FILE        query GEO datasets file or GEO datasets search query
  PLATFORM CODES        list of GPL platform codes
  CANCER_TYPE           cancer type
  OUTPUT_FILE           name of file which will contain the output

  Optional arguments:
  -h                    show help message and exit
  ```

## License
All the code is licensed under the <a href="http://www.gnu.org/licenses/gpl-2.0-standalone.html">GNU General Public License, version 2 (GPLv2).</a> 

## Contact
<p><b>geo_Cancer_Prognostic_Datasets_Retriever was developed by:</b><br>
<a href="http://kuweb.ku.edu.kw/biosc/People/AcademicStaff/Dr.AbbasAlameer/index.htm">Abbas Alameer</a>,<br>
Bioinformatics and Molecular Modelling Group,<br> 
<a href="http://kuweb.ku.edu.kw/ku/index.htm">Kuwait University</a><br>
Email: abbas.alameer(AT)ku.edu.kw</p>

## Support
<address>Please email <a href="mailto:abbas.alameer@ku.edu.kw">Abbas Alameer</a> to obtain support for geo_Cancer_Prognostic_Datasets_Retriever.</address>
