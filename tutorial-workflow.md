# Tutorial Workflow

These are the steps generally necessary to prepare and deliver a specific tutorial event.

## Proposal

## Planning

* Finalize agenda
    - Need to know fixed points for schedule
        - Start
        - End
        - Coordinated breaks (if any)
* Finalize staffing
* Determine deadlines for preparations
    - Preliminary content drop for venue (if required)
    - Final versions of content from presenters
    - Final versions of hands-on instructions and code
    - Content drop for venue (if required)
* Make specific plans for content enhancements
    - In presentations
    - In hands-on activities and related code base
    - In web site
    - Review bug tickets that can/should be addressed
    - Review enhancement tickets that can/should be addressed
* Create issues to track preparation activities

## Preparation

* Update web site
* Update presentations
* Update master agenda slide
* Update master license slide
* Update individual presentations
    - Title slide
        - Presenter
        - Venue
        - Additional contributors (if appropriate)
    - License slide
* Update overview with agenda slide
* Generate PDFs
* Put PDFs in event directory
* Commit PDFs to presentations repository
* Create FigShare record for event, uploading PDFs
* Record DOI
    - In `presentations/final_presentations/<event>/doi.txt`
    - In web site metadata
* Create zip of PDFs
* Tag presentations repository for event
* Create GitHub release for the event, with zip of PDFs
* Tag web site repository
* Copy `hello-numerical-world` (as template) to event-specific repository