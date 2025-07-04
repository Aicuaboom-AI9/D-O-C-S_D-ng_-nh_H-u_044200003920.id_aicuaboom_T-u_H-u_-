---
title: Autolinked references and URLs
intro: 'References to URLs, issues, pull requests, and commits are automatically shortened and converted into links.'
product: '{% data reusables.gated-features.markdown-ui %}'
redirect_from:
  - /articles/autolinked-references-and-urls
  - /github/writing-on-github/autolinked-references-and-urls
  - /github/writing-on-github/working-with-advanced-formatting/autolinked-references-and-urls
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Auto linked references
---
## URLs

{% data variables.product.github %} automatically creates links from standard URLs.

`Visit https://github.com`

![Screenshot of rendered {% data variables.product.github %} Markdown showing how a URL is displayed as a blue clickable link, "Visit https://github.com."](/assets/images/help/writing/url-autolink-rendered.png)

For more information on creating links, see [AUTOTITLE](/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links).

## Issues and pull requests

Within conversations on {% data variables.product.github %}, references to issues and pull requests are automatically converted to shortened links.

> [!NOTE]
> Autolinked references are not created in wikis or files in a repository.

| Reference type | Raw reference | Short link |
| --- | --- | --- |
| Issue or pull request URL | https://github.com/jlord/sheetsee.js/issues/26 | [#26](https://github.com/jlord/sheetsee.js/issues/26)
| `#` and issue or pull request number | #26 | [#26](https://github.com/jlord/sheetsee.js/issues/26) |
| `GH-` and issue or pull request number | GH-26 | [GH-26](https://github.com/jlord/sheetsee.js/issues/26) |
| `Username/Repository#` and issue or pull request number | jlord/sheetsee.js#26 | [jlord/sheetsee.js#26](https://github.com/jlord/sheetsee.js/issues/26)
| `Organization_name/Repository#` and issue or pull request number | github-linguist/linguist#4039 | [github-linguist/linguist#4039](https://github.com/github-linguist/linguist/pull/4039)

{% ifversion fpt or ghec %}
If you reference an issue, pull request, or discussion in a list, the reference will unfurl to show the title and state instead. For more information about task lists, see [AUTOTITLE](/get-started/writing-on-github/working-with-advanced-formatting/about-task-lists).
{% endif %}

## Labels

When referencing the URL of a label in Markdown, the label is automatically rendered. Only labels of the same repository are rendered, URLs pointing to a label from a different repository are rendered as any [URL](/get-started/writing-on-github/working-with-advanced-formatting/autolinked-references-and-urls#urls).

The URL of a label can be found by navigating to the labels page and clicking on a label. For example, the URL of the label "enhancement" in our public [docs repository](https://github.com/github/docs/) is

```markdown
https://github.com/github/docs/labels/enhancement
```

> [!NOTE]
> If the label name contains a period (`.`), the label will not automatically render from the label URL.

## Commit SHAs

References to a commit's SHA hash are automatically converted into shortened links to the commit on {% data variables.product.github %}.

| Reference type | Raw reference | Short link |
| --- | --- | --- |
| Commit URL | [`https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e`](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e) | [a5c3785](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e) |
| SHA | a5c3785ed8d6a35868bc169f07e40e889087fd2e | [a5c3785](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e) |
| User@SHA | jlord@a5c3785ed8d6a35868bc169f07e40e889087fd2e | [jlord@a5c3785](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e)
| `Username/Repository@SHA` | `jlord/sheetsee.js@a5c3785ed8d6a35868bc169f07e40e889087fd2e` | [`jlord/sheetsee.js@a5c3785`](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e) |

### Troubleshooting referencing commit SHAs

When referencing a commit from a private repository inside of a commit message, the commit SHA will only be shortlinked if at least one of the authors or committers of the commit have at least read access to the referenced commit.

## Custom autolinks to external resources

{% data reusables.repositories.autolink-references %}

## Avoiding backlinks to linked references

By default, references generate a backlink. For example, manually linking to an issue in a pull request will automatically generate another link from the issue *back* to the pull request.
To avoid this behavior, you can use `redirect.github.com` instead of `github.com` when constructing the URL in your reference. If you do use a `redirect.github.com` URL in your reference link, no pop-up window will appear when hovering over it.

## Further reading

* [AUTOTITLE](/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
