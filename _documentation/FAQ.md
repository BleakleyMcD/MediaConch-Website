---
layout: default
permalink: documentation/FAQ.html
title: "Documentation: FAQ"
---

# FAQ

- [What is MediaConch?](#what-is-mediaconch)
- [What file formats can I use with MediaConch?](#what-file-formats-can-i-use-with-mediaconch)
- [What are the benefits of file conformance checking?](#what-are-the-benefits-of-file-conformance-checking)
- [How can I provide feedback?](#how-can-i-provide-feedback)

## What is MediaConch?

MediaConch is an extensible, open source software project that helps information professionals validate and standardize audiovisual files for long-term preservation. It offers users more flexibility and technical control over the contents of open audiovisual formats, revealing how the file is built, rather than just how it plays. It does so by enabling users to define criteria for moving image files and test the collections of files against that criteria for select open formats such as Matroska (mkv) and FF Video Codec 1 (FFV1). 

The core MediaConch application is available through three adaptable program interfaces, via: the command line, a graphical user interface, or a web-based interface, for uses such as integration into existing archival processing infrastructures as a microservice, local detailed file inspection for irregular video files, or server-based batch-level file checking in distributed processing systems. These three shells allow greater flexibility of product use to serve the various needs of memory institutions. 
 

## What file formats can I use with MediaConch?

Supported Formats:
<ul>
<li><b><a href="https://en.wikipedia.org/wiki/MatroskaMatroska">Matroska</a></b> is a multimedia container format with files ending in the suffix of .mkv or .webm. Matroska is a file container, or wrapper, meaning that it holds encoded video and audio streams as well as supplemental metadata. Matroska files are based upon <a href="https://github.com/MediaArea/ebml-specification/blob/master/specification.markdown">EBML</a>, a binary file format similar to XML.</li> 
<li><b><a href="https://en.wikipedia.org/wiki/FFV1">FFV1</a></b> is a lossless, open source codec developed by FFmpeg.</li>
<li><b><a href="https://en.wikipedia.org/wiki/Pulse-code_modulation">LPCM</a></b> is a method for encoding audio. It is an uncompressed audio format.</li> 

MediaConch’s target of the implementation checker is currently compatible with these supported formats: Matroska-wrapped video files encoded with FFV1 (File Format Video Codec 1) and LPCM (Linear Pulse Code Modulation). The goal of MediaConch is to check open source preservation-level files for archival conformance at the file level and within the localized policy level per the institution. Because MediaConch builds on MediaInfo, it can provide general file information and analysis on many <a href="https://mediaarea.net/en/MediaInfo/Support/Formats">digital media files</a> and will be extended to a larger variety of formats.

## What are the benefits of file conformance checking?

MediaConch analyzes preservation-level audiovisual files for use in memory institutions, providing a detailed report of a file’s technical metadata and other related information. MediaConch can be used during file creation or ingestion, after a file migration, during a quality analysis or quality control phase, or as part of routine file checkups.

<b>Preservation Standardization:</b> Since digital files deteriorate over time, archives can assure that their files are interoperable and conform to established preservation standards by checking that they adhere to format specifications using MediaConch. Such checking will allow for revitalization of potentially corrupt files, prompting an archive, to correct errors within the file when necessary or create new preservation-level files when feasible.

<b>OAIS Adherence:</b> The conformance checking of files helps archives adhere to the OAIS (Open Archival Information System) reference model. Files can be checked for conformance upon initial digitization, upon ingest into a digital repository, upon migration to different locations, and during regular quality control and checkups, as defined by the implementing memory institution.

<b>QA Expansion:</b> Quality control can be better monitored through MediaConch through algorithmic detection of conformance errors as well as the supplemental institution-based policy conformance checker.  Since files are checked in a systematic way, preservationists can know definitively whether or not the file is working or how the file has changed since the last time it was reviewed (whether that is from previous quality analysis or during digitization, ingestion, or migration. The result is further usability of files, while also maintaining constant contact between the producer and consumer of content, once again adhering to OAIS standards.

<b>Streamlining & Customizing Routine File Checkup Process:</b> Conformance checking with MediaConch allows institutions to perform routine file checkups in a streamlined process. Such checkup standards can be altered according to shifts in standards regarding preservation-level quality, whether established internally or externally. MediaConch allows for potential users to establish their own standards, choosing files based on personal conformance preferences, which can be altered to fit specific, situational needs.

## How can I provide feedback?

Feedback such as requests for clarifications, suggestions, enhancements, or reports of bugs is important for MediaConch. If you find an issue, please visit the <a href="https://github.com/MediaArea/MediaAreaXml/issues">issue tracker at MediaArea’s GitHub repository</a> for the project and create a new issue, where you can describe your suggestion or the bug you’ve found. This would be incredibly helpful and would enable us to improve the tools and experience for you, our intended users.  Once submitted, the issue will be in the public issue tracker and the development team can respond to it or associate improvements to it. 
				                             
				                             
