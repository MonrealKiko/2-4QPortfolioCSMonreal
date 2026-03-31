# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.
- Answer: The positioning of the Sidebar changes in a way that it changes to its default position on the page, and other changes to its location adds to this default. This changes because previously the position of the Sidebar is dependent on the location of the other content. Now the Sidebar acts independently.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
- Answer: After applying position fixed, the sidebar now only stays on a specific part of the page (bottom) with varying sizes depending on the zoom, despite scrolling to different areas. This is different from position relative, as relative is more free to change as it relies on values given from top/left/right/etc., and others. While fixed requires the content to be at a constant set area in the page. 

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
- Answer: Position absolute now completely completely acts independent from all other elements of the page. No longer relying on the default position, applying absolute can now shift content freely, even overlapping or floating other elements without affecting others. It now acts separate from the document flow, allowing other elements to move into this. 

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?
- Just like normal axes (x,y,z), the values of these axes can determine its location on the page. If the y-axis discusses its up-down location, x-axis discusses its left-right location (though a x/y-index doesn't exist), then intuitively the z-axis discusses its front-back location (similar to how the 3d axes look like). The z-index values work accordingly with all the other z-index values of the page. The highter the z-index, the more likely it appears at the front of the page (front = overlapping other content), and vice versa. Here "Notice!" appears at the front of the page, because as the other content doesn't have a z-index value, it defaults to zero. When comparing the values of the z-indexes, we can see that "Notice!" has a much higher z-index (2 > 0), therefore, the greater z-index value overlaps the smaller. Swapping the z-index values changes the content layering. In this case setting "Notice!"'s z-index to 0, makes it appear below the Main Content. Or even setting Main Content's z-index to 3, makes it appear over "Notice!".

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 
    - Answer: Static: is the default positioning for all css elements. Relative: Changes its location based on its static position. Absolute: Changes its location based on other elements' location. Fixed: Fixes the content on a specific location on the page regadless of scrolling. 

    b. How does absolute positioning depend on its parent element?
    - Answer: 

    c. How do you differentiate sticky from fixed (you can research on sticky)?
    - Content applied with fixed is fixed consistently based on the viewport. While content applied with sticky, although similar, only sticks in place relative to a parent container (location dependent on this container). 

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
    - 
