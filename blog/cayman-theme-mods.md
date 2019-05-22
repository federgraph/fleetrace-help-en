---
layout: default
lang: en
title: FR Cayman theme
---

# About theme modifications

## Headings Color

I played with the [Cayman](https://pages-themes.github.io/cayman/) theme and updated the color for `section-headings-color`.
It used to be green.

```css
---
---

$header-bg-color: #7a1599 !default;
$section-headings-color: #925ad3 !default;
@import 'jekyll-theme-cayman';
@import 'start-btn';
```

> Fleet racing is a water sport, we need more blue than green.

This is actually the whole content of my `assets/css/style.scss`.

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
This button is in `start-btn.scss`, in the _sass folder.

I changed the color values.

In the Cayman theme the button is used on the page-header and is fully transparent with white border.
Therefore you cannot see the button on a white background in the normal content area.

Our new start-button:

[Top](#){: .start-btn}

And the markdown for the button:

```md
[Top](#){: .start-btn}
```
