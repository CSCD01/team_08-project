This version of the report is a markdown copy. The information should be identical to the PDF, albeit with some potential format differences. 

# Deliverable 2 Roles

The team member roles listed here are not “set in stone” and each team member will likely be helping with other tasks if needed. However these roles designate what each member will primarily be working on. 

| Team Member | Role |
| --- | --- |
| Charmaine Yung | Documentation and flex developer (will help with both issues and third if time permits) |
| Austin Seto | Working on issue: Calendar Read-Only Bug |
| Julian He | Working on issue: Calendar Read-Only Bug |
| Lintao Yin | Working on issue: Focus Mismatch |
| Mikhail Makarov | Working on issue: Focus Mismatch |

# Discussed Issues

## Inability to Edit Remote Calendar

| | |
| --- | --- |
| Bugzilla ID | [315307](https://bugzilla.mozilla.org/show_bug.cgi?id=315307) |
| Title | remote calendar location cannot be edited in edit calendar/calendarProperties |
| Description | The location for saving Lighting calendars always reverts to default when it’s changed. |
| Status | Not Selected (will work on if time permits) |

## Calendar Read-Only Permission Bug

| | |
| --- | --- |
| Bugzilla ID | [1273793](https://bugzilla.mozilla.org/show_bug.cgi?id=1273793) |
| Title | added calendars could be set with "read only option" accordingly to its real permissions |
| Description | When a calendar property is readonly, the UI does not indicate as such, and still allows for editing. The change is not reflected in the backend. |
| Status | Selected |

## Attendee List Focus Mismatch

| | |
| --- | --- |
| Bugzilla ID | [1051572](https://bugzilla.mozilla.org/show_bug.cgi?id=1051572) |
| Title | Attendee Dialog: Focus mismatch when moving in attendee list |
| Description | In the attendee list dialog the selected (aka focused) attendee desyncs where the UI shows a non-selected attendee as selected while the actual selected one does not have the focused styles applied |
| Status | Selected |

## Calendar HTML/CSS Template Improvements

| | |
| --- | --- |
| Bugzilla ID | [1594335](https://bugzilla.mozilla.org/show_bug.cgi?id=1594335) |
| Title | calMonthGridPrinter.html and calWeekPrinter.html should use \<html:template> and css for align/valign |
| Description | The files mentioned in the title use outdated HTML tags and properties. Update them using modern tags and CSS. |
| Status | Not Selected (not relevant enough to users) |

## Allow Access to Resource and Location Calendars

| | |
| --- | --- |
| Bugzilla ID | [481021](https://bugzilla.mozilla.org/show_bug.cgi?id=481021) |
| Title | Allow easy access to resource and location principals and calendars |
| Description | **This is a new feature that has been requested by a user.** A feature to allow booking/indication of rooms in a building in which an event is taking place. Note that in the description in the link, [Iceowl is another name for Lightning](https://en.wikipedia.org/wiki/Mozilla_software_rebranded_by_Debian#Iceowl). |
| Status | Not Selected (task appears outside the scope of this deliverable, saved for deliverable 3) |

# Issues Worked On

## Calendar Read-Only Permissions Bug

Description: [See Above](#calendar-read-only-permission-bug)

Work Estimates:

* Analysis: 6 hours
* Acceptance Tests: 2 hours
* Implementation: 6 hours
* Verification: 1 hours
* Delivery: < 1 hours

### Checklist

- [x] Review/Design - Analyze code and bug, update implementation section with further plans (2020/03/07 - 2020/03/08)
- [x] Acceptance Tests - Write tests for future verification stage (2020/03/08 - 2020/03/09)
- [ ] Implementation - Writing and functional test of code (2020/03/09 - ___)
    - [x] Pull data regarding user permissions from CalDav server during calendar retrieval (2020/03/10)
    - [ ] Set calendar permissions according to permissions read
- [ ] Verification - Run acceptance tests and verify passes
- [ ] Delivery - Pull Request

### Review Notes

* (2020/03/08) Austin and Charmaine successfully recreated issue using Google CalDav servers
* (2020/03/09) Austin and Julian analyzed code and found changes only had to be made in file "calendar/providers/caldav/calDavCalendar.js", specifically in the calDavCalendar prototype. 
* (2020/03/11) Austin and Charmaine found during implementation that setting the property mReadOnly for the calendar doesn't seem to have an effect. As well oddly there appears to be inconsistency in the readOnly property of the calDavCalendar. The functions within the calDavCalendar appear to use a property named "mReadOnly" but its observer tries to modify a property named "readOnly", with the front end also appearing to read a property called "readOnly", this is somewhat confusing. 

### Tests Designed

These are manual tests

#### Pull editable calendar

1. Set up calendar on CalDav server and give user edit permissions
2. Open Thunderbird Calendar and add previously created calendar using CalDav
3. Open newly created calendar
4. Check to see if the local calendar is editable

#### Pull read-only calendar

1. Set up calendar on CalDav server and give user read permissions only
2. Open Thunderbird Calendar and add previously created calendar using CalDav
3. Open newly created calendar
4. Check to see if the local calendar is not editable, it should have a lock symbol or similar to indicate this

### Other Developer Commentary

(Austin) Regarding automated testing I am not sure how automated tests would be written. What CalDav server would be used? How can we ensure its integrity? I know I definitely wouldn't be using my personal Google account's calendars (what I used to replicate the issue) but I don't know what other CalDav server I would use. 

(Austin) Asked Prantar about testing and was told mock objects could work but would be overkill and manual testing was okay.

## Attendee List Focus Mismatch

Description: [See Above](#attendee-list-focus-mismatch)

Work Estimates:

* Analysis: 3 hours
* Acceptance Tests: 2 hours
* Implementation: 4 hours
* Verification: 1 hours
* Delivery: < 1 hours

### Checklist

- [ ] Review/Design - Analyze code and bug, update implementation section with further plans (2020/03/05 - ___)
- [ ] Acceptance Tests - Write tests for future verification stage
- [ ] Implementation - Writing and functional test of code
    - [ ] TBD
- [ ] Verification - Run acceptance tests and verify passes
- [ ] Delivery - Pull Request

### Review Notes

### Tests Designed

### Other Developer Commentary
