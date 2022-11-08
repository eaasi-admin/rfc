# Meeting Notes

[Dev Meeting Notes](https://docs.google.com/document/d/1XVAfRK5LuGlTonzzlI9wvwDlMaaJazjZPLKlGRTRX_k/edit?usp=sharing)

# Summary

Each resource has a detail page presenting metadata and settings where users can edit metadata if role and resource permissions level permits

# Motivation

Details regarding the contents of an object or environment are essential to making informed decisions about the use of resources in an emulation project. Users may utilize detail pages as an additional discovery step if the information presented in search results is insufficient. Detail pages also provide an opportunity to gather or correct information for user/org private resources that wasn't captured during import or configuration. 

# Proposal

**All resources must have a detail page**

## Environment detail

* Environment detail pages have 5 tabs:
  * Metadata - presents information about the hardware and software used by the environment
  * Screenshots
  * History - provides details of changes made to the environment 
  * Settings - where users can change emulator settings like environment can print, internet enabled, etc.
  * Access - users can turn on/off sharable access link (in future this will also be home to user-level access permissions)

### Metadata

![707_Environment-Detail](https://user-images.githubusercontent.com/70149705/200668145-19e616ef-85d7-4649-bdea-3287bcc944a8.png)

The metadata tab contains the following sections:

**Descriptive metadata (Header)**

* (Icon) Resource type
* (Icon) Permission status
* Environment Name
* Description

**Hardware - cannot be edited from detail page**

* Emulator template details - fields displayed TBD
* Drive configuration - presents drives with object resources attached to them

**Software**

*MVP*
* Software environment details
  * Operating System
  * Operable Software

* Entries for software environment components may be edited
  * Users may identify what software or content is operable in the environment

***Future iteration***
  
![Environment_wireframe_Software-edit](https://user-images.githubusercontent.com/70149705/200668364-ce79592c-2a5d-45a9-a17c-381a63a0b2f7.png)

* The configured software metadata edit interface should appear if a user selects the edit button next to an entry in an environment's detail page. This widget allows users to edit or add statements to the details of software installed and configured in the environment.
* Users may compile claims from a limited set of properties for either the environment or configured software (see options below)
* The system should determine the permitted properties based on the item selected by the user. For example, if the user selects Microsoft Windows 95, the system should only allow properties of an Operating System.
* If a user creates a claim for a property that is already defined, the new entry takes precedence. We assume that the user is making a correction.
* Users must be able to add qualifiers to their claims to allow for more detailed record entry.

**Editable Properties**

| Item | Property | Definition |
| --------- | --------- | --------- |
| Environment | OS Installed/Configured | Name of installed/configured OS |
| Environment | Software Installed/Configured | Name of installed/configured software |
| [Operating System Name] | DateTime | Date and time assigned to software |
| [Operating System Name] | Language | Language selected for use in software (primary language indicated in UI) |
| [Operating System Name] | User information | Account type configured in operating system (Qualifiers: username, password, pin) |
| [Operable Software Name] | Language | Language selected for use in software |
| [Operable Software Name] | User information | Account type configured in software (Qualifiers: username, password, organization) |
| [Operable Software Name] | Executable Syntax | Command required to execute software |
| [Operable Software Name] | Executable Location | Path to location of software executable |
| [Operable Software Name] | Save Location | Path to location where software saves outputs |

### Screenshots

![Environment_wireframe_Screenshots](https://user-images.githubusercontent.com/70149705/200669079-f5136543-55b7-40ae-a00e-03b899af9302.png)

![Environment_detail___Screenshots](https://user-images.githubusercontent.com/70149705/200669108-7a940819-4e94-469f-8dba-5c9d8f87bb7f.png)

* Users must be able to see a larger view of a screenshot when a thumbnail is clicked.
* Users must be able to scroll through screenshots in full view.
* Screenshots should be displayed with a timestamp noting it's creation date and time.

### History

* Environment history entries include all changes made dating back to the creation of the base environment
* Entries should include the date of the change and the description provided by the user during the save process.
* **Users should have the option to fork environments from any point in the environment's history, making a new environment from the previous state of the existing environment**

### Settings

* Users may change and save certain settings (TBD) that determine emulator behavior when running the environment

### Access

<img width="747" alt="Environment-detail_access" src="https://user-images.githubusercontent.com/70149705/200668440-4e8123f2-e4d7-49b8-8fb6-4b9fa25dd5e1.png">

* Environment access links should be set to off by default
* If turned off, any attempt to access via a shared link will be denied
* If turned on, any attempt to access via a shared link will lead directly to the end-user environment access page

## Object Detail

* Object detail pages have 2 tabs:
  * Metadata
  * Photos - The Photos page allows users to view photos of an object added during import or from the Photos page.

### Metadata

![721_Object-detail](https://user-images.githubusercontent.com/70149705/200670244-b36359e9-a89b-4d68-94b6-6dd933810638.png)

* Descriptive metadata should provide the user a clear understanding of an object's contents and any information necessary to use the object.
* Object file section should provide a comprehensive view of the object's component parts
* Users may only see the metadata of resources they have access to (e.g., “my resources,” local resources, and network resources)
* Users must be able to edit the following in "Edit Mode" of an object detail page:
  * Add or delete "External Identifiers"
  * Product Key
  * Allowed # of instances
  * Add software titles that the Object includes
  * Object file order
  * Object file format
  * Object file label

### Photos

![720_Object-detail_1](https://user-images.githubusercontent.com/70149705/200669932-62481b53-479e-4d13-8334-bf27c6f68bf7.png)

![720_Object-detail_2](https://user-images.githubusercontent.com/70149705/200669945-523bf93d-95b6-420f-aaa0-7678cde46221.png)

* Users must be able to see a larger view of a photo when a thumbnail is clicked.
* Users must be able to scroll through photos in full view.
* Photos should be displayed with the filename

# Open Questions

* How should the action menu be displayed in the detail page? Currently a button to hide/reveal it, but could be something more dynamic.
* Does the Review Mode/Edit Mode feature stay? Currently allows the user to see editable fields when edit mode is on. Would only be applicable on Metadata tab.

# Answered Questions


