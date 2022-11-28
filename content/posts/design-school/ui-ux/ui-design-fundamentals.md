+++
title = "Ui Design Fundamentals"
date = "2022-11-23T14:22:08-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["ui-ux", "designschool"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = true
+++

## White Space

White space, also known as "negative space", is important as it gives our webpage "body". Without a good amount of whitespace, we risk "pancaking" our webpage

White space should take into consideration:

1. Space availability -- This is usually the viewport. (i.e. the body of our webpage or a phone screen)

2. Number of components -- Do we have a header/footer? How many headlines do we have? Buttons? Links? etc.

    A smaller number of components can give us more whitespace to work with. For example, a title and a button can be more impactful and easier to work with as opposed to a magazine/newspaper style webpage where we have to squeeze in more components.

3. Alignment -- Are we left-aligned? center-aligned? Do elements follow the same gridlines? If not, are they aligned in some other way?

4. Consistency -- Are we using the same amount of whitespace everywhere? Think about the spacing around buttons, headlines, paragraphs. 

## Contrast

Contrast allows us to distinguish elements better by manipulating color, brightness and/or opacity.

When applying contrast we should consider:

1. Is it type? If so, is it text the user needs to read?
2. If it's not type, how important is it in relation to other elements?

### Type

Type-based contrast, or the colors we use for the text foreground/background should be take into consideration:

1. How large is it?
2. Should it be readable?
3. Does it adhere to the WCAG Contrast Guidelines?

#### WCAG Contrast

Web Content Accessibility Guidelines give the following guidelines for color contrast ratios.

| Levels | Small Text | Large Text |
| ------ | :--------: | :--------: |
| AA     |  4.5 : 1   |   3 : 1    |
| AAA    |   7 : 1    |  4.5 : 1   |

The WCAG defines 3 levels of compliance, with AAA being the optimal level of compliance. While remembering this info can be hard, apps like [Stark](https://www.getstark.co/) can be used in Figma to help ensure we are being WCAG compliant. They also have an article about the [A-levels and contrast ratios](https://www.getstark.co/blog/accessible-contrast-ratios-and-a-levels-explained).

![WCAG Compliance Levels](https://res.cloudinary.com/stark-lab/image/upload/v1649356355/compliance_levels_f8abbf659e.png)

Image taken from Stark.

### Scale

Scale describes how large or small an element is, especially in regards to the porportions between elements.

When working with scale, we should consider:

1. Should it be readable?
2. How much space is available?

#### Type

Paragraph text should be no smaller than 16px.

The type scale should reflect a visual hierarchy. Visual hierarchy is a concept that states that we look at elements from biggest to smallest when trying to make sense of a webpage.

![Visual hierarchy](https://i.imgur.com/UqPKZ96.jpg)

Image taken from [Reddit](https://www.reddit.com/r/web_design/comments/bzjjfr/visual_hierarchy_perfectly_illustrated/)

