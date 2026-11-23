---
title: "Five checks before publishing a Jekyll portfolio"
date: 2026-11-23 00:00:00 +0530
description: "A pre-launch checklist for Jekyll portfolios, covering homepage links, project pages, build output, and custom domains."
---

A portfolio homepage can answer three questions quickly. What kind of work do you do? Where can I see an example? How can I contact you? Those questions give me a way to check the content and the technical setup in the same pass.

1. **Read the first screen on a phone.** Check that someone can see your specialty and find the link to your work without having to read the whole page. Use descriptive links such as “View selected work” and “Get in touch.”
2. **Give each project one concrete detail.** A project name, your contribution, and a detail about the scope help readers understand the work. If you can share a screenshot, add a caption that explains what they should look at.
3. **Build before you ship.** Run `bundle exec jekyll build` from the site repository. Check that the homepage, work page, and latest post appear in the generated `_site` directory. Use Jekyll's `relative_url` filter for internal links so they include the configured base path.
4. **Check the generated URLs.** Open the generated HTML and inspect the canonical link. For a site with a custom domain, set the full HTTPS address in `url` in `_config.yml`. Verify that the sitemap uses the same domain.
5. **Follow the visitor's path after deployment.** Open the home page in a private window, click through to your strongest project, and try the contact links. This checks that a visitor can get from the first screen to a real way to reach you.

I keep this checklist short enough to run whenever I add a project or update the homepage.
