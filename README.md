# CV

An online which uses no Javascript, just static hand-crafted semantic HTML and CSS.

The CSS is little changed from its original 2021 incarnation and so uses a media query for responsiveness. The break point is at 800px. Smaller than the content has no grid layout. At 800px a simple grid layout is applied to the three section elements.

The collapse/expand pattern here is taken from the always excellent [MDN docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/:checked#toggling_elements_with_a_hidden_checkbox).

Each of the items on the right hand side of the grid (when applied) is collapsed by default and expanded by clicking on a hidden checkbox which occupies the same space as the svg icon which is visible and therefore appears to be clickable.

The hamburger menu is collapsed by default using a similar css pseudo class selector (:checked) and the subsequent sibling combinator to target the element (a sibling of the checkbox in the same parent element) to hide when checked.

```css
    .collapsible-menu input[type="checkbox"]:checked~ul {
        opacity: 0;
        max-height: 0;
        border: none;
        z-index: -1;
    }
```

A grid area is also applied to each of the collapsible items which are the different jobs and education in the c.v. A one second opacity transition is applied to the job description etc when they are expanded or collapsed.

Icons are inline [feather icons](https://feathericons.com/).

A previous version had a mouse running around on the screen using CSS animations with transform translateX and Y to move the SVG of the mouse around in a rectangle, its there in the git history but I removed it as it was rather distracting I thought.

Hosted [on Render](https://paulhibbert.onrender.com/).
