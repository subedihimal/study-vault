**Browser architecture Overview**
![[20.png]]

- Disk API: For interacting with the os


**HTML Flow Overview**
![[21.png]]

- HTML : Raw html code
- CSS: Raw css code
- HTML Parser:  Converts html into structured data that browser can understand
- CSS Parser: Converts css into structured data that browser can understand
- Content Sink: Storage for the parsed html and css
- DOM: Document Object Model is a tree like structure that contain all the HTML elements in structured manner.
- CSSOM: DOM but for css

**Frame Constructor**
The Frame Constructor converts the DOM + CSS into the visual "boxes" (layout frames) that the browser uses to compute layout and draw the webpage.The Frame Constructor converts the DOM + CSS into the visual "boxes" (layout frames) that the browser uses to compute layout and draw the webpage.
This tree contains all the _visual boxes_ the browser will actually place on screen.
Not every DOM element becomes a box, and some boxes are created even without DOM nodes.

**Reflow**
Reflow (also called **layout**) calculates:
- The size of each element
    
- How much space it needs
    
- Line breaks, positions, margins, padding
    
- Where every box should be placed on the page

Panting
Painting is where the browser decides:

- Which pixels to draw
    
- Colors, borders, backgrounds
    
- Text glyphs
    
- Shadows, gradients, images

**Parsing in depth**
![[22.png]]

Here from the figure 1+2* 3 is converted into BODMAS equivalent tree, where multiplication happens first then the addition happens

**Web Parsing**
	Parser lets u know if there is error in the code (Validation check). Also does tokens, tokenization and tree creation.AST (Abstract Syntax Tree) comes under parser. After its sure that dom tree will be made without any error in the parser then then actual dom tree is created.
Conventional Parsing: Follows all the rules properly
Un-Conventional Parsing: Isn't strict with rules

**Why html goes through un-conventional parsing ?**
- Not case sensitive
- Error Friendly 





**WWW**

api.chaicode.com = API Server
imags.chaicode.com = Images

www.chaicode.com = Web server
even if u go to chaicode.com it redirects to www.chaicode.com
www means its a webserver
**Some Modern websites don't follow this, It's just a standard, but google does follow the www standard**
If a user goes to www he expects a HTML

### **CDN (Content Delivery Network)**

A CDN stores cached copies of your website’s static content (images, CSS, JS, videos, etc.) on servers around the world, so users can load your site faster from the nearest location.

 **If you use a hosting provider that includes CDN (e.g., Cloudflare, AWS CloudFront):**

You don't have to host your website with them, but **if your DNS is managed by Cloudflare or your site is integrated with AWS CloudFront**, the CDN automatically accelerates your content.

**If you host your website on your own server:**

You can still use a CDN by configuring it through any CDN provider (Cloudflare, CloudFront, Fastly, Akamai, etc.).  
CDNs pull content from your **origin server** and cache it globally.