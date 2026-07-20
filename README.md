<h1>GeoDBToText_Plus</h1>

<p>
GeoDBToText_Plus is an enhanced version of the original 
<a href="https://github.com/NPS-ARCN-CAKN/GeoDBToText">GeoDBToText</a> 
tool. It was redesigned to improve metadata preservation, support complex geodatabase structures, 
and create more reliable non-proprietary text archives from ESRI File Geodatabases.
</p>

<h2>Purpose</h2>

<p>
The purpose of GeoDBToText_Plus is to convert ESRI File Geodatabases into portable, 
human-readable, and machine-readable text formats. This allows GIS datasets to be 
archived and potentially reconstructed in the future without depending on proprietary 
software.
</p>

<h3>Motivation for GeoDBToText_Plus</h3>

<ul>
  <li>
    The original tool was designed primarily for a File Geodatabase containing a 
    single feature class.
  </li>
  <li>
    Metadata was entered manually through GUI input fields instead of extracting 
    existing metadata from the geodatabase.
  </li>
  <li>
    User-entered metadata could overwrite existing metadata and was applied across 
    exported datasets.
  </li>
  <li>
    The tool did not preserve metadata from multiple levels of a geodatabase structure, 
    including:
    <ul>
      <li>File Geodatabase level</li>
      <li>Feature Dataset level</li>
      <li>Feature Class level</li>
    </ul>
  </li>
  <li>
    The delimiter was manually selected by users, despite the tool requiring a 
    consistent format to avoid conflicts with Well-Known Text (WKT) geometry.
  </li>
</ul>


<h3>Improvements in GeoDBToText_Plus</h3>

<ul>
  <li>
    <b>Automatic Metadata Extraction</b><br>
    Extracts existing ESRI metadata directly from the File Geodatabase, Feature Dataset, 
    and Feature Class instead of requiring users to manually enter metadata.
  </li>

  <li>
    <b>Metadata Preservation</b><br>
    Preserves original metadata including titles, tags, summaries, descriptions, 
    credits, and usage limitations.
  </li>

  <li>
    <b>Support for Complex Geodatabase Structures</b><br>
    Handles File Geodatabases containing multiple feature classes and feature datasets.
    Each feature class is exported individually while maintaining its associated metadata.
  </li>

  <li>
    <b>Improved Export Organization</b><br>
    Generates separate metadata and data files with clearer naming conventions to 
    improve readability and archival management.
  </li>

  <li>
    <b>Metadata Cleaning</b><br>
    Removes HTML formatting from ESRI metadata fields to improve readability in exported 
    text files.
  </li>

  <li>
    <b>Consistent Data Formatting</b><br>
    Uses a fixed delimiter for attribute tables to avoid conflicts with commas commonly 
    found in metadata and WKT geometry.
  </li>

  <li>
    <b>Machine-Readable Output</b><br>
    Exports feature classes into CSV and JSON formats for long-term accessibility and 
    interoperability.
  </li>
</ul>


<h3>Workflow Comparison</h3>

<table border="1">
<tr>
<th></th>
<th>Original GeoDBToText</th>
<th>GeoDBToText_Plus</th>
</tr>

<tr>
<td>Metadata Source</td>
<td>Manual user input</td>
<td>Automatically extracted from ESRI metadata</td>
</tr>

<tr>
<td>Geodatabase Support</td>
<td>Primarily single feature class workflows</td>
<td>Multiple feature classes and feature datasets</td>
</tr>

<tr>
<td>Metadata Levels</td>
<td>Feature class metadata only</td>
<td>File Geodatabase, Feature Dataset, and Feature Class metadata</td>
</tr>

<tr>
<td>Metadata Preservation</td>
<td>Existing metadata may be overwritten</td>
<td>Original metadata preserved</td>
</tr>

<tr>
<td>Output Formats</td>
<td>CSV and JSON export</td>
<td>CSV and JSON export</td>
</tr>

<tr>
<td>Metadata Formatting</td>
<td>Raw metadata including HTML formatting</td>
<td>Cleaned, human-readable metadata</td>
</tr>

</table>





<h2>How to Use GeoDBToText_Plus in ArcGIS Pro</h2>

<p>
GeoDBToText_Plus is provided as an ArcGIS Pro Toolbox (<code>.atbx</code>). 
The toolbox contains the tool definition and automatically connects to the 
included Python script. Both the <code>.atbx</code> and <code>.py</code> files 
must remain in the same folder.
</p>

<ol>
  <li>
    Download or clone this repository.
  </li>

  <li>
    Open <b>ArcGIS Pro</b> and open the <b>Catalog</b> pane.
  </li>

  <li>
    Add the toolbox:
    <br>
    <code>Catalog → Toolboxes → Add Toolbox → GeoDBToText_Plus.atbx</code>
  </li>

  <li>
    Open <b>GeoDBToText_Plus</b> from the toolbox.
  </li>

  <li>
    Select the input File Geodatabase:
  </li>

  <li>
    Click <b>Run</b>.
  </li>
</ol>
