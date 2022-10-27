# Meeting Notes

Dev Meeting Notes: https://docs.google.com/document/d/1FVOQU9eM6hNaKeOIZCVAfS-G6ljhGbOuht_6rf90c3E/edit?usp=sharing](https://docs.google.com/document/d/1FVOQU9eM6hNaKeOIZCVAfS-G6ljhGbOuht_6rf90c3E/edit?usp=sharing

# Summary

At the start of a configuration session, a second window opens to display three interfaces: the configuration session's change log, environment metadata, and object metadata.

# Motivation

We need users to input information about the changes they make to an environment (e.g., what software they install, settings they've changed) so that we can utilize that information in search, automation, administration, etc. Users also need to see metadata and photos of the resources they're using in a configuration session. There's not enough real estate on the configuration page to accommodate all of these elements.

# Proposal

## Configuration Session Pop-Up

* When a session is started by a user with the Admin, Configuration User, or Guest role a popup window will appear outside the main EaaSI interface.
* The pop-up should contain three interfaces, identified by tabs or some other menu format: the configuration change log, environment metadata, and object metadata
  * The change log allows users to input data about the configuration adjustments made while interacting with the environment. This information may be used by the system for search/discovery, automation, and administration. *See below for more details on the scope of the change log*
* Environment metadata displays a summary of the descriptive and technical information about the environment that is being altered.
* Object metadata displays a summary of the descriptive and technical information about the object(s) that were mounted in the environment for this session.
* Users should be discouraged from closing this window during their session and will need the option to relaunch the window from the main UI should they close it erroneously.

## Change Log

### MVP

* Users will be prompted to identify what software or content they configured in the environment
* The system could determine the software or content the user could configure in the environment based on the software/content associated with the object(s) mounted in their session.
* Entries in the change log should be recorded as part of the event record of the configuration session once the user has saved or revised the record.

**Example change log entry - MVP**

| Item | Property | Value |
| ------ | ------ | ------ |
| Environment | Software Configured | Corel WordPerfect 7 |
| Environment | Software Configured | Corel Quattro Pro 7 |
| Environment | Software Configured | Corel Presentations 7 |

### Later Iteration

* The change log must contain one recorded action in order to save the environment.
* Changes are compiled according to the component of the environment they are describing: operating system, operable software, base environment
* Available properties to edit are based on the component selected, see below

**Editable Properties**

| Item | Property | Definition | Controlled Vocab |
| --------- | --------- | --------- | --------- |
| Environment | OS Installed/Configured | Name of installed/configured OS |  |
| Environment | Software Installed/Configured | Name of installed/configured software |  |
| [Operating System Name] | DateTime | Date and time assigned to software |  |
| [Operating System Name] | Language | Language selected for use in software (primary language indicated in UI) | X |
| [Operating System Name] | User Account | Account type configured in operating system (Qualifiers: username, password, pin) |  |
| [Software Name] | Language | Language selected for use in software | X |
| [Software Name] | User information | Account type configured in software (Qualifiers: username, password, organization) |  |
| [Software Name] | Executable Syntax | Command required to execute software |  |
| [Software Name] | Executable Location | Path to location of software executable |  |
| [Software Name] | Save Location | Path to location where software saves outputs |  |
| [Software Name] | Default Readable Format | Read format implementation selected as default | X |
| [Software Name] | Default Writeable Format | Write format implementation selected as default | X |

_Old mock-ups of this feature can be found in the folder along with this proposal. These were designed according to the look of the WikiDP portal and may not be the design settled upon for EaaSI._

**Example change log entry**

**Example Config Documentation**

| Item | Property | Value |
| ------ | ------ | ------ |
| Environment | Software Installed | Corel WordPerfect Suite 7 |
| Corel WordPerfect 7 | Username | User |
| Corel WordPerfect 7 | Organization | Organization |
| Corel WordPerfect 7 | Executable Location | C:\Corel\Office7\WPWin7\WPWIN.EXE |
| Corel WordPerfect 7 | Save Location | C:\MyFiles |
| Corel WordPerfect 7 | Configured Language | Spanish |

## Environment Metadata

* In the environment metadata section of the pop-up, the user should see the following information:

| Section | Metadata Property | Example |
| --------------- | --------------- | --------------- |
| Hardware | Emulator (version) | QEMU v3.1 |
| Hardware | Architecture | x86 |
| Hardware | RAM | 512 |
| Hardware | CPU Cores | 1 |
| Operating Environment | OS Software (Language) | Windows 98 SE (English) |
| Operating Environment | Operable Software (Language) | Microsoft Word 97 (English) |

  *Operating environment section repeats if environment has more than one*
  
* Screenshots of the environment may also be displayed as reference of what the environment should look like in the emulator.

## Object Metadata

* In the object metadata section of the pop-up, the user should see the following information:

| Section | Metadata Property | Example |
| --------------- | --------------- | --------------- |
| Software | Related Software | Adobe Acrobat 3.0 |
| Object Part | Label (or filename if no label) | Disc 1 of 3  |
| Object Part | Physical Format | CD-ROM (maybe an icon?) |

* Photos of the environment may also be displayed as reference of what the environment should look like in the emulator.

# Open Questions
* How will pop up blockers interfere with this interface?
* What will the user experience be like on smaller monitors?
* Would users be expected to also have the WikiDP interface open to record details about software products?

# Answered Questions


