# Website Environments

Most Varbase sites run in more than one copy, called environments. Knowing which copy you are working in keeps your content from being lost or published by mistake. This page explains the usual environments and how to work across them.

## Types of Environments

### Development

Where developers build and test new features.

- Usually open to the development team only.
- Changes often, and its content can be replaced at any time.
- **Do not enter real content here.** It may be overwritten.

### Staging

A close copy of the live site, used to check changes before they go live.

- Open to the project team, testers and reviewers.
- Used for review, user acceptance testing and approvals.
- Its database is often refreshed from the live site, which replaces what was entered on staging.

Use staging to try a workflow or check how a page looks, then do the real work on the live site unless your team says otherwise.

### Production

The live site that visitors see.

- The one place where final content belongs.
- Backed up regularly.
- Changes here are public as soon as they are published.

## Working Across Environments

1. **Enter final content once**, on the environment your team names (usually production).
2. **Ask when the databases are copied.** A copy from production to staging replaces staging content, and the other way round is rare and planned.
3. **Save as a draft first.** Use the content workflow so nothing half finished goes live. See [Content Workflow](../content-workflow/).
4. **Tell your team** what you are working on, so two people do not edit the same item in two places.

## Knowing Where You Are

Check the address bar: each environment has its own web address, for example `staging.example.com` and `www.example.com`. Your team may also show the environment name in the site name or in a coloured label at the top of the page. If you are not sure, ask before you publish.

## Tips

- Bookmark the login page of each environment with a clear name, such as "Staging, do not publish".
- Before a large content task, confirm with your team that no database copy is planned that day.
