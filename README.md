For best viewing, open the actual website [here](https://rpl-cs-ucl.github.io/seminar-template/)

## Tutorial

Preliminaries:
1. Fork the website 
2. Make github page from settings

How to edit the website:
1. Edit the _config.yml
2. Delete the `content/<>.html` files that you don't want as tabs or add new ones. Alphabetical order determines navigation order.
3. Edit them to your liking. Check example markdown code below this list for html templates. 
4. Edit `index.md` to your landing page description
5. Change `favicon.ico` to your icon
6. Move this file (`content/0-markdown.md`) to a different folder for future reference.

#### Optional edits:

- To use Google Analytics, add your analytics id to `_config.yml` in `google-analytics-id:` (if `google-analytics-id` is blank, the GA code will not added)
- The `custom.scss` in the `assets/css` folder exposes variables that can customize the basic style of website.
- Give a tiny splash of color on the header and footer borders by tweaking the `$top-border` 
- `$link-color` colors links

---------

## Content Pages

Content pages are written in markdown and can be enhanced using Liquid includes that are packaged with the template.
Start by editing the examples or creating new files in the "content" folder.

[Markdown](https://daringfireball.net/projects/markdown/) is a standard to [simplify writing](https://evanwill.github.io/_drafts/notes/writing-markdown.html) content for the web. 
[GitHub markdown flavor](https://help.github.com/articles/basic-writing-and-formatting-syntax/) can be used any where on GitHub and in Jekyll.
The basics are intuitive, you can learn in about a minute!
See [Markdown in a Minute](https://evanwill.github.io/_drafts/notes/markdown-minute.html) to get started.

At the top of each page is "YML front matter" used to configure the page.
Use these options:

- to include a page in the header and footer navigation, add `nav:` push the text you want to appear to the file's yml front matter. Alternatively, add `nav: true` to use the page's `title:` value. All pages with a `nav` value will appear in the top-bar, sorted by order of filenames. For simplicity use leading numbers in the lesson page filenames to create correct order.
- `title:` value will appear as `h1` at the top of the page.
- `description:` will appear as an indented text block below the title (optional). This gives you a chance to summarize the section contents. 
- `youtubeid:` will add an YouTube video embed (optional). Find the id in the YouTube link. For example, in `https://youtu.be/moJgWrD6dwg` or `https://www.youtube.com/watch?v=moJgWrD6dwg` the youtubeid is `moJgWrD6dwg`.
- Alternatively, if you don't want `title` or other options to appear on the page, you can over ride the layout by adding `layout: default` 


## Content templates

Use snippets from this file to copy over to your other pages as needed:


----------

#### Capture text:

```raw
{% capture text %}
1. Can add more complex text using markdown.
2. Use a Liquid capture to create the text.
3. It magically becomes a [Bootstrap Card](https://getbootstrap.com/docs/4.1/components/card/).
{% endcapture %}
{% include card.html text=text header="Example Card" title="Title example" img="uidaho-workshop.jpg" %}
```

```raw
{% capture text %}
1. Link: [GitHub](https://github.com)
{% endcapture %}
{% include card.html text=text header="Setup Overview" %}
```

----------

#### Alert:

```raw
{% include alert.html text="This is a [Bootstrap Alert](https://getbootstrap.com/docs/4.1/components/alerts/)" align="center" color="success" %}
```

```raw
{% capture text %}Note:
There are *soft* limits and guidelines for gh-pages usage: sites should be < 1GB, use < 100GB bandwidth per month, and make < 10 builds per hour.
If your site exceeds these quotas, GitHub will send you a notice asking you to modify the repository.
All content must follow the [community guidelines](https://help.github.com/articles/github-community-guidelines/), e.g. no violence, obscene sex, or illegal stuff.{% endcapture %}
{% include alert.html text=text color=secondary %}
```

----------
#### Raw code

`{% raw %}{% include figure.html img="uidaho-workshop.jpg" alt="workshop scene" caption="Library workshops!" width="75%" %}{% endraw %}`

----------

#### Figures 

- put any images you want to use in the "images" folder.
- in a markdown file where you want the image to appear, use the `figure.html` include on its own line, following the pattern: `{% raw %}{% include figure.html img="my-cat.jpg" alt="cat" caption="My cat" width="50%" %}{% endraw %}`

```raw
{% include figure.html img="uidaho-workshop.jpg" alt="workshop scene" caption="Library workshops!" width="75%" %}
```
-----------

#### Link Buttons 
```raw
{% include button.html text="Bootstrap Docs" link="https://getbootstrap.com/docs/4.1/components/buttons/" color="info" %}
```
---------

#### Modal
```raw
{% include modal.html button="Try Me" color="success" title="Example Modal" text="This is a modal, with little text." %}
```
-------------

#### YouTube embed
```raw
{% include video-embed.html youtubeid="moJgWrD6dwg" caption="Example video" %}
```
