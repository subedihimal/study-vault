**Browser architecture Overview**
![[Study/HTML/images/1.png]]

**HTML Flow Overview**
![[Study/HTML/images/2.png]]

- HTML : Raw html code
- CSS: Raw css code
- HTML Parser:  Converts html into structured data that browser can understand
- CSS Parser: Converts css into structured data that browser can understand
- Content Sink: Storage for the parsed html and css
- DOM: Document Object Model is a tree like structure that contain all the HTML elements in structured manner.
- CSSOM: DOM but for css

**Parsing in depth**
![[Study/HTML/images/3.png]]

Here from the figure 1+2* 3 is converted into BODMAS equivalent tree, where multiplication happens first then the addition happens

**Web Parsing**
Conventional Parsing: Follows all the rules properly
Un-Conventional Parsing: Isn't strict with rules

**Why html goes through un-conventional parsing ?**
- Not case sensitive
- Error Friendly