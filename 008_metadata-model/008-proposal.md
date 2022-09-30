[Dev Planning Notes](https://docs.google.com/document/d/1A-g-b59uG3P5wN2shbcQEG1H_A--uAqfRUg90iMlYTY/edit?usp=sharing)

# Summary

Additional metadata describing environments and objects is compiled and utilized by the EaaSI system.


# Motivation

Additional metadata describing environments and objects is required to power administration, discovery, and automation within EaaSI.


# Proposal

[EaaSI Metadata Schema - V10](https://docs.google.com/spreadsheets/d/1eTJB2dFUaHiLVbEGDn_zpPrpR818fB10vq2iywVi2Og/edit?usp=sharing)

## Environments

Environment description contains system metadata (branches, source node, events, etc.), descriptive metadata (name, description), and description of component parts (hardware environment, operating environment). The **hardware environment** description compiles information regarding the emulator settings and elements of existing templates. The **operating environment** is a description of the operating system, various applications, and content (if present) that may be executed when running the environment in an emulator. An environment may have more than one operating environment, as in computers with multiple bootable partitions.

An annotated example json serialization is available [here](https://docs.google.com/document/d/1zfguiX3gwQgRSsQzrLj31uF6uZlpXn6i0dAfhfOMigY/edit?usp=sharing)

A clean version of the json example is available [here](https://github.com/sth-rbrt/rfc/blob/main/006_metadata-model/environment_example_2022.json}.

## Objects

Object description contains system metadata (permissions, source node, events, etc.), descriptive metadata (name, related software, alternate IDs, etc.), and details of the component object files. The **object files** description provides details that may be applied while configuring an environment with the object, such as the disc label, the original physical format of the disk image, and operating order (?).

An annotated example json serialization is available [here](https://docs.google.com/document/d/1pZYgT3upV0K-YhnUEfKeoxV86k7wRUv0WTi6OJOncPQ/edit?usp=sharing)

A clean version of the json example is available [here](https://github.com/sth-rbrt/rfc/blob/main/006_metadata-model/object_example_2022.json).

## Software

Software metadata may not be managed within EaaSI, but will be referenced periodically for discovery and automation purposes. Current efforts by the EaaSI team have compiled a set of software metadata in a Wikibase instance that may be useful for this purpose. Software metadata is included in the schema documentation linked above.


# Open Questions

* How will EaaSI manage it's use of software metadata? Regular pull from Wikibase? Call only when needed?
* Do we continue to use the METS format for objects?
* Is the terminology used meaningful to users/system? Does this matter?
* How do we expand the model once we get a working version in place? What can we add?

# Answered Questions



# New Implications

Metadata improvement may vastly improve the user experience of EaaSI. Our current search/discovery capabilities are limited by the lack of legible structured data that users can make use of. That said, it also adds a complex layer to manage within the system and steps must be taken to ensure that quality data is collected and that the structure is useful but flexible for future changes. 
