---
title: "Week 9/10 GitHub Pages Workshop"
subtitle: "Web Presentation, Accessibility, and Sustainability"
author: "HIST 501D - Digital History"
date: "April 7, 2026"
---

# Overview

This workshop prepares students to build the GitHub Pages assignment that follows the web presentation unit. It assumes students have already completed earlier assignments in data cleaning, visualization, scraping, mapping, and network analysis and now need to turn one or more of those outputs into a public-facing project site.

The intellectual frame for this class comes from four linked ideas in the readings:

1. interface is part of the scholarly argument, not decoration
2. a well-designed interface does two things: it *reveals* contents and *guides users toward actions* — both must be planned before coding begins
3. the built site is a mockup, not a finished product — it documents the design process and establishes a foundation for later development
4. web platforms shape what kinds of work users can find and understand
5. sustainability and preservation should be considered while building, not after the fact

# Learning Objectives

By the end of this 120-minute workshop, students should be able to:

1. distinguish between a project repository and a public-facing project website
2. create or enable a GitHub Pages site
3. build a small multi-page site with clear structure and navigation
4. embed or link to a prior course visualization in a meaningful way
5. make basic accessibility and usability improvements
6. describe how a static site supports sustainability and future project development

# Materials

Students should have access to:

1. a GitHub repository for their course work or project
2. at least one visualization from an earlier assignment
   - visualization image or interactive chart
   - map output
   - network image
   - cleaned dataset excerpt
   - OCR or scraped material
3. VS Code and GitHub access

# Framing Points for Opening Discussion

Use these ideas to open the workshop:

1. A project website is not just a container. It is an argument about what matters, in what order, and for whom.
2. A static site is often a good fit for scholarly work because it is legible, lightweight, and easier to preserve.
3. A good DH site does not need to be technically elaborate. It needs to be clear, navigable, and intellectually responsible.
4. The question is not "how much can I put on the web?" but "what should a visitor understand after five minutes on the site?"

# 120-Minute Plan

## 1. Opening and Framing - 10 minutes

Briefly connect the workshop to the readings and assignment.

Key questions:

1. Who is the audience for your site?
2. What should a visitor understand first?
3. What visualization from an earlier week is worth making public?

## 2. Model Review - 10 minutes

Open the course demo site first: [https://bds134.github.io/dh-demo/demo-site/index.html](https://bds134.github.io/dh-demo/demo-site/index.html)

This is the scale students are building toward — a minimal, readable, four-page static site. Walk through the home page briefly, then switch to the four DH project sites from Exercise 10.2 in the Drucker reading.

1. [China Unofficial Archives](https://minjian-danganguan.org/)
2. [The George Eliot Archive](https://georgeeliotarchive.org/)
3. [The Iraqi Jewish Archive](https://ijarchive.org/s/iraqi-jewish-archive/page/home)
4. [Real Face of White Australians](https://www.realfaceofwhiteaustralia.net/)

For each site, ask students to answer the two questions from the Drucker reading:

1. What does the site *reveal* — what can a visitor find here?
2. What does the site *guide* users to do — what actions does the interface support?

Note the range: the Iraqi Jewish Archive is a directed narrative (panels with arrows); the George Eliot Archive is a dense repository; the China Unofficial Archives uses absence of decoration as an argument. None of them are technically elaborate. All of them make a clear intellectual claim through interface decisions.

The point to land: interface is not decoration added at the end. It is the argument made visible.

## 3. Interface Sketch Activity - 15 minutes

Before any coding, students sketch their site on paper.

Instructions:

1. Take one sheet of paper per page you plan to build
2. Sketch boxes and labels showing where navigation, headings, content sections, and your visualization will appear
3. Label each region: what does it *reveal*? what does it ask a visitor to *do*?
4. Sketch at least three pages: Home, Planning, Findings, Sustainability
5. Take a photo of each sketch — these images will go into your repository and your Planning page

Circulate and ask:

1. What does a visitor see first on the home page?
2. Where is the visualization on the findings page — how prominent is it?
3. What does the navigation tell a visitor about what the site contains?
4. Does the sustainability page look like an afterthought or like an intentional part of the site?

This step follows Drucker's point that a schematic sketch of the interface is one of the first steps in the planning process, and should precede any technical decisions.

## 4. Demo: Minimal GitHub Pages Site - 20 minutes

Instructor demo should cover:

1. repository structure for a small site
2. `index.html` as homepage
3. adding a second and third page
4. linking pages through a nav bar
5. enabling GitHub Pages
6. checking the live URL

Recommended demo structure:

1. `index.html`
2. `planning.html`
3. `findings.html`
4. `sustainability.html`
5. `style.css`
6. `assets/` folder for images, interface sketch photos, or data excerpts

If desired, show Jekyll only as an optional path for students who want templating or blogging features.

## 5. Hands-On Build Phase I - 20 minutes

Students create the basic shell of the site, working from their interface sketches.

Checkpoint:

1. homepage created, matching their interface sketch layout
2. planning page created with interface sketch photos uploaded to `assets/`
3. findings page and sustainability page stubs created
4. nav links working across all pages
5. Pages publishing enabled or in progress

## 6. Hands-On Build Phase II - 20 minutes

Students add one prior-course visualization and contextualize it.

Prompt them to include:

1. what the visualization is
2. what data or sources produced it
3. what a viewer should notice
4. what the visualization cannot show on its own

Also prompt them to add initial content to the sustainability page:

1. what platform and tools they are using
2. what files are essential to the site

## 7. Accessibility and Usability Pass - 10 minutes

Students review their site for:

1. heading order
2. alt text on all images (including interface sketch photos)
3. readable fonts and contrast
4. whether a first-time visitor can tell what the project is about

Have them test each other's sites quickly in pairs if time permits.

## 8. Git Workflow and Next Steps - 10 minutes

Show the workflow students will use after class:

1. commit and push updates
2. continue revising through the week
3. submit live URL by April 13
4. prepare for peer review and sustainability document

For 4-credit students, explicitly connect this site to later project prototype expectations.

## 9. Wrap-Up - 5 minutes

Have students leave class with:

1. interface sketches photographed and in the repository
2. a live or nearly live site URL
3. a clear list of missing pieces to finish before the deadline
4. one next technical task and one next interpretive task

# Suggested Instructor Demo Talking Points

## Why Static?

1. fewer moving parts
2. easier to understand
3. easier to preserve
4. good fit for student projects and scholarly portfolios

## Why Not Just Upload a Notebook?

1. notebooks are for process and analysis
2. websites are for presentation and communication
3. a public visitor needs framing, interpretation, and structure

## What Makes a Weak Site?

1. only a title and a picture
2. visual without interpretation
3. methods hidden or absent
4. no indication of data provenance
5. confusing navigation

## What Makes a Strong Site?

1. clear purpose within seconds
2. concise writing
3. meaningful visualization placement
4. transparent methods and sources
5. design choices that support reading rather than distract from it

# Assessment Connection

This workshop prepares students for a three-part assignment sequence:

1. public GitHub Pages website
2. peer review of another student's site
3. short sustainability document

For 2-credit students, the GitHub Pages site is the endpoint.

For 4-credit students, the site should become part of the project's ongoing public-facing component and feed into the MVP/prototype and later documentation work.

# Suggested Homework Reminder

Before leaving class, remind students to finish:

1. homepage text
2. methods/data explanation
3. at least one embedded visualization with interpretation
4. repository link and credits
5. accessibility check

# Optional Extension Path

If a student finishes early or already has a working site, they can:

1. use Jekyll instead of plain HTML
2. add a project blog/update page
3. create a reusable site template for later project work
4. add a simple peer feedback form or contact page
5. draft the sustainability page early