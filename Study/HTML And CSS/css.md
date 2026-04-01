CSS implements design according to **Line + Specificity**. It prioritizes the specificity of the  selector first, then the line in which the code is written. Css reads the code form top to bottom and the design that comes later i prioritized before the earlier one given it doesn't have broader specificity compared to previous line.

![[24.png]]

Least Opinionated to more opinionated.
1. Normal CSS and Tailwind CSS (Tailwind is basically more Highly Optimized atomic css)
2. Shadcn
3. Bootstrap
---

### Flex Box

**Default Layout of flexbox**
![[27.png]]

**When you do `flex-direction: row`**
![[28.png]]
**PROPER NOTES IN COPY**

---
# Grid

commands:

```css

parent{
 display: grid;
}
/*Allows you to select how much space a child elemht takes in grid */

child{
grid-row-start:1;
grid-row-end:2;
grid-column-start:2;
grid-column-end:-3;
}

/* More Compact version */

child{
	grid-row: 1 / 2;
	grid-column: 2 / -3;
}

/* Even More Compact */
child{
	/* RowStart/ ColumnStart/ RowEnd/ ColumnEnd */
	grid-area: 1 / 2 / 2 / -3;
}

```

**Important Tips**
- Positive value counts from right to left  or top to bottom and Negative from bottom to top or left to right
- You can use **span** keyword to choose how many grid boxed to use Example:
```css
child{
	grid-row: 1 / span 2; /* Takes two box from row 1 */
	grid-column: 1 / 2;
}
```


---
[[Tailwind]]