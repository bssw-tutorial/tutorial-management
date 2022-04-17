# Tutorial Management

This repository is mostly issue-only, for the purposes of managing the activities of the BSSw tutorial team.  However it also includes data files and instructions to help keep things synchronized and connected across the multiple repositories within this organization that are part of the BSSw tutorial ecosystem.

## Organization-Level Project Board

* [management](https://github.com/orgs/bssw-tutorial/projects/1)

## Development Repositories

The following repositories are involved in the *development* of tutorial materials.  All of these repositories should use the same set of issue labels and milestones (see [Synchronizing Issues and Milestones](#synchronizing-issues-and-milestones)).  Most (all?) of the issues in these repositories should appear on the [Organization-Level Project Board](#organization-level-project-board).

* [bssw-tutorial.github.io](https://github.com/bssw-tutorial/bssw-tutorial.github.io)
* [hello-numerical-world](https://github.com/bssw-tutorial/hello-numerical-world)
* [presentations](https://github.com/bssw-tutorial/presentations)
* [tutorial-management](https://github.com/bssw-tutorial/tutorial-management)

## Student Repositories

Repositories named following the pattern `hello-numerical-world-YYYY-MM-DD-venue` following the same shorthand label used in the web site and in the presentations (for some older events `hello-numerical-world-YYYY-MM-venue`) are copies of `hello-numerical-world` made for each tutorial event.  The `.github/workflows` directory should be deleted in the student copy of the repository. This allows students in the tutorials to file issues and pull requests as part of the hands-on activities without turning the primary repository into a complete mess in the long term.

## Synchronizing Issues and Milestones

We use [github-sync-labels-milestones](https://www.npmjs.com/package/github-sync-labels-milestones) to keep the issues and milestones in the [Development Repositories](#development-repositories) synchronized. The file `master-labels-milestones.json` is the configuration file.  It needs to be updated for each new milestone.  We're currently using GitHub's default set of labels.

1. Update `master-labels-milestones.json`
    - Add milestone for new tutorial event.  This should be the same as the `event-label` used elsewhere, e.g., `YYYY-MM-DD-venue`
    - Update the state of any events which have already taken place
2. Get your GitHub [Personal Access Token](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) (shown as `<pat>` below)
3. Run `npx github-sync-labels-milestones -t <pat> -c master-labels-milestones.json -v`

## Synchronizing Actions

At present, the only GitHub Action used across all development repositories is `issues-to-project.yml` which automatically assigns all opened or reopened issues and PRs to the [Organization-Level Project Board](#organization-level-project-board).  It should be in `.github/workflows` in all repositories, and should be the same.
