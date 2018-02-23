---
layout: default
title: Adding images to GitHub wikis
date:   2018-02-22 17:50:00
categories: main
---

Yesterday I learned a neat trick to add images to GitHub wikis without having to upload them
to the main repository.

The GitHub wiki is based on git so one can simply clone the wiki for a given repo like so:

```bash
git clone git@github.com:<repo>/<proj>.wiki.git wiki && cd wiki
```

Once one has the wiki cloned and assuming you have some content already there you can simply
create an images folder and copy your image into it.

For this example we will use the Linux Tux:

<img src="/img/Tux.png" width="100">


```bash
mkdir images
cp ~/Tux.png images
```

Then you can simply reference the image in a wiki page with the following syntax: `![yourtitle](Tux.png)`

So for this example you could add a link to your `Home` wiki.

```bash
echo \!\[yourtitle\]\(images/Tux.png\) >> Home.md
```

Once that is done you can git add, commit and push to your wiki to see the image in its full glory.

```bash
git add Home.md images/Tux.png && git commit -m "first image" && git push
```

This will then produce the expected result in the wiki:

<img src="/img/Selection_223.png" width="300">
