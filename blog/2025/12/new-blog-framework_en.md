---
title: "New Blog Launched"
description: "Development and deployment of the new blog framework"
aiGenerated: "translate"
pubDate: 2025-12-21
tags: ["blog", "vibe-coding"]
---

Under my direct direction and with the persistent efforts of Claude Opus 4.5, I completed the development and launch of a new blog framework in two days. This article records that process.

## Background

My previous blog was built with Hexo, and I chose a very flashy theme — then the blog went dormant shortly after launch. The reason for stopping wasn't the flashy theme or dissatisfaction with Hexo; it was that I lost interest in blogging itself. Later, discussing with friends in my group, some felt Hexo had performance issues and some switched to Hugo. I considered following the trend and trying Hugo, but I wasn't satisfied with the Chinese blog themes for Hugo, and since I don't know front-end development, I couldn't build my own theme, so it was put on hold.

Later Astro suddenly became popular. Unlike the static site generators mentioned earlier, Astro isn't designed just for static sites — it's a modern front-end framework that allows highly customized page development. More and more friends started rebuilding their blogs with Astro with great results, but I still didn't know front-end tech and couldn't catch up with the refactor wave.

Until recently, with the rise of AI agents, I found that an AI agent can quickly get you productive in completely unfamiliar development areas, and often the result is better and faster than me spending days learning and doing it myself. The concept of "Vibe Coding" also grew alongside AI agents. I became curious whether, as someone who knows nothing about front-end development, I could rely solely on natural language to direct an AI agent to build a modern blog.

## Framework Selection and Basic Configuration

Since I chose Astro — the hottest modern framework — I also picked trendy libraries: React for the front end, Tailwind CSS for styling, and Shadcn UI as the component library — very fresh and modern.

Because I intended not to write a single line of code, I needed to set up an AI agent to handle development. As a "privileged participant" in the GitHub Education program, I have a free GitHub Copilot Pro subscription. Although the quota isn't huge, this month is nearly over and it's close to the Christmas break, so I didn't need it for other tasks and was comfortable burning tokens. For the model I chose the well-regarded Claude Opus 4.5; its consumption multiplier is 3x, but I simply accepted that cost.

Copilot is built into VS Code, so I opened a folder I created two years ago, deleted everything inside, configured Astro, Shadcn, and Chrome DevTools MCP, then launched Copilot Chat and began directing it myself.

## Blog Development and Launch Process

### Directing the Development

Based on friends' experience, the Vibe Coding workflow of `Plan` followed by `Implementation` works well. In `Plan` mode I described a rough requirement:

> I need a blog framework based on Astro with the following requirements:
> 
> - Include basic pages required by a blog, including but not limited to an about page, a post timeline, tag pages, and a friend-links page
> - Use Shadcn as the UI component library
> - Since the blog content mixes Chinese and English, help me choose appropriate fonts

The AI agent quickly provided a detailed development plan and suggested finer points, including whether to add MDX support, dark mode, and SEO and RSS features. I didn't think MDX was necessary at this stage, but dark mode, SEO, and RSS were essential, so I asked the AI agent to include them. It added those to the plan.

Then I switched the AI agent to `Implementation` mode. It began implementing those features step by step and I only needed to keep clicking the "Accept" button. Soon the agent completed the blog framework and started a local dev server for preview.

Of course it wasn't entirely smooth: I directed the agent to fix all warnings and errors in the workspace, then acted as product manager and tester, directing the agent to fix UI bugs and implement new requests such as adding a table-of-contents component, adjusting the light/dark toggle styles, and adding math formula support. After burning about half of my token quota for the month, the blog framework finally met my expectations.

### Deploying the Blog

Next I deployed the blog by myself. I'm familiar with CI/CD and Cloudflare Pages, so I had the AI agent restructure the repo to separate the blog framework from content and moved configurable options into environment variables. The blog structure now looks like this:
```bash
blog/
├── .env.example          # environment variable template
├── xxx/                  # blog framework code
├── yyy/                  # more blog framework code
├── content@sha1hash      # blog content, managed as a git submodule
├── ...
.......
```

I created two GitHub repositories to host the blog and the content separately, then deployed the blog to Cloudflare Pages. Finally I set up GitHub Actions workflows for both repos so that when the content repo updates it automatically updates the blog submodule to the latest commit and triggers Cloudflare Pages to redeploy.

It's worth noting that while I'm familiar with this part, my personal deployment speed still lagged behind the AI agent's development speed.

### Directing Changes

After the blog went live, several issues surfaced. I requested additional changes and new features from the AI agent, such as:
1. Adding real i18n support instead of simple Chinese-English mixing
1. Optimizing the mobile UI layout
1. Improving the friend-links configuration format to simplify link exchanges
1. Adding a Generated AI notification component

Under my direction the AI agent implemented these changes quickly. The blog now essentially meets my expectations. I will continue to direct the AI agent for more fixes and improvements. If you find any issues, please contact me via the footer and I'll instruct the AI agent to fix them.

### Future Work

I expect to implement the following features:
+ Add a commenting system
+ Enhance post features
+ Improve the 404 page
+ Optimize blog performance

The AI agent will implement these incrementally under my direction, but I've exhausted this month's token quota so development will resume next month.

## About Friend-Link Exchanges

My previous blog theme didn't include a friend-links page, so I never exchanged links before. If you'd like to exchange links, please follow the instructions on the [Friend Links Page](../friends) and submit a PR to my blog content repository. You can also contact me directly by any means.

## Conclusion

Many thanks to AI agents and Claude Opus 4.5 for helping me, a person with no front-end skills, complete the development and launch of a modern blog. I hope this self-built blog framework helps me keep writing and avoid another long hiatus.
