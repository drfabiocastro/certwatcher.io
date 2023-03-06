---
title: 'Templating Guide'
date: 2019-02-11T19:27:37+10:00
draft: false
weight: 5
---

A detailed guide on creating and customizing templates.

<!--more-->

## Quickstart

Certwatcher is designed to be based on `YAML` templates, which define how obtained certificates will be processed. This allows certwatcher to be extensible and flexible.

The templates are written in YAML which specifies a simple human-readable format to quickly define the execution process.

### Guide to write your own certwatcher template

---

## Template Details

Each template has a `unique` ID which is used during output writing to specify the template name for an output line.

The template file ends with YAML extension. The template files can be created any text editor of your choice.

```yaml
  id: fas-keywords-malware
```

ID must not contain spaces. This is done to allow easier output parsing.

### Information

Next important piece of information about a template is the info block. Info block provides `id`, `name`, `author`, `description`, `classification`, `reference`.

Example of an info block


```yaml

  info:
    id: fas-keywords-malware
    name: Ads Malware Delivery
    author: Fábio Castro
    description: List of Ads Malware Delivery for keyword matching.

    classification:
      tags:
        - ads
        - windows

    reference:
      - https://github.com/certwatcher/certwatcher-templates


```
Actual requests and corresponding matchers are placed below the info block, and they perform the task of making analyzed.

### Keywords

The keywords used by Certwatcher are used to filter keywords that correspond to the domain returned by the certificate logs in the YAML file. These keywords can be useful to limit the amount of logs that need to be analyzed

```yaml

  # Keywords for domain matching.
  keywords:
    - acrobat
    - adwcleaner
    - airtable
    - airvpn
    - androidstudio
    - anydesk

```

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.

### Matchers

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

``` yaml

  matchers:
    # Using regular expressions to search in the page body.
    - pattern: "\\b(UA-167472923|UA-145098812)\\b"
      type: body
      description: "Matches UA tracking codes in the body of the request."

    - pattern: "\\bGTM-[A-Z0-9]+\\b"
      type: body
      description: "Matches Google Tag Manager container IDs"

    - pattern: "\\b(RC-|YCL)[0-9]+\\b"
      type: body
      description: "Matches Yahoo Search Ads conversion tracking IDs"

```

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry’s standard dummy text ever since the 1500s.

### Top-Level Domain (TLDs)

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

``` yaml

  tlds:
    - pattern: "\\b\\w+\\.net|org|io|info|xyz|top|club|pw|tk|ga|ml|cf|gq|online|tech\\b"
      type: url
      description: "Matches common TLDs used for phishing"

    - pattern: "\\b\\w+\\.link|bid|download|loan\\b"
      type: url
      description: "Matches common TLDs used for phishing"


```
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry’s standard dummy text ever since the 1500s.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

### Structure of the template:

- `id`: a unique identifier for the set of keywords.
- `name`: the name of the keyword set.
- `country`: location of fraud or phishing site, common to have keywords for specific countries.
- `author`: the name of the author or creator of the keyword set.
- `description`: a description of the keyword set and its purpose.
- `classification`: additional information about the classification of the keyword set, including tags and references.
- `references`: a list of relevant references related to the set of keywords.
- `keywords`: a list of keywords relevant to the keyword set.
- `matchers`: a list of match types used to identify keywords on phishing sites. Includes an exact word match and a pattern match to identify specific form fields.
- `tlds`: a list of top-level domain patterns used to identify URLs relevant to the keyword set. Includes a description of each pattern.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry’s standard dummy text ever since the 1500s.