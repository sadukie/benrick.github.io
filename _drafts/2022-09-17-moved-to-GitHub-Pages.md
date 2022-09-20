---
layout: post
title: "Migrating Blog to Jekyll on GitHub Pages"
date: 2022-09-20 12:00:00 -0400
comments: true
published: true
categories: ["Tutorial", "Archive"]
tags: ["GitHub Pages", "BlogEngine.NET"]
permalink: "/post/Migrating-Blog-Jekyll-GitHub-Pages/"
---

I recently [moved my blog](/post/Moved-My-Site-to-GitHub-Pages/) (this one) from BlogEngine.NET to a Jekyll site on GitHub Pages. I tried to keep all of my posts working with the same URLs for the content. I didn't worry about the tags, categories, etc. pages remaining the same. I figured that no one linked to those anyway, so the redirects would only be important on the posts.

Hopefully this post will help you migrate an old site from any platform (not just BlogEngine.NET) to Jekyll on GitHub Pages.

## Exporting Existing Blog Content

Before we can create all of the posts on the new site, we'll need to export the posts from our existing site. For this, most sites have an export function. In BlogEngine.NET, you'll want to got to the Admin Dashboard by navigating to `/admin/` or clicking on `Dashboard` in the Admin widget.

![Adminstration Widget in BlogEngine.NET](/images/files/2022-posts/BlogMigration/AdministrationMenu.png)

From here, we need to open up `Settings -> Import export` then click on the `Export` button in the `Export` section of that page.

![Export Screen in BlogEngine.NET](/images/files/2022-posts/BlogMigration/ImportExportScreen.png)

When we click this button, the site will create a `BlogML.xml` and your browser will download it. That's an XML containing your posts, comments, metadata, etc. from your site.

<p class="message">I exported my comments, since I didn't care about preserving them. I did some googling and found that some people created tools to assist in moving this data to Disqus, but I haven't bothered with that yet.</p>

## Setting Up Jekyll Site on GitHub Pages

Now I needed a new GitHub repository to host the content for my site, so I created [benrick.github.io](https://github.com/benrick/benrick.github.io/) to host my site.

### Types of GitHub Pages sites

For GitHub Pages, you can set up `User`, `Organization`, or `Project` sites to be hosted by GitHub Pages.

I did a user site with repository name `benrick.github.io`, which followed the required repository name pattern of `[username].github.io` (will be the same as the address).

If I'd done a site for my `DevChatter` organization, it would've been `devchatter.github.io`, following the `[organization].github.io` pattern.

If I did a project site, it could've had any name, but would be hosted at `[username].github.io/[project-name]` or `[organization].github.io/[project-name]`. So if you're going to do this, be warned of the subfolder, which can be avoided with a custom domain (discussed below).

### Configuring the Repository as a GitHub Pages Site

Navigate to the `Settings` of the repository and click on the `Pages` in the `Code and automation` section of the sidebar navigation.

![Settings page showing Pages in sidebar]()



[Official GitHub Page Get Started Documentation](https://docs.github.com/en/pages/quickstart)

### Choosing and Customizing a Theme

Content about layouts and features here.

## Converting Blog Posts to Jekyll Markdown Posts

Content here

### Content Fixes

Content about fixing tags, categories, permalinks.

## Deploying and Verifying

Content here

## Setting up Custom Domain (Optional)

If you want to have a custom domain, you'll need to set up your DNS to point to your GitHub Pages and then tell your GitHub Pages repository about your custom domain. By doing it in this order, GitHub will be able to verify that your DNS settings are pointing to the GitHub Pages site.

### Set Up DNS A Records

TO set up the A Records for your domain, create it with these IP Addresses pointing at GitHub Pages, so it looks like these:

![Google Domains Custom Records View](/images/files/2022-posts/GDomainsCustomRecordsView.png)

For the first record, leave the `Host name` blank, set the `Type` to "A", and the `Data` to the first IP Address. In some DNS systems you add more records (like this one), but in other systems, you create 4 separate A records with these addresses.

- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

You can check the [GitHub Pages Custom Domain Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain) for the most up-to-date list of IP Addresses.

### Set Up DNS CNAME Record

Next, you'll set up a CNAME Record to point to the subdomain you have at GitHub, mine is `benrick.github.io`. Create the CNAME record like this:

![Google Domains Custom Records Edit](/images/files/2022-posts/GDomainsCustomRecordsEdit.png)

Just be sure that you set the `Host name` to "www", the `Type` to "CNAME" and the `Data` to your "*github.io" subdomain.

### Set Custom Domain in GitHub

After configuring DNS, we need to tell GitHub by going to the `Settings` tab in your repository, and clicking on the "GitHub Pages" link in the sidebar navigation.

![GitHub Settings Side Nav](/images/files/2022-posts/GitHubRepoSettingsNav.png)

Now change the Custom domain to your domain name that we just configured and save that change, which causes GitHub to run a check of the DNS settings.

![GitHub Pages Settings Custom Domain](/images/files/2022-posts/GitHubCustomDomainSetting.png)

After verification, the page will look like this:

![GitHub Pages Settings Custom Domain Verified](/images/files/2022-posts/GitHubCustomDomainSettingVerified.png)

## Additional Resources

If you want full instructions for setting up the custom domain name for GitHub using Google Domains, check my post about [how to set up a custom domain from google domains for GitHub pages](/post/Custom-GitHub-Pages-Domain-with-Google-Domains/).