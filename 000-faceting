[Dev Planning Meeting Notes](https://docs.google.com/document/d/1A-g-b59uG3P5wN2shbcQEG1H_A--uAqfRUg90iMlYTY/edit?usp=sharing)

[Dev Planning Meeting Notes - 7/14](https://docs.google.com/document/d/1XVAfRK5LuGlTonzzlI9wvwDlMaaJazjZPLKlGRTRX_k/edit?usp=sharing)

# Summary

Certain metadata properties describing environments and objects can be used to filter the resource cards displayed on the Explore Resources and My Resources pages via a sidebar menu. Facets are dynamic and the user can apply multiple facets (to narrow the list of resources displayed matching the selected facets) or deselect facets (to expand the list of resources displayed). 


# Motivation

Users need to locate and understand relevant resources so they can complete actions in the system, such as compiling resources in an emulation project, editing metadata, sharing to node/network, providing access to guest users, etc.

Users also may not know *exactly* the resource they are looking for or what terms would be relevant to put in the keyword search bar. They want to "browse" available resources with some guidance from the system as to their options (possibly *after* completing a keyword search and receiving 1-2 pages worth of results). Faceting is not driven by a desire to find one specific resource but to gain an accurate sense of the number of resources available to the user that meet certain meaningful conditions.


# Proposal

## Current State
Metadata for all resources and each requesting user:
* is fetched from the back-end
* cached in RAM

Facets are presented to the user on the Explore and My Resources pages via the "Refine Your Resources" sidebar in a handful of properties from currently-available metadata:
* Resource Type (Environment, Software, Content, or Image)
* Network Status (Private, Public, or Public + Saved Locally)
* Environment Type (Base, Object)
* Source Organization (always "Shared")
* Operating System (inconsistent smattering of Wikidata QIDs and a few other legacy EaaS strings, e.g. "Eaas-c64")
* Emulator (list of Emulators that are imported in the instance and have at least one environment associated with them)

Selecting one or more facets within these categories:
1) Narrows the number of resource cards displayed to the user according to the selected facet/filter
2) Adds a bar to the top of the results page displaying selected properties as well as the ability to clear all selected filters

## Desired State

UI facet functionality (the behavior once a facet is selected) is working well and as-intended. Improvements at this point are related to performance (in initially fetching displayed resources) and improving the descriptive quality of the facet properties.

* As in keyword proposal, system stores metadata describing resources such that they can be indexed and displayed by UI. Standardized documentation format stores metadata about resources at rest, which can be used for faceting/filtering.
* Redundant storage of metadata and front and back-end reduced to improve performance and establish single source of truth in system.
* Selecting any one individual facet filters displayed resources within seconds.
* For facet properties where there is overlap between user and system (i.e. properties like Environment Type or Emulator that are both necessary for back-end functionality and useful to users to narrow results), all displayed values and properties are, at a minimum, aliased to human-readable values.

### Potential properties for faceting

* Resource Type
* Network Status
* Environment Type (Base, Content)
* Operating System Name
* Source Organization
* Emulator
* Tags
* Developer/Publisher (TBD)


# Open Questions

* When and how is data exchanged for search and display requirements?
* Are there computing benchmarks/targets for
faceting?

# Answered Questions


# Proposed Iterations

Maintain current facet behavior, focus on adjusting metadata capture and storage, then improve user-facing description.
1. Server-side pagination and cache improvements
2. Alias existing facet properties and values to user-meaningful labels
3. Expand available fields/properties/values available in Refine Your Results sidebar (see proposed properties above)
