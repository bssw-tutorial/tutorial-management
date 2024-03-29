# Create Hands-On Code Repository for the Event

We create a fresh copy of the hands-on code repository for each tutorial event.  This allows us to maintain the archival copies of the repository for each event while allowing he parent repository to evolve without concern to "polluting" it development artifacts.  It also allows tutorial participants to file issues and PRs against he event-specific repository as part of their explorations without "polluting" the parent repository.

The process is simple.  The parent repository, `bssw-tutorial/hellow-numerical-world` is setup in GitHub as a *template* repository.  Initiate the event-specific copy by clicking the green **Use this template** button at the top of the file listing in the Code view of the repository.

The owner for the new copy will default to your personal space.  This needs to be changed to the **bssw-tutorial** organization.  For the repository name use **`hello-numerical-world-<event-label>`**. For the description, use text along the lines of `Hands-on code repository for <event-date> <event-title> @ <venue>`.  And make sure the visibility is set to **public**.

Once the event-specific repository is created, you should delete the workflow files from it (*not* from the parent).  The workflows we use in the parent repository are not just irrelevant for the student experience, but they'll cause problems.  The easiest way to do this is to use the repository file list view in the browser to move into the **`.github/workflows/`** directory, click the **ellipsis menu** at the top right of the file list, and select **Delete directory**.  Then commit the change.

You will want to add the "NWO" (GitHub shorthand for repository name with organization) to the website `_data/bsswt/<event-label>/artifacts.yml`