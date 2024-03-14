# Frontend Mentor - Recipe page solution

This is a solution to the [Recipe page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it.

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [Sass](https://sass-lang.com/) - CSS Preprocessor
- [BEM](https://getbem.com/) - CSS naming methodology
- [Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/) - Accessibility

### What I learned

- Screen reader accessibility - elaborate
- Normalize CSS - elaborate
- Prettier Ignore
- noreferrer and noopener - I learned that using "rel="noreferrer noopener"" in your link tag is pretty important. Without using them, when a link is clicked, it could potentially leak information from the old page (where you clicked the link) into the new page, and can lead to JavaScript execution, leading to malicious activities and phishing attacks. Here's what ChatGPT says:

> ## noopener
>
> - Purpose: Prevents the newly opened page from having control over the page that opened it.
> - Security Benefit: This is particularly important because, without noopener, the new page
>   (the page you link to) can potentially access the window.opener property and execute JavaScript
>   in the opening page's context. This can lead to malicious activities, such as phishing attacks,
>   where the original page is replaced with a fake one to steal information.
> - Performance Benefit: Using noopener also improves performance for the page that opened the
>   link. Without it, the new page shares the same process as the opener page, which could affect the
>   performance of the original page.
>
> ## noreferrer
>
> - Purpose: Prevents the browser from sending the HTTP Referer header to the linked page.
> - Privacy Benefit: This hides the referrer information (the page the user came from) from the
>   destination page, which can be particularly useful for privacy reasons, ensuring that the
>   destination site does not know where the traffic originated from.
> - Security Benefit: Similar to noopener, noreferrer also implies noopener behavior in modern
>   browsers, providing the same security benefits by not allowing the new page to have control over
>   the originating page.
> - Compatibility Note: Before noopener was widely supported, noreferrer was often used to achieve
>   similar security benefits. Now, noopener is supported in most modern browsers, but noreferrer is
>   still useful for older browsers and for situations where you want to hide referrer information.
>
> ## Using Both
>
> While noopener alone can protect against the security vulnerabilities mentioned and is widely
> supported in modern browsers, adding noreferrer as well ensures broader compatibility with older
> browsers and also addresses privacy concerns by not leaking referrer information. Thus, using
> rel="noreferrer noopener" together in links to external sites that open in a new tab/window (target="\_blank")
> is a good practice for enhancing both security and privacy.

- Heading tags have a prebuilt margin on the top and bottom. This is to ensure a clear and visible hierarchy for readability and accessibility. While working closely with the design file and setting consistent padding around the elements, this got tricky. However, you can reset the heading tags to include no margin as long as the hierarchy is still visible, which can be done using padding.

- I learned how to override the bullet styles of a list item.

### HTML

```html
<ul class="custom-bullets">
  <li>
    <span class="label">Total</span
    ><span class="value">: Approximately 10 minutes</span>
  </li>
  <li>
    <span class="label">Preparation</span><span class="value">: 5 minutes</span>
  </li>
  <li>
    <span class="label">Cooking</span><span class="value">: 5 minutes</span>
  </li>
</ul>
```

### CSS

```css
ul.custom-bullets {
  list-style-type: none;
  padding-left: 0;
}

ul.custom-bullets li {
  position: relative;
  padding-left: 40px;
}

ul.custom-bullets li::before {
  content: '•';
  position: absolute;
  top: 50%;
  left: 8px;
  font-size: 13px;
  color: #7a284e;
  transform: translateY(-50%);
}
```

- Inheretance - elaborate (from bullet style, fixed by assigning font to body)

### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

### Useful resources

- [Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/) - This guide is helping me to better understand how to make the content of my web sites accessible to as many users as possible, including those with disabilities such as "blindness and low vision, deafness and hearing loss, limited movement, speech disabilities, photosensitivity, and combinations of these, and some accommodation for learning disabilities and cognitive limitations."[^1]
- [Sass](https://sass-lang.com/) - While I've used Sass in the past, their documentation helped me get a better understanding of this CSS preprocessor tool.
- [BEM](https://getbem.com/) - This guide helped me adopt the methodology and naming convention for organizing CSS code to make it more readable, scalable, and easier to maintain.
- [Normalize CSS](https://necolas.github.io/normalize.css/) - This seems to be the most comprehennsive CSS reset (but not actually a reset) that I've found so far. I haven't compared it line-by-line with Eric Meyer's CSS Reset as of yet, but it is in my plans. I'm also reading in the about section that it doesn't reset every element, instead it "retains many useful default browser styles[^2]." I do notice, however, that this post is written in 2012, so I may have to dig deeper into some research. While browsing Normalize css's [GirHub](https://github.com/necolas/normalize.css), I came across an interesting [issue](https://github.com/necolas/normalize.css/issues/880) that shows that the project may no longer be maintained. There are some alternatives by the community that I may look into. [This one](https://github.com/u1ui/norm.css) has tons of listed resources.

[^1]: Source: [Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/2023/REC-WCAG21-20230921/#abstract)
[^2]: Source [About normalize.css](https://nicolasgallagher.com/about-normalize-css/)

## Author

- Website - [Steve Xero](https://www.stevexero.com)
- GitHub - [Steve Xero](https://www.github.com/stevexero)
- Frontend Mentor - [@stevexero](https://www.frontendmentor.io/profile/stevexero)
- X - [@steve_xero](https://www.twitter.com/steve_xero)

## Acknowledgments

I'd like to give a shoutout to [Shashi Lo](https://github.com/shashilo) [X](https://www.twitter.com/shashiwhocodes) for hosting the [Gridiron Survivor Project](https://www.youtube.com/watch?v=JfLfIKMgnDQ&list=PLxiHOcgq5czRYfmc-bO_aABECrtBE3YR3) as well as [Corina Murg](https://github.com/CorinaMurg) [LinkedIn](https://www.linkedin.com/in/corinamurg/) for diving deep into accessibility right when I became very interested in it!
