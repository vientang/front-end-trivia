#CSS Questions

What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why? 
Resetting - Removing all styling from every element - margins, padding, etc. All elements will have the same font-size, same line-height and no spacing. Eric Meyer's Reset is the most common approach. 
Normalizing - Different browsers render styles and markup in slightly different ways. These inconsistencies across browsers can throw off your expectations. The concept of normalizing your code makes elements render consistently across browsers. So all h1s will have the same size across browsers, for instance. Nicolas Gallagher's normalize.css is widely used for normalizing.
