---
title: 'sbomqs, an open source tools to quality check your SBOMS'
date: '2023-02-02'
tags: [Amazon ECR, sbomqs, SPDX, SBOM]
---

When putting together a previous post on how to use open source tools to create a software bill of materials (SBOM), Ritesh Noronha alerted me to another project, [sbomqs](https://github.com/interlynk-io/sbomqs) that aims to simplify the evaluation of SBOM quality for both producers and consumers. A quality SBOM is one that is accurate, complete, and up-to-date. It should accurately reflect the components and dependencies used in the software application, including their version and optionally any known vulnerabilities. In addition, it should be easily accessible and understandable by stakeholders, such as developers, security teams, and compliance officers. I guess these are some of the heuristics used.

I thought it was interesting enough to dive into and see how we can use this to check out the output from the previous post, [Building a software bill of materials (SBOM) using open source tools]()

**Installation**

To install [sbomqs](https://github.com/interlynk-io/sbomqs), we can follow the instructions on the GitHub project.


```
go install github.com/interlynk-io/sbomqs@latest
go: downloading github.com/interlynk-io/sbomqs v0.0.2
go: downloading github.com/samber/lo v1.37.0
go: downloading github.com/spf13/cobra v1.6.1
go: downloading go.uber.org/zap v1.24.0
go: downloading github.com/olekukonko/tablewriter v0.0.5
go: downloading github.com/spdx/tools-golang v0.4.0
go: downloading github.com/CycloneDX/cyclonedx-go v0.7.0
go: downloading golang.org/x/exp v0.0.0-20220303212507-bbda1eaf7a17
go: downloading go.uber.org/atomic v1.7.0
go: downloading go.uber.org/multierr v1.6.0
go: downloading github.com/mattn/go-runewidth v0.0.9
go: downloading github.com/spdx/gordf v0.0.0-20201111095634-7098f93598fb
```

After making sure sbomqs is in the path, I can check it works and the version. As we can see, this is still early days for this project.

```
sbomqs version
  ____    ____     ___    __  __    ___    ____
 / ___|  | __ )   / _ \  |  \/  |  / _ \  / ___|
 \___ \  |  _ \  | | | | | |\/| | | | | | \___ \
  ___) | | |_) | | |_| | | |  | | | |_| |  ___) |
 |____/  |____/   \___/  |_|  |_|  \__\_\ |____/
sbomqs: sbomqs application provides sbom quality scores.

GitVersion:    v0.0.2
GitCommit:     unknown
GitTreeState:  unknown
BuildDate:     unknown
GoVersion:     go1.18.1
Compiler:      gc
Platform:      linux/amd64
```

From the docs, it looks like we can run this tool against the SBOM we created in the previous post. We can find out what parameters it takes via the command line help (it is also in the README of the project)

```
sbomqs score --help
provides a comprehensive quality score for your sbom

Usage:
  sbomqs score [flags]

Flags:
      --category string       scoring category
      --dirpath string        sbom dir path
      --filepath string       sbom file path
  -h, --help                  help for score
      --reportFormat string   reporting format basic or detailed
```

In the previous post, I had originally tried (and failed) to attach an SBOM in json format. I thought I would try and see how this tool handles this.

```
sbomqs score --filepath  os-security-sbom.spdx.json
```

And sure enough, it printed out my very first quality assessment for my SBOM. I got a score of 8.0. The docs say that the score is 0 to 10, with 10 being the highest score, so I think I am on the right track with this score.

```
SBOM Quality Score: 8.0	os-security-sbom.spdx.json
+-----------------------+--------------------------------+-----------+--------------------------------+
|       CATEGORY        |            FEATURE             |   SCORE   |              DESC              |
+-----------------------+--------------------------------+-----------+--------------------------------+
| NTIA-minimum-elements | Components have supplier names | 0.0/10.0  | 0/15 have supplier names       |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Doc has authors                | 10.0/10.0 | doc has 2 authors              |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Doc has relationships          | 10.0/10.0 | doc has 98 relationships       |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have versions       | 10.0/10.0 | 15/15 have versions            |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Doc has creation timestamp     | 10.0/10.0 | doc has creation timestamp     |
|                       |                                |           | 2023-01-31T18:09:28Z           |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have uniq ids       | 9.3/10.0  | 14/15 have unique ID's         |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have names          | 10.0/10.0 | 15/15 have names               |
+-----------------------+--------------------------------+-----------+--------------------------------+
| Quality               | Components have no deprecated  | 10.0/10.0 | 0/15 components have           |
|                       | licenses                       |           | deprecated licenses            |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have primary        | 0.0/10.0  | 0/15 components have primary   |
|                       | purpose defined                |           | purpose specified              |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have multiple       | 4.7/10.0  | comp with uniq ids: cpe:0,     |
|                       | formats of uniq ids            |           | purl:14, total:15              |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have valid spdx     | 9.3/10.0  | 14/15 components with valid    |
|                       | licenses                       |           | license                        |
+-----------------------+--------------------------------+-----------+--------------------------------+
| Semantic              | Components have checksums      | 0.0/10.0  | 0/15 have checksums            |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Components have licenses       | 9.3/10.0  | 14/15 have licenses            |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Doc has all required fields    | 10.0/10.0 | Doc Fields:true Pkg            |
|                       |                                |           | Fields:true                    |
+-----------------------+--------------------------------+-----------+--------------------------------+
| Sharing               | Doc sharable license           | 10.0/10.0 | doc has a sharable license     |
|                       |                                |           | free 1 :: of 1                 |
+-----------------------+--------------------------------+-----------+--------------------------------+
| Structural            | Spec File Format               | 10.0/10.0 | provided sbom should be in     |
|                       |                                |           | supported file format for      |
|                       |                                |           | spec: json and version:        |
|                       |                                |           | json,yaml,rdf,tag-value        |
+                       +--------------------------------+-----------+--------------------------------+
|                       | SBOM Specification             | 10.0/10.0 | provided sbom is in a          |
|                       |                                |           | supported sbom format of       |
|                       |                                |           | spdx,cyclonedx                 |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Spec is parsable               | 10.0/10.0 | provided sbom is parsable      |
+                       +--------------------------------+-----------+--------------------------------+
|                       | Spec Version                   | 10.0/10.0 | provided sbom should be in     |
|                       |                                |           | supported spec version for     |
|                       |                                |           | spec:SPDX-2.3 and versions:    |
|                       |                                |           | SPDX-2.1,SPDX-2.2,SPDX-2.3     |
+-----------------------+--------------------------------+-----------+--------------------------------+
```

The project repo contains some additional command line recipes to show you how you can use this project. Well worth checking those out.

Finally, the doc provides some details as to the criteria evaluated and what they mean.

**Conclusion**

In this short blog post, I looked at a new open source tool that looks to assess the quality of a software bill of materials (SBOM). I can see how this might be useful as part of a broader solution, and should help move SBOMs from being a static asset to something more actionable. As I mentioned in the post, this is an early project (0.2 version) so will keep an eye on this tool, and encourage you all to try it out and provide feedback to the maintainers.

I would love the hear more from readers about what your biggest pain points and frustrations when you work with open source is. Please complete [this very short survey](https://pulse.buildon.aws/survey/PJRTOUMK), as this would help me massively. (All responses are anonymous) 

You can check out and explore the sbomqs tool [here](https://github.com/interlynk-io/sbomqs). 