---
layout: default
permalink: documentation/HowToUse.html
title: "Documentation: How To Use"
---

#How To Use

##Checking files with the Online GUI 
<ol type="1">
  <li>Go here for the latest version: https://mediaarea.net/MediaConchOnline/checker</li>
  <li>Register an account by creating  your username / password, which will be emailed to you with instructions. Then log in.</li>
  <li>Choose a policy</li>
  <li>Choose a file</li>
  <ul>
  <li>You can check a [local file](#check-local-file) by selecting the “check file by upload” tab</li>
  <li>Choose one from [the Internet](https://mediaarea.net/MediaConch/documentation/HowToUse.html#check-online-file) by selecting the “check online files” tab, or</li>
  <li>Use the test files uploaded to the server by selecting the “check server files” tab</li>
  </ul>

  <li>Click “Check Files”</li>
  <li>Once checked, the results will appear below and you can see the reports for each section by clicking on the “eyecon” ![eyecon][images/eyecon.png] (3rd screenshot) or download them by clicking the ![down arrow][images/downArrow.png]</li>
</ol>
e
MediaConch currently consists of three main sections, “Checker,” “Policies,” and “Display.”

##Checker
- [Check local file](#check-local-file)
- [Check online file](#check-online-file)
- [Check local folder](#check-local-folder)
- [Reporting](#reporting)
- [Policy Report](#policy-report)
- [Implementation Report](#implementation-report)
- [MediaInfo Report](#mediainfo-report)
- [MediaTrace Report](#mediatrace-report)
- [Exporting Reports](#exporting-reports)

##Policies
- [Type](#type)
- [Field](#field) 
- [Occurrence](#occurrence)
- [Validator](#validator)
- [Value](#value)
- [Free Text Mode](#free-text-mode)

##Display 
- [Import display set](#import-display-set)
- [Export display set](#export-display-set)
- [Delete selected display file](#delete-selected-display-file)

MediaConch currently consists of three main sections, "Checker," "Policies," and "Display."

##Checker

In the "Checker" section, files may be checked for conformance using policies defined by the user. A user may choose from either an existing policy in MediaConch or from an imported XSLT or Schematron policy file. 

###Check local file

“Check local file” allows a user to select a file or files from a local computer. A user may choose from either an existing policy and display in MediaConch or from an imported XSLT or Schematron policy file. Policies will be run when selecting the "Check files" button.

Example: /Users/mycomputer/mediafiles/ffv1.mkv

###Check online file

“Check online file” allows a user to select a file using a URL path. A user may choose from either an existing policy and display in MediaConch or from an imported XSLT or Schematron policy file. Please note that this feature supports HTTP/HTTPS/FTP/FTPS application protocols. Policies will be run when selecting the "Check files" button.

Example: *http://www.mywebsite.com/media/ffv1.mkv*

###Check local folder

“Check local folder” allows a user to select a folder of files from a local computer or volume. A user may choose from either an existing policy and display in MediaConch or from an imported XSLT or Schematron policy file. Policies will be run when selecting the "Check files" button.

Example: */Users/mycomputer/mediafiles/* 

###Reporting

Once a file or files are “checked,” several conformance checking reports are generated. These reports are made viewable by clicking on the “eyecon" next to each report, where, in ”View Mode,” a report is overlaid onto the GUI for review. 

###Policy Report

A policy report will declare whether a particular file is either wholly VALID or NOT VALID according to the prescribed policy tests. A file will only be considered VALID if all rules and asserts are found to be true. When declared NON VALID, a text-based Policy Report (FileName_PolicyReport.txt) will list all failed rules and asserts. 

For example, a line from a policy report states the following failed rule:

`<policy title="General FileExtension must be mkv">`
`<context value="track[@type='General']/FileExtension = 'mkv'"/>`
`<test outcome="fail" reason="is not true"/>`

In this example, the stated policy rule (General FileExtension must be mkv) proved not to be true, causing a failed test outcome (in this case the file extension was .avi). 

###Implementation Report

An implementation report will declare whether a particular file is either VALID or NOT VALID according to specifications of Matroska, FFV1, and LPCM. Currently, a text-based Implementation Report (FileName_ConformanceReport.txt) will list a general readout of container and video streams, including whether a required field has either passed or failed specification.

###MediaInfo Report

In View Mode, a user may navigate through an interactive jstree-grid of a file's MediaInfo general report. This report may be exported in a well-formed XML format. 

###MediaTrace Report

In View Mode, a user may navigate through an interactive jstree-grid of a file's more verbose MediaTrace report. Like MediaInfo's general report, this report may be exported in a well-formed XML format.  

User Note: When opening MediaTrace in View Mode, offsets will be addressed in hexadecimal, or “hex” notation. This differs from the MediaTrace XML output, which addresses offset in decimal notation. 

###Exporting Reports

Reports can be downloaded by either clicking on the down arrow (↓) found directly to the right of each report, or by clicking on the “Download” button located at the bottom right of each report in View Mode. 

User Note: When switching from Checker to Policies or Display modes, any analysis results will be discarded. An alert will prompt the user as a reminder to export all reports before the changeover. 

##Policies

In the "Policies" section, a user can create policy tests as well as import previously generated policy sets in either XSL or Schematron format. 

Policy sets consist of individual rules and asserts. A policy may contain one or more rules, and rules may consist of one or more asserts. Rules and asserts typically contain a metadata field (e.g., “Format”), that field’s associated metadata stream type (e.g., “General), a validator (e.g., “is_equal), and a desired value (e.g., “Matroska”). Rules and asserts are automatically saved during creation, but may be duplicated or deleted by the user using the associated buttons on each rule/assert window. 

For example, the following rule/assert would ensure that all reported files must contain a frame rate associated with the NTSC broadcast standard:

- Type: General
- Field: FrameRate
- Validator: Equal
- Value: 29.970

###Type

Allows a user to select from a list of available metadata stream types. These streams include General, Video, Audio, Image, Text, Menu, or Other. 

Example: *General*

###Field

Allows a user to select from a list of associated fields. Fields vary according to what type of metadata stream is selected. 

Example: *General/UniqueID*

###Occurrence

Allows a user to select whether a rule or assert occurs more than once in reportage. 

Example: *Occurrence:1*

###Validator

Validators for MediaConch include *is_equal*; *is_not_equal*; *is_greater than*; *is_less_than*; *is_greater_or_equal_than*; *is_less_or_equal_than*; *exists*; *does_not_exist*; *contains_string*.

**is_equal**: Requires the reported field value to be the same as the associated policy value.

Example: *General/Format is_equal to Matroska*

**is_not_equal**: Requires the reported field value to be different as the associated policy value.

Example: *General/Format is_not_equal to MPEG-4*

**is_greater than**: Requires the reported field value to be greater than the associated policy value.

Example: *General/Duration is_greater_than 1 mn*

**is_less_than**: Requires the reported field value to be less than the associated policy value.

Example: *Audio/Channels is_less_than 2 Channels*

**is_greater_or_equal_than**: Requires the reported field value to be greater or equal than the associated policy value.

Example: *Video/FrameCount is_greater_or_equal_than 1*

**is_less_or_equal_than**: Requires the reported field value to be less or equal than the associated policy value.

Example: *Video/FrameRate is_less_or_equal_than 29.970*

**exists**: Requires the reported field value to exist.

Example: *Video/Width_Original exists*

**does_not_exist**: Requires the reported field value to not exist.

Example: *Video/Width_CleanAperture does_not_exist*

**contains_string**: Requires the reported field value to contain an associated string.

Example: *General/CompleteName contains_string ffv1*

###Value

Allows a user may select a desired value . 

User note: When creating a value, do not include any associated strings (e.g., "pixels"). 

###Free Text mode

In addition to the Editor, policies may also be edited in Free Text mode. Free Text uses the XML Path Language, or XPath. An example of a MediaConch XPath expression in Free Text mode includes the following:

Example: *track[@type='General']/FileExtension = 'mkv'*

##Display

The Display section will allow a user to apply various display XSLs for use with policy and implementation check reports in the checker section. MediaConch has provided example HTML, XML and TXT displays. Once a display XSL is imported, it can be actived by selecting the display in the "Choose a Display" dropdown menu located in the Checker section. 

###Import display set

Allows a user to import a display XSL file to the display set. 

###Export display set

Allows a user to export a display XSL file to the display set. 

###Delete selected display file

Allows a user to delete a display XSL file from the display set. 


