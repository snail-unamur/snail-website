# SNAIL website

[![Netlify Status](https://api.netlify.com/api/v1/badges/f3d3682d-9ae5-4efa-85d7-2c9943bca46f/deploy-status)](https://app.netlify.com/sites/snail-unamur/deploys)

_[**Wowchemy**](https://wowchemy.com) makes it easy to create a beautiful website for free. Edit your site in Markdown, Jupyter, or RStudio (via Blogdown), generate it with Hugo, and deploy with GitHub or Netlify. Customize anything on your site with widgets, themes, and language packs._

- 👉 [**Get Started**](https://wowchemy.com/templates/)
- 📚 [View the **documentation**](https://wowchemy.com/docs/)
- 💬 [Chat with the **Wowchemy community**](https://discord.gg/z8wNYzb) or [**Hugo community**](https://discourse.gohugo.io)
- 🐦 Twitter: [@wowchemy](https://twitter.com/wowchemy) [@GeorgeCushen](https://twitter.com/GeorgeCushen) [#MadeWithWowchemy](https://twitter.com/search?q=(%23MadeWithWowchemy%20OR%20%23MadeWithAcademic)&src=typed_query)
- 💡 [Request a **feature** or report a **bug** for _Wowchemy_](https://github.com/wowchemy/wowchemy-hugo-modules/issues)
- ⬆️ **Updating Wowchemy?** View the [Update Guide](https://wowchemy.com/docs/update/) and [Release Notes](https://github.com/wowchemy/wowchemy-hugo-modules/releases)

## Adding elements to the SNAIL Website

### Team members

Team members are listed in [content/authors/](content/authors/). Each team member has its own subdirectory, corresponding to their **firstname-lastname**. *Please use this identifier of the members of the team (i.e., firstname-lastname) instead of their full name when encoding authors for publications, projects, and news to ensure proper linking on the website.*

Each user must be part of one of the following user groups (`user_groups:` in the `_index.md` of the user):
- Faculty
- Researchers
- PhD Students
- MSc Students
- Alumni

More groups can be added in the [content/people/people.md](content/people/people.md) file.

Check [Wowchemy documentation](https://wowchemy.com/docs/content/authors/) to know more about profiles content.


Hugo command to add a team member:

```
hugo new --kind authors authors/eid
```

### Projects

Projects are listed in [content/project/](content/project/). Each project has its own subdirectory, which respects the format:

- `msc-firstname-lastname` for master thesis projects. Those projects **must** include the following tags to ensure proper rendering:
```
tags:
  - Msc Thesis
  - (Finished|Ongoing)
```

- `phd-firstname-lastname` for PhD thesis projects. Those projects **must** include the following tags to ensure proper rendering:
```
tags:
  - PhD Thesis
  - (Finished|Ongoing)
```

- `project-id` for (funded) research projects that are not PhD thesis projects (like FRIA or FNRS scholarships). Those projects **must** include the following tags to ensure proper rendering:
```
tags:
  - Funded
  - (Finished|Ongoing)
```

Hugo command to add a project:

```
hugo new --kind project project/msc-firstname-lastname
```

### Publications

Publications are available in [content/publication/](content/publication/). Each publication has its own subdirectory, corresponding to the key `first author's last name-year`, followed by a letter if multiple publications have been accepted on the same year. Each folder should contain:

- `index.md` contains the information about the publication, following the format detailed at [https://wowchemy.com/docs/content/publications/](https://wowchemy.com/docs/content/publications/).

- `cite.bib` contains the reference to the publication in Bibtex format.

- `featured.(png|jpg)` is a figure used as a preview of the paper, displayed before the abstract.

Alternatively, one can use the [Hugo Academic CLI](https://github.com/wowchemy/hugo-academic-cli/) tool to automatically import publications from BibTeX. Please make sure that the Bibtex key follows the `first author's last name-year` format before the import (or you will have to rename all the folders manually).

Hugo command to add a publication:

```
hugo new --kind publication publication/lastname-2020
```

### Posts and news

News are available in [content/post/](content/post/). Each news has its own subdirectory respecting the format `year-month-day-id`. Check the documentation on blog posts at [https://wowchemy.com/docs/content/blog-posts/](https://wowchemy.com/docs/content/blog-posts/).

Hugo command to add a news:

```
hugo new --kind post post/2020-10-08-mynews
```

### Checklist before commit

Please check before comiting your changes that:

- authors of the SNAIL team  have been added using their identifier, corresponding to the name of the folder [content/author/](content/author/) (for example, `xavier-devroey` or `benoit-vanderose`), to ensure proper referencing on the website.

- the tags you used make sense and are consistent with the existing tags. Have a look at the list available on the [SNAIL website](https://snail.info.unamur.be/tags/) or add you own tags for new research topics.   

- the projects linked to the publication or post have been properly referenced. For instance, if the publication is part of a master or phd thesis, add the reference to the list of projects
```
projects:
  - mscthesis-xyz
```
