# Hands-On Exercise: Build the First Version of Your Project Website

**Course:** HIST 501D Digital History  
**Date:** Tuesday, April 7, 2026  

## Goal

During class, build the first working version of a public-facing GitHub Pages site for your project or course work.

By the end of class, you should have:

1. a repository connected to GitHub Pages
2. a homepage and at least two additional pages
3. one prior-course visualization embedded or linked with explanation
4. a live site URL

After class, you will continue to revise and expand the site for the formal deadline on Monday, April 13 at 9:00 AM. The in-class goal is to get a working shell of the site up and running so you can keep testing and revising it as you add content and polish the design. Importantly, you will create hand-drawn interface sketches for homework after class that will inform the next round of revisions. These sketches will be included and explained on the Planning page of your site.

## Recommended Site Structure

Create these files:

1. `README.md`
2. `index.html`
3. `planning.html`
4. `findings.html`
5. `sustainability.html`
6. `style.css`
7. `assets/` for interface sketch photos, visualization images, and any downloadable files

## Step 1. Set Up the Site Shell

Start by getting the boilerplate pages in place so you have something concrete to work from in class.

Begin with a fresh folder on your local machine that is not already inside another Git repository. This should be a new standalone project folder for the site you are building today.

Treat this as scaffolding, not as a finished site structure. The boilerplate material can be removed, rewritten, or reorganized later as your specific project takes shape. In class, the immediate goal is simpler: make sure the HTML files load, the navigation works, the stylesheet applies correctly, images display, and links behave the way you expect.

Before you make the first commit and publish the site, drop in the demo stylesheet as your starting `style.css`. That is the easiest way to make the live version readable right away with visible navigation, stable page structure, and sensible spacing.

The demo stylesheet (`style.css` in the course demo repository) is the recommended starting point. You can view the live demo site at [https://bds134.github.io/dh-demo/demo-site/index.html](https://bds134.github.io/dh-demo/demo-site/index.html) and copy the stylesheet from the repository at [https://github.com/bds134/dh-demo](https://github.com/bds134/dh-demo).

It already includes:

1. clear heading hierarchy
2. legible text size and line spacing
3. visible nav links
4. spacing around sections
5. enough contrast between text and background
6. a media query that makes the site readable on narrow screens — this is activated by the `<meta name="viewport">` tag already present in the demo HTML

Use that stylesheet first. You can revise it later once the basic site is live.

Your workflow for this step should be:

1. create the minimal local files first: the core HTML pages, `style.css`, and `README.md`
2. copy in the demo stylesheet as your starting `style.css`

Make a basic site with:

1. project title
2. short subtitle or one-sentence description
3. navigation linking all pages
4. consistent header and footer
5. the demo `style.css` in place so headings, text, and nav links are already readable

Minimum page purposes:

1. `index.html`: What is the project? What question does it ask?
2. `planning.html`: What were your design decisions? Show your interface sketches here.
3. `findings.html`: What does your visualization show?
4. `sustainability.html`: How was this site built and how could it be maintained?

## Step 2. Set up GitHub Pages and Confirm the Live Site

As soon as your four html files exist, along with `style.css` and `README.md`, and the navigation works, it is time to set up git, push to github, and enable GitHub Pages.

Follow these steps:

1. initialize Git in that folder and make your first commit
2. create the remote **public** repository on GitHub
3. connect the local folder to the remote repository and push your first commit
4. **turn on GitHub Pages** and get the site live as early as possible

>Github pages is a static site hosting service. It takes the files in your repository and serves them as a website. When you push updates to the repository, the live site updates too. This makes it ideal for a simple project website that does not require server-side processing or a database.
>
>Github Pages are free, easy to set up, and integrate well with Git version control. They are a great option for hosting a project website that is primarily informational and does not require complex interactivity.
>
>You can activate GitHub Pages in your repository settings. Go to **Settings → Pages**, select the source branch (usually `main`) and folder (root), and save. Your site will be live at `https://[username].github.io/[repo-name]/` within a few minutes. 

Do not wait until the end of class to publish. The point is to get a live URL early enough that you can keep testing the real site as you revise it.

## Step 3. Add Core Content

Once that first commit, push, and publication are done, continue revising the HTML pages and the `README.md` file. In particular, expect to keep developing the page with the featured visualization as the site takes shape.

Write short working text for each page.

### Homepage

Include:

1. project title
2. 1 to 2 paragraphs explaining the historical topic and question
3. 1 short paragraph explaining why the project matters

### Planning Page

Include:

1. a short placeholder note saying that interface sketches and design notes will be added after you complete them
2. space or a section heading where the sketch images and design notes will go later

### Findings Page

Include:

1. a short placeholder section where the featured visualization will go
2. 1 short paragraph introducing what you plan to feature
3. 1 short paragraph explaining what visitors should eventually notice there
4. 1 sentence on limitations or what the visualization will not show by itself

### Sustainability Page

Include:

1. what platform and tools you used (GitHub Pages, plain HTML/CSS, or Jekyll)
2. what files are essential to the site functioning
3. what data, media, or dependencies a future user would need
4. one sentence on what would be required to maintain or expand the site

This page can be brief. It should be a serious, honest statement of how the site was built and what it would take to keep it alive.

## Step 4. Refine the Styling

By this point, the site should already have a working stylesheet. Now improve and refine it.

Your design does not need to be complex. It does need to be readable.

Modify the demo stylesheet rather than replacing it. Focus on small revisions that make the site clearer for your project: spacing, heading emphasis, image sizing, and any adjustments needed for mobile readability. Responsive layout requires no framework — it is a few lines of CSS at the bottom of the file.

## Step 5. Add a Visualization

Once the basic site is live, the navigation works, and the layout is readable, choose one visualization from an earlier week to feature on the findings page. Good options include:

1. a chart or visualization
2. a map
3. a network graph
4. a cleaned dataset excerpt or table
5. OCR output or scraped material with interpretation

Your site should explain what this visualization is, how it was produced, and what it helps reveal.

Embed or link your chosen visualization.

If using an image:

1. place it in `assets/`
2. give it meaningful alt text
3. add a caption or short interpretive note

If using an interactive visualization:

1. link clearly to it
2. explain what the viewer should do or notice
3. explain how it connects to the project as a whole

## Step 6. Accessibility Check

With the site live, confirm:

1. every image has alt text
2. page titles and headings are descriptive
3. link text makes sense out of context
4. color is not the only way meaning is communicated
5. content is still readable on a narrow browser window

Once your site is live, run it through **WAVE** (https://wave.webaim.org): paste your GitHub Pages URL and WAVE will overlay the page with icons for every error and alert. Fix all red errors before submitting.

## Step 7. Confirm the Live GitHub Pages Site

By this point, your site should already be published. Now confirm that the live version is updating correctly and record the URL.

When the site is live, test:

1. homepage loads
2. nav works
3. images or links work
4. repository link works

## Step 8. Add Credits and Repository Link

Somewhere on the site (footer or sustainability page), include:

1. your name
2. course name
3. link to the repository
4. source or data credit
5. any image or media credit if needed

## Step 9. Enhance the README

Expand the `README.md` in the root of your repository so that it includes:

1. project title and one-sentence description
2. the live site URL
3. a list of the files in the repository and what each one is
4. your data sources
5. brief instructions for viewing locally and deploying via GitHub Pages

The README is what another researcher sees first when they arrive at your repository. It should be enough for someone to understand what the project is and how the site works without opening any other file.

## End-of-Class Checkpoint

Before leaving class, make sure you can answer yes to these:

1. Do you have the site shell and navigation in place, even if the sketches will be finished after class?
2. Is there a live site URL already working?
3. Can a visitor tell what the project is about within 30 seconds?
4. Is there at least one visualization with interpretation on the findings page?
5. Is the planning page ready for sketches and design notes, even if you will finish them at home?
6. Does the sustainability page have at least a stub with your platform listed?
7. Is the design readable and navigable?
8. Does the repository have a README?

## If You Finish Early

Choose one extension:

1. add an About page
2. add a short bibliography or sources section
3. create a project updates page
4. revise the layout for better mobile viewing
5. begin drafting your sustainability notes

## After Class. Sketch and Refine the Interface

Once the basic pages, navigation, text, styling, and featured visualization are in place, sketch each page on paper. In most cases, this step will be completed after class, not during class. You may begin it in class if time allows, but you should expect to finish and revise the sketches at home after the first working version of the site is up.

This is intentional. Good sketching is a thoughtful, reflective process, not a quick box-checking exercise. If done well, it takes time: you are deciding what a visitor sees first, what the site is asking them to do, and how your design choices reflect the needs of a specific user profile. It is better to do this carefully after the site shell, basic content, and visualization are visible than to rush through it in class.

Before sketching, write one or two sentences answering this question: **Who is the intended visitor for this site?** Be specific. Not "anyone interested in history" — a specific type of person: their background, what they are looking for, what they do not already know. Drucker calls this a *user profile* or *persona*. A first-year undergraduate is different from a professional archivist. A curious general reader is different from a peer researcher. Your design decisions — what to put first, how much to explain, how to label navigation — follow from this.

An interface sketch is a rough layout drawing — boxes and labels, not a visual design. Draw:

- where the navigation appears on each page
- where headings and text blocks go
- where your visualization will sit on the findings page
- what a visitor encounters first, second, and third
- what each page asks a visitor to *do*

Draw one sketch per page. When you are done, take a photo of each sketch with your phone and add the images to your `assets/` folder. These will appear on your Planning page.

Then revise the Planning page so it includes:

1. your user profile — one or two sentences describing your intended visitor from this sketching step
2. your interface sketch photos (embed them using `<img>` tags with alt text)
3. 1 short paragraph per page explaining: what you decided to *reveal* on that page, and what you designed it to *guide visitors toward doing* — and how that decision connects to your user profile
4. any decisions you changed between the sketch and the built page

## Deadline

Finish the site for the formal deadline.

**Due Monday, April 13 at 9:00 AM:** GitHub Pages website

Do not leave publishing until the deadline. Your site should be live well before then and revised incrementally.

All students complete this part.

For 4-credit students, this site should become part of the next stage of your project and will feed into the user testing, peer review, and sustainability documentation.