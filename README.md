# Easy CSS Grid
An easy-to-use CSS grid framework that is based on the `grid` CSS property and implemented using CSS Custom Properties.


## Install
### npm
`npm install easy-css-grid`  

### sass 
Import into your sass using `@import '~easy-css-grid/easy-css-grid';`


## Properties
```css
:root {
	--Grid-width: 100%;
	--Grid-gap: 1em;
	--Grid-columns: 12;
	--Grid-columns-width: 1fr;
	--Grid-rows: 1;
	--Grid-rows-height: auto;
	--Grid-rows-min-height: var(--Grid-rows-height);
	--Grid-rows-max-height: var(--Grid-rows-height);
	--Grid-column-gap: var(--Grid-gap);
	--Grid-column-position: auto;
	--Grid-column-span: 1;
	--Grid-row-gap: var(--Grid-gap);
	--Grid-row-position: auto;
	--Grid-row-span: 1;
}

.Grid {
	--width: var(--Grid-width);
	--gap: var(--Grid-gap);
	--columns: var(--Grid-columns);
	--columns-width: var(--Grid-columns-width);
	--columns-template: repeat(var(--columns), var(--columns-width));
	--rows: var(--Grid-rows);
	--rows-height: var(--Grid-rows-height);
	--rows-min-height: var(--rows-height, var(--Grid-rows-min-height));
	--rows-max-height: var(--rows-height, var(--Grid-rows-max-height));
	--rows-auto: minmax(var(--rows-min-height), var(--rows-max-height));
	--rows-template: repeat(var(--rows), var(--rows-auto));
	--column-gap: var(--gap, var(--Grid-column-gap));
	--row-gap: var(--gap, var(--Grid-row-gap));
}

.Grid .cell {
	--column-position: var(--Grid-column-position);
	--column-span: var(--Grid-column-span);
	--column-start: var(--column-position);
	--column-end: span var(--column-span);
	--row-position: var(--Grid-row-position);
	--row-span: var(--Grid-row-span);
	--row-start: var(--row-position);
	--row-end: span var(--row-span);
}
```


## Usage
E.g.:
```css
:root {
	--Grid-columns: 3;
	--Grid-gap: 10px;
	--Grid-width: 1024px;
	--Grid-rows-height: 100px;
}

.Grid {
	margin: 10px auto;
}

.Grid.grid-of-four {
	--columns: 4;
	--rows: 4;
}

.Grid .cell {
	background: #ddd;
	text-align: center;
	line-height: 100px;
}

.Grid .cell.two-cols {
	--column-span: 2;
}

.Grid .cell.two-rows {
	--row-span: 2;
}

.Grid .cell.col-position-first {
	--column-position: 1;
}

.Grid .cell.col-position-second {
	--column-position: 2;
	--row-position: 2;
}
```
```html
<div class="Grid">
	<div class="cell">CELL</div>
	<div class="cell">CELL</div>
	<div class="cell">CELL</div>
	<div class="cell col-position-second">CELL</div>
	<div class="cell two-cols col-position-first">CELL</div>
</div>

<div class="Grid grid-of-four">
	<div class="cell">CELL</div>
	<div class="cell">CELL</div>
	<div class="cell two-cols two-rows">CELL</div>
	<div class="cell">CELL</div>
	<div class="cell">CELL</div>
</div>
```

## Licence
Code released under the [MIT License](LICENSE).