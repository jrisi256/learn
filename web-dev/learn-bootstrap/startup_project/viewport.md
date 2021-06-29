https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag
[For a good overview of visual vs. layout viewports on mobile](https://stackoverflow.com/questions/6333927/difference-between-visual-viewport-and-layout-viewport)

The viewport of a browser is the area of the window in which web content can be seen. This is often not the same size as the *rendered* page. In the case that the two don't match, the browser provides the user with scrollbars.

Something different happens on mobile devices however. For example, a mobile screen might have a width of 640 pixels. A webpage might be rendered with a **virtual viewport** of 980 pixels, and then it will be shrunk down to fit into the 640 pixel space. The viewport on a mobile device can thus be larger or smaller than the visible area. The viewport on mobile devices is mostly in charge of determining how content is laid out and when text wraps on the webpage. Users can then pan around and zoom in to see different areas of the screen. All these gestures change the **scale** of the viewport, but they do not change the **size** of the viewport. This is done because many websites are not optimized for mobile and look bad when natively rendered at such a small viewport size. The **virtual viewport** is a way to make non-mobile-optimized sites look better on mobile. The viewport basically got split into the **visual** and **virtual** or **layout** parts. It is rendered like a desktop browser, and then users can pan around the big desktop-style website.

Pages which use media queries for optimizing for mobile have a problem. If the virtual viewport is 980px, media queries that kick in at 640px or 480px will never activate. To mitigate this problem, Apple introduced the viewport meta tag in Safari for iOS to let web developers control the viewport's size and scale. Many other mobile browsers also now support this tag.

```html
`<meta name = "viewport" content = "width = device-width, initial-scale = 1">`
```

The width property controls the size of the viewport. Normally it's good to leave it at *device-width* which is the width of the screen in CSS pixels at a scale of 100%. The *initial-scale* property controls the zoom level when the page is first loaded. The *maximum-scale* and *minimum-scale* properties control how users are allowed to zoom in and out. Make sure you don't cause accessibility issues with these settings.