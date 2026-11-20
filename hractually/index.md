# HR, Actually

The content contract for the **HR, Actually** website: what the files in
[`HRactually/hractually-data`](https://github.com/HRactually/hractually-data) must look like for the site to
read them. The site, `Cavatina-Solutions/client-hractually-site`, owns these schemas and validates against them
when it processes that repository; the data repository's own check, and any editor following a file's `"$schema"`
line, use the same published documents.

## Schemas

Each content file is one collection, wrapped in an object so it can carry its `"$schema"` line:

| Schema              | Content file                    | What it holds                                                  |
| ------------------- | ------------------------------- | -------------------------------------------------------------- |
| `verdicts`          | `content/verdicts.json`         | The short verdicts quoted on the home page.                    |
| `about`             | `content/about.json`            | The owner's pull quote, job title, bios and personal links.    |
| `social-links`      | `content/socialLinks.json`      | The site's own accounts.                                       |
| `linkedin-posts`    | `content/linkedInPosts.json`    | The LinkedIn posts the site shows.                             |
| `press-credentials` | `content/pressCredentials.json` | The press credentials the publication currently issues.        |
| `social-link`       | none                            | One link, shared by `about` and `social-links` through `$ref`. |

## Status

Stable. The site reads these as written, so the [versioning rules](../README.md#versioning) apply: a change that
would fail a file valid today goes to `v2`.
