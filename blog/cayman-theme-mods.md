---
layout: default
lang: en
title: FR Cayman theme
---

# About theme modifications

## Heading Color

I am still playing with the **Cayman** theme
and have just updated the color for the sass variable `section-headings-color`,
did you notice?

```css
---
---

$header-bg-color: #7a1599 !default;
$section-headings-color: #925ad3 !default;
@import 'jekyll-theme-cayman';
@import 'start-btn';
```

> FR is a water sport, we need more blue than green.

This is actually the whole content of my `assets/css/style.scss`.
In the documentation of the Cayman GitHub-Pages theme they say that custom css or sass should *immediately* follow the import of the jekyll theme.

But what does immediately mean, do they mean there cannot be any empty lines in between.
For now I took *no* risk, and imported my start-btn immediately, on the next line.

## Start Button

I needed a **Start** button for [FREO](../angular/FREO.html).

Just another button, slightly changed from .btn in `jekyll-theme-cayman.scss`:
```css
.start-btn {
    display: inline-block;
    margin-bottom: 1rem;
    color: rgba(0, 0, 0, 0.7);
    background-color: rgba(128, 128, 255, 0.12);
    border-color: rgba(255, 255, 255, 0.2);
    border-style: solid;
    border-width: 1px;
    border-radius: 0.3rem;
    transition: color 0.2s, background-color 0.2s, border-color 0.2s;

    &:hover {
        color: rgba(67, 48, 150, 0.8);
        text-decoration: none;
        background-color: rgba(128, 128, 255, 0.2);
        border-color: rgba(0, 0, 255, 0.3);
    }

    + .btn {
        margin-left: 1rem;
    }

    @include large {
        padding: 0.75rem 1rem;
    }

    @include medium {
        padding: 0.6rem 0.9rem;
        font-size: 0.9rem;
    }

    @include small {
        display: block;
        width: 100%;
        padding: 0.75rem;
        font-size: 0.9rem;

        + .btn {
        margin-top: 1rem;
        margin-left: 0;
        }
    }
}
```
This button is in `start-btn.scss`.
I changed the color values, because the btn in the Cayman theme is made for the page-header and is fully transparent.
That means that you can not see the button on a white content background.

Here is how our start-button looks:

[Top](#){: .start-btn}

And here is the markdown for the button above:

```md
[Top](#){: .start-btn}
```
