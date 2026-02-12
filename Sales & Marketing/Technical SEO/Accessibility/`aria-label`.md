- Will override `alt` for image tags or `for` on `<label>` tags in forms
- Intended for use with screen readers
- Default strategy for labelling `<button>` elements

### Uses

 `aria-label` is a tag which is typically put on html tags on the page which represent navigational landmarks

- Declaring Navigational landmarks
```
<div role="navigation" aria-label="Primary">
	<ul>
		<li>...a list of links here ...</li>
	</ul>
</div>
<div role="navigation" aria-label="Secondary">
	<ul>
		<li>...a list of links here ...</li>
	</ul>
</div>
```
- Declaring Navigational regions
```
<div role="region" aria-label="weather portlet"> ... </div>
```
- Declaring maths
  ```
  <div role="math" aria-label="6 divided by 4 equals 1.5">
	  <math xmlns="https://www.w3.org/1998/Math/MathML">
		  <mfrac>
			  <mn>6</mn>
			  <mn>4</mn>
		  </mfrac>
			  <mo>=</mo>
			  <mn>1.5</mn>
	  </math>
  </div>
  ```
ref: [WCAG ARIA6](https://www.w3.org/WAI/WCAG22/Techniques/aria/ARIA6)