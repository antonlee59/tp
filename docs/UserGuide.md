---
layout: page
title: User Guide
---

Ultron is a **desktop app for compiling job and internship openings, optimized for use via a Command Line Interface** (CLI) while still having the benefits of a Graphical User Interface (GUI). If you are familiar with the Ultron interface, it can help you organise your openings in a structured manner. 

* Table of Contents
{:toc}

--------------------------------------------------------------------------------------------------------------------

## Quick start

Refer to the [Features](#features) below for details of each command.

_More details coming soon ..._


--------------------------------------------------------------------------------------------------------------------

## Features

<div markdown="block" class="alert alert-info">

**:information_source: Notes about the command format:**<br>

* Words in `UPPER_CASE` are the parameters to be supplied by the user.<br>
  e.g. in `outcome /o STATUS`, `STATUS` is a parameter which can be used as `outcome /o ongoing`.

* Parameters can be in any order.<br>
  e.g. if the command specifies `/n POSITION /c COMPANY`, `/c COMPANY /n POSITION` is also acceptable.

* If a parameter is expected only once in the command but you specified it multiple times, only the last occurrence of the parameter will be taken.<br>
  e.g. if you specify `p/12341234 p/56785678`, only `p/56785678` will be taken.

* Extraneous parameters for commands that do not take in parameters (such as `exit`) will be ignored.<br>
  e.g. if the command specifies `exit 123`, it will be interpreted as `exit`.

</div>

### Adding an opening : `add`

Adds a new opening to the list.

Format: `add /n POSITION /c COMPANY /s STATUS /d DEADLINE`

Examples:
* `add /n Software Engineer /c Google /s ongoing /d 2023-03-14`

### Listing all openings : `list`

Shows the whole list of openings, regardless of whether the opening is ongoing, successful or rejected.

Format: `list`

### Listing all opening outcomes : `outcome`

Shows the list of openings based on the opening status provided. 

Format: `outcome /o STATUS`

* Shows all openings with specified `STATUS`.
* The status **must be of either ongoing, successful or rejected**.

Examples:
`outcome /o ongoing` produces a list of ongoing openings.

### Locating openings by name: `find`

Finds openings whose NAME_OF_COMPANY contain any of the given keywords.

Format: `find KEYWORD [MORE_KEYWORDS]`

* The search is case-insensitive. e.g `google` will match `Google`
* The order of the keywords does not matter. e.g. `Goldman Sachs` will match `Sachs Goldman`
* Only the name is searched.
* Only full words will be matched e.g. `Amaz` will not match `Amazon`
* Openings with NAME_OF_COMPANY matching at least one keyword will be returned (i.e. `OR` search).
  e.g. `google amazon meta` will return `Google`, `Meta`, `Amazon Web Services`

Examples:
* `find Google` returns `google` and `Google Cloud`
* `find bank america` returns `Bank of America`, `Bank of Singapore`<br>
  <!--![result for 'find alex david'](images/findAlexDavidResult.png)-->

### Deleting a person : `delete`

Deletes the specified person from the address book.

Format: `delete INDEX`

* Deletes the person at the specified `INDEX`.
* The index refers to the index number shown in the displayed person list.
* The index **must be a positive integer** 1, 2, 3, …​

Examples:
* `list` followed by `delete 2` deletes the 2nd person in the address book.
* `find Betsy` followed by `delete 1` deletes the 1st person in the results of the `find` command.

### Deleting an opening : `delete`

Deletes an opening from the list.

Format: `delete INDEX`

* Deletes the opening at the specified `INDEX`.
* The index refers to the index number shown in the displayed opening list.
* The index **must be a positive integer** 1, 2, 3, …​

Examples:
* `list` followed by `delete 2` deletes the 2nd opening in the opening list.

### Exiting the program : `exit`

Exits the program.

Format: `exit`

### Saving the data

Ultron data are saved in the hard disk automatically after any command that changes the data. There is no need to save manually.

### Archiving data files `[coming in v2.0]`

_Details coming soon ..._

--------------------------------------------------------------------------------------------------------------------

## FAQ

_Details coming soon ..._

--------------------------------------------------------------------------------------------------------------------

## Command summary

Action | Format, Examples
--------|------------------
**Add** | `add /n POSITION /c COMPANY /s STATUS /d DEADLINE` <br> e.g., `add /n Software Engineer /c Google /s ongoing /d 2023-03-14`
**Delete** | `delete INDEX`<br> e.g., `delete 3`
**Outcome** | `outcome /o STATUS`<br> e.g., `outcome /o ongoing`
**List** | `list`
**Find** | `find KEYWORD [MORE_KEYWORDS]`<br> e.g., `find amazon google meta`
