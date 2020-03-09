
This version of the report is a markdown copy. The information should be identical to the PDF, albeit with some potential format differences.

  

# Deliverable 2 Roles

  

The team member roles listed here are not “set in stone” and each team member will likely be helping with other tasks if needed. However these roles designate what each member will primarily be working on.



| Team Member | Role |
| --- | --- |
| Charmaine Yung | Documentation and flex developer (will help with both issues and third if time permits) |
| Austin Seto | Working on issue: Calendar Read-Only Bug |
| Julian He | Working on issue: Calendar Read-Only Bug |
| Lintao Yin | Working on issue: Attendee Multiple Copies |
| Mikhail Makarov | Working on issue: Attendee Multiple Copies |

  

# Discussed Issues

  

## Inability to Edit Remote Calendar

| Bugzilla ID | [315307](https://bugzilla.mozilla.org/show_bug.cgi?id=315307) |
| --- | --- |
| Title | remote calendar location cannot be edited in edit calendar/calendarProperties |
| Description | The location for saving Lighting calendars always reverts to default when it’s changed. It is likely that this occurs due to either a timing bug or unimplemented change in field in the calendar\base\content\dialogs\calendar-properties-dialog.js file |
| Work Estimate | 6 Hours |
| Status | Deprecated (Address of ICS imported Calendars are no longer editable and must be destroyed) |

  

## Calendar Read-Only Permission Bug

| Bugzilla ID | [1273793](https://bugzilla.mozilla.org/show_bug.cgi?id=1273793) |
| --- | --- |
| Title | added calendars could be set with "read only option" accordingly to its real permissions |
| Description | When a calendar property is readonly, the UI does not indicate as such, and still allows for editing. The change is not reflected in the backend. |
| Work Estimate | 10 Hours |
| Status | Selected |

  

## Attendee List Focus Mismatch

| Bugzilla ID | [1051572](https://bugzilla.mozilla.org/show_bug.cgi?id=1051572) |
| --- | --- |
| Title | Attendee Dialog: Focus mismatch when moving in attendee list |
| Description | In the attendee list dialog the selected (aka focused) attendee desyncs where the UI shows a non-selected attendee as selected while the actual selected one does not have the focused styles applied. Likely caused by some issues with array holding values and index specifying focus in the calendar-invitations-dialog.js |
| Work Estimate | 5 Hours |
| Status | ABANDONED (Could not replicate issue, arrow keys do not work for navigating Attendees) |

## Calendar HTML/CSS Template Improvements

| Bugzilla ID | [1594335](https://bugzilla.mozilla.org/show_bug.cgi?id=1594335) |
| --- | --- |
| Title | calMonthGridPrinter.html and calWeekPrinter.html should use \<html:template> and css for align/valign |
| Description | The files mentioned in the title use outdated HTML tags and properties. Update them using modern tags and CSS. Would have to go through all CSS and HTML files to change. More of a refactor request. Could potentially write script to fix but would then need to test extensively |
| Work Estimate | 22 Hours |
| Status | Not Selected (not relevant enough to users and too much menial labor) |

  

## Allow Access to Resource and Location Calendars

| Bugzilla ID | [481021](https://bugzilla.mozilla.org/show_bug.cgi?id=481021) |
| --- | --- |
| Title | Allow easy access to resource and location principals and calendars |
| Description | **This is a new feature that has been requested by a user.** A feature to allow booking/indication of rooms in a building in which an event is taking place. Note that in the description in the link, [Iceowl is another name for Lightning](https://en.wikipedia.org/wiki/Mozilla_software_rebranded_by_Debian#Iceowl). This would be generally nice to have feature. We would have to research how caldav handles resource/room calendars and see if we need to make any modification to Caldav import/export. Beyond that we would need to edit the create calendar dialog to support the creation of resource and room calendars as well as have indicators in the calendar properties dialog that the calendar is a resource/room calendar. Further extension of resource/room properties would be best left to further Change Requests due to a lack of time for the group to implement. |
| Work Estimate | 48 Hours |
| Status | Not Selected (task appears outside the scope of this deliverable, saved for deliverable 3) |

  

## Addresses are duplicated in attendee dialog box

| Bugzilla ID | [1596941](https://bugzilla.mozilla.org/show_bug.cgi?id=1596941) |
| --- | --- |
| Title | Addresses are duplicated when entered in the invite attendees dialog |
| Description | Create an event in a calendar that has no email set on it. Open the invite attendees dialog for the event. Enter an address in the list on the left and hit enter. The address appears twice. Hit enter again, it appears three times, etc. Seems to be an issue with how it adds elements to the list and how it delets elements in the list. Likely in the event dialog attendees file. |
| Work Estimate | 10 hours |
| Status | Selected (relevant to users, simple to test, good to prove understanding of logic) |

  

# Issues Worked On

## Calendar Read-Only Permissions Bug
Description: [See Above](#calendar-read-only-permission-bug)

Work Estimates:
* Analysis: 6 hour
* Acceptance Tests: 2 hours
* Implementation: 6 hours
* Verification: 1 hours
* Delivery: < 1 hours

### Checklist
- [ ] Review/Design - Analyze code and bug, update implementation section with further plans (2020/03/07 - ___)
- [ ] Acceptance Tests - Write tests for future verification stage
- [ ] Implementation - Writing and functional test of code
- [ ] TBD
- [ ] Verification - Run acceptance tests and verify passes
- [ ] Delivery - Pull Request

### Review Notes



### Tests Designed



### Other Developer Commentary



## Attendee List Focus Mismatch
Description: [See Above](#attendee-list-focus-mismatch)

Work Estimates:
* Analysis: 3 hours
* Acceptance Tests: 2 hours
* Implementation: 4 hours
* Verification: 1 hours
* Delivery: < 1 hours

### Checklist

- [X] Review/Design - Analyze code and bug, update implementation section with further plans (2020/03/05 - 2020/03/07)
- [ ] Acceptance Tests - Write tests for future verification stage
- [ ] Implementation - Writing and functional test of code
- [ ] TBD
- [ ] Verification - Run acceptance tests and verify passes
- [ ] Delivery - Pull Request

### Review Notes

Could not replicate issue, abandoned

### Tests Designed

### Other Developer Commentary

We couldn’t replicate the defect, arrows key inputs did not affect the attendee list at all

## Addresses are duplicated in attendee dialog box

Description: [See Above](#addresses-are-duplicated-in-attendee-dialog-box)

Work Estimates:

* Analysis: 4 hours
* Acceptance Tests: 2 hours
* Implementation: 4 hours
* Verification: 1 hours
* Delivery: < 1 hours

### Checklist
-  [X] Review/Design - Analyze code and bug, update implementation section with further plans (2020/03/07 - 2020/03/07)
-  [X] Acceptance Tests - Write tests for future verification stage (2020/03/07 - 2020/03/07)
- [ ] Implementation - Writing and functional test of code (2020/03/07 - ____)
- [ ] TBD
- [ ] Verification - Run acceptance tests and verify passes
- [ ] Delivery - Pull Request

### Review Notes

Bug appears as stated but also appears when pressing backspace.
Deleting when one character in attendee entry also creates a new row.
Bug Confirmed as such fix and acceptance test writing beginning

### Tests Designed

1. Create a calendar with no attached email address (local only)
2. Disable all other calendars
3. Create a new event
4. Go to invite attendees (insure there are no auto populated attendees)
5. Attempt to create a new row
	- Try backspace and delete
	- Try enter
	- Try filling out value and enter
6. Insure no extra rows are created
7. Save event, close and reopen, insure no duplicate rows
8. Attempt to create a new row
9. Repeat with Network Calendar

### Other Developer Commentary
