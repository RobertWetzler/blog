---
title: "Writing my Resume in Markdown"
date: 2026-01-06
draft: false
tags: ["blog"]
---


I've been exploring using [Hugo](https://gohugo.io/) for my personal site and have grown to appreciate how simple it is. Set up a theme, make a Github Action for publishing the site to Github Pages, then simply commit a markdown file for each new post. 

After setting it up, I was reminded of this great blog post, [Make Your Website Printable with CSS](https://barish.me/blog/make-your-website-printable-with-css/). The author's mention of maintaining their resume fully in HTML stood out as, especially I've been pondering a personal site.

Then it hit me, this could be even easier - if Hugo can transform Markdown to HTML, then why not maintain my resume in Markdown too?

### Defining the resume in Markdown
Markdown is a joy to write. Sure, HTML is pretty good, but it can get a bit cumbersome to write directly. With a Hugo Resume (TM), I just write out:
```
# Robert Wetzler
**Seattle, WA** · [github.com/RobertWetzler](https://www.github.com/RobertWetzler)
# Work Experience
## Where I work
### My Title · *Date*
Job Description
```
And Hugo will simply render this as a page on your site. Now we need to make it look like a resume...
### Use CSS rules to make it printable and look like an actual resume
As mentioned in the above blog, we can display the resume however we like on our website but make it printable as a regular PDF when the user clicks "Save as PDF (Ctrl+P)". This is achieved using the CSS [print media type](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Media_queries/Printing), which applies certain rules specifically when printing.

Most importantly, I can display my resume in dark mode 😎. The Hugo PaperMod theme defines CSS variables like `--entry` (background) and `--primary` (text color) that automatically change based on your light/dark preference. By using these variables in the resume CSS, it inherits the theme's colors:
```css
.resume {
  background: var(--entry, #fff);
  color: var(--primary, #000);
  ...
```
(of course, this gets disabled when the resume is printed/saved to PDF)
### Add a Hugo Template
This informs Hugo to render the resume page using the above printable CSS, plus a save to PDF button.
```html
{{- define "main" }}
<link rel="stylesheet" href="{{ "css/resume.css" | relURL }}" media="screen,print">
<article class="resume-page">
  <main class="resume">
    {{ .Content }}
  </main>
    <div class="no-print resume-intro">
    <button onclick="window.print()">Save to PDF</button>
  </div>
</article>
{{- end }}

```

### Maintaining my resume in version control 
Now I can use my commit history to keep a working record of my resume over the years. Gone are the days of sifting through Google Docs history or saving yearly versions!

### Making my resume "modular"
I tend to keep various resume pieces on hand, which I mix and match depending on the job I'm applying to. Instead of maintaining these in a massive word document, I can use Hugo shortcodes to compose my resume from reusable pieces. Store each job, project, or skills section as a separate markdown file:
```
content/resume/_pieces/
  job1.md
  project-backend.md
  project-robotics.md
  skills-backend.md
  skills-robotics.md
```
Then compose your resume by including just the pieces you need:
```
{{</* resume-piece "job1" */>}}
{{</* resume-piece "project-robotics" */>}}
{{</* resume-piece "skills-robotics" */>}}
```
Applying to a robotics company? Swap in `skills-robotics.md` and your robotics side projects. Backend role? Use `skills-backend.md` instead. Now you can create multiple resume variants without duplicating content.

## Want to see it in action? **[Check out my resume →](/blog/resume/)**


### Thanks for Reading!
This is my first blog post, hopefully I'm doing it right. I'm hoping to come back and write up my old projects I think are interesting (putting the "log" in "roblog"). Stay tuned!

