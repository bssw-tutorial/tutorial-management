# Using the Agenda Spreadsheet

We’ve used Google spreadsheets for some time to plan agendas.  But since SC21, we’ve developed a more sophisticated spreadsheet that is (a) more helpful in calculating the timeline for the agenda, and (b) after being exported to CSV format, it can used directly in the bssw-tutorial.github.io website to provide the agenda displayed on the event web page.  This simplifies creating the site and reduces the opportunities for errors.

## Getting Started

The simplest way to proceed is to copy an existing `agenda` spreadsheet to the new event folder.  Obviously, starting from a prior event that has a similar structure and schedule is likely to be simplest, but any copy can be adapted.  As noted above, we started using this spreadsheet structure for SC21 (`2021-11-sc21-bssw-tutorial` in Google Drive).

You might find it useful to have a copy of the spreadsheet for *planning* purposes (proposal development), and then a *separate* copy in which to finalize the agenda after acceptance.  This allows you to retain a copy that is consistent with the proposal to avoid confusion when referencing past events for new tutorial proposals.

## Key Points for Agenda Planning

* **`Fixed Points`** (usually column A) should be populated with the fixed points in the schedule -- start and end times, as well as mandatory breaks.  
  * When moving around items on the agenda, make sure the fixed points remain where they’re supposed to be.
* **`Duration`** (column B) is the duration in minutes of each module.  You should change these entries to suit.
* **`Time (<timezone>)`** (column C) is *calculated* from the start time (cell A1) and the durations (column B).  
  * Make sure you have the formulas here, not values.
  * Note that the formula for C3 is different from the rest.
  * This column has conditional formatting to highlight where the timeline does not line up with the fixed points in column A.
* In some cases, additional columns may have been added, for example to provide information in another timezone.  These added columns may result in the columns referenced above shifting.  The additional columns may use/adapt some of the formulas of the above columns.

## Key Points for Use on the bssw-tutorial.github.io Website

* **Row 1** are the headings that will appear in the HTML rendering of the agenda (subject to `<!--skip-->` instructions in row 2).
  * Make sure the proper time zone for the event is specified in C1
  * One column should be headed `Title` (details below)
  * One column should be headed `Presenter` (details below)
  * Other columns may be added as needed
    * For example, it is sometimes useful to have a second time zone, where the event time zone is far from the presenter time zones, to reduce conversion errors. See, for example,  [https://bssw-tutorial.github.io/2021-06-24-isc/#agenda](https://bssw-tutorial.github.io/2021-06-24-isc/#agenda) (though this was not done with the spreadsheet per se).
* **Row 2** controls the formatting of the agenda when rendered in HTML.  Cells should either contain structured HTML comments or they should be empty.
  * `<!--skip-->` indicates that the column should not be included in the HTML rendering.
  * `<!--left-->`, `<!--center-->`, `<!--right-->` indicate the alignment of the columns.
  * Empty cells give the default alignment
* The **remaining rows** are treated as agenda items, to be rendered as described here.
* The **`Title` column** cells should contain the pre-defined presentation labels for presentations, or text to be rendered directly.  Cells may be empty.
  * The mapping of shorthand presentation labels to full titles is defined in a separate `presentations.yml` spreadsheet which is provided to the website as a .yml (not .csv) file.
  * Shorthand labels will be replaced with the full titles in the HTML rendering
  * Cells containing presentation labels should contain nothing else
  * Cells not containing recognized shorthand labels are treated as text to be copied directly into the HTML rendering.  This is typically used for hands-on segments, breaks, adjournment time, etc.  Empty cells are okay.
    * Special formatting should use HTML markup (not Markdown).  
    * By convention, we use `<em>` markup to denote breaks and other non-content elements of the agenda.
* The **`Presenter` column** cells should either contain GitHub IDs which can be matched in the website’s `_people` collection or should be empty.
  * GitHub IDs are mapped into names and affiliations (short form) based on the data in the `_people` collection of the website.
  * The ability to have other content rendered directly in HTML, as with the `Title` column, might be a useful enhancement.
* The **`Module` column** is used to indicate the sequence numbers used so that the presentation slides and such sort in order. 
  * Cells should be left blank for items that are not presentations. 
  * The user of the spreadsheet is responsible for ensuring that the numerical sequence is correct.  
  * The bssw-tutorial website machinery will generate helper scripts to prepare the presentations for release which use the data in this column to rename the PDF files.

## Mapping Presentation Labels to Titles

In the `agenda` spreadsheet, shorthand presentation labels are used in the `Title` column.  In the web site, the mapping of presentation labels to full titles is provided in the `_data/bsswt/<event-label>/presentations.yml` file.  This file is tracked in the `bssw-tutorial/presentations` repository.  It should be updated any time new presentations are added or titles are changed, and the current version for each tutorial should be copied to the appropriate location in the `bssw-tutorial/bssw-tutorial.github.io` repository as part of the process of adding the agenda to the web site.