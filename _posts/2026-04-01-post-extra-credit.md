---
title: "[Extra Credit] EcStatic Magic: Making Static Sites for DH Projects"
date: 2026-03-31T15:34:30-04:00
categories:
  - blog
tags:
  - extra credit
  - static sites
  - DH projects
  - Jekyll
  - GitHub Pages
---

# EcStatic Magic: What I Learned About Static Sites for Digital Humanities

**Event:** EcStatic Magic: Static Sites for DH Projects
**Date/Time:** March 31, 2026, 9:30 PM - 11:00 PM
**Location:** Online [Zoom]

---

## Static vs. Dynamic: The Basics

Most people use the internet every day without thinking about what kind of site they are actually looking at. The websites we see can broadly be divided into two categories: dynamic and static.

Dynamic sites, like WordPress, Squarespace, or Omeka, generate a fresh page every time someone visits. They pull from databases, run server-side code, and do a lot of work behind the scenes. Static sites do none of that. They are just pre-built HTML files. No database. No live generation. What you see is what was built ahead of time.

Static sites are faster because there is nothing to compute on the spot. They are more secure because there is no database to attack. They are easier to preserve because they do not depend on other things to stay compatible. The presenter made a point that landed: the [Space Jam 1996 website](https://www.spacejam.com/1996/) still works perfectly. Countless dynamic sites from the same era are gone. Static sites outlast the platforms that dynamic sites depend on.

There is also an environmental argument. Pre-built, smaller sites consume less energy than sites that require constant server processing. I had not thought about the carbon footprint of websites before this. It makes sense when you think about it.

![Screenshot of the workshop with space jam site](../../assets/images/ec_spacejam.png)
*Figure 1: An example of a static site.*

---

## The Tools

The workshop walked through three main tools. They work together.

**[Jekyll](https://jekyllrb.com/)** is a static site generator. You write content in Markdown, a simple plain-text formatting syntax, and Jekyll converts it into a full website. You do not need to write HTML by hand. You pick a theme or template and customize from there. The presenter showed his own [personal site](https://prithvidineshchandra.github.io). It looks professional. It took far less code than one would expect to build a site like that. It does simplify the process of building a website.

**[CollectionBuilder](https://collectionbuilder.github.io/)** is a set of Jekyll-based templates made specifically for digital humanities collection websites. It was developed by the University of Idaho Library. You bring images, documents, audio recordings, or something else, and CollectionBuilder turns that data into a browseable, searchable site with timelines, maps, and subject visualizations built in. One of the examples shown was [Runakunaq Bibliotecanku](https://lib-static.github.io/), a People's Library focused on Quechua and Andean materials, built by Alía Warsco, who originally developed these workshop slides.

**[GitHub Pages](https://pages.github.com/)** is where you host it all, for free. Your site lives in the same GitHub repository as your project files, and updating it is as simple as pushing a change. It is designed exactly for this kind of work. It allows you to easily host and update your site without having to worry about the technical details.

---

## Tutorials and Resources Shared at the Event

The presenter shared several starting points for anyone who wants to try this:

- [Try CollectionBuilder](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/) — the documentation for CollectionBuilder
- [Explore Static DH Projects](https://lib-static.github.io/) — examples of what people have actually built with these tools
- [Explore Jekyll Themes](https://jekyll-themes.com/) — a gallery of themes to start from

For going deeper these resources were listed on the slides:

- [The Programming Historian](https://programminghistorian.org/) — peer-reviewed tutorials on digital methods, including several on Jekyll and static sites
- [NYU DH LibGuide](https://guides.nyu.edu/digital-humanities) — NYU Libraries' guide to digital humanities tools and resources
- [Lib-Static community](https://lib-static.github.io/) — the broader practice of static web tools in libraries and DH
- [Minimal Computing Group](https://go-dh.github.io/mincomp/) — a community exploring low-resource approaches to digital scholarship
- [Jekyll step-by-step setup guide](https://jekyllrb.com/docs/step-by-step/01-setup/)
- [GitHub Pages getting started guide](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [CollectionBuilder metadata documentation](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/)

![Resources shared during the workshop](../../assets/images/ec_resources.png)
*Figure 2: Resources shared during the workshop.*

---

## How This Connects to the Course

We already use a static site for this course. Every assignment, every response, lives on a GitHub Pages site. Understanding the logic behind it changes how I think about the work. Also the exposure to additional themes and tools has deepened my understanding of the possibilities of static sites. It has also given me ideas for my own projects.

The concepts covered in the workshop are more like a tool that is an improvement on how we can document things. It makes our work more accessible and shareable. It also makes it more durable and easier to update. It is clear to see how these tools would be useful for a variety of projects.

---

## Where I Think I Can Use This

The most immediate thing is a personal portfolio site. Jekyll and GitHub Pages make it straightforward to put writing samples, project documentation, and a CV somewhere accessible and professional-looking.

Beyond that, there is something genuinely interesting about writing research papers as static sites rather than documents. A site can have interactive maps, embedded timelines, searchable data. We can add a demo readers can engage with in the form of iframes or embedded videos. For a research project with a real digital component, that matters.

For a capstone project involving archival research or a digital collection, CollectionBuilder seems like the natural choice. The metadata-driven approach is exactly how archivists think about describing objects. It would not require learning something entirely new. It would just be applying the same logic to a different output.

And the environmental point stuck with me. If static sites use meaningfully less energy than dynamic ones, that is a reason to prefer them as a default whenever a database is not actually necessary.

---
READY FOR GRADING.