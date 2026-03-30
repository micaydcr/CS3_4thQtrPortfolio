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

**The sidebar moved 20 px down and 20 px to the right from its original position. Unlike static positioning, relative positioning allows the element to be shifted using top, left, right, or bottom while still keeping its original space in the layout. Other elements are not affected and will not overlap it.**

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

**When I scroll, the footer stays visible at the bottom of the screen at all times. This is because fixed position places the element relative to the browser view not the document. Unlike relative positioning, it does not move along the page when scrolling.**

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

**Setting position to absolute removes the element from the normal layout and places it based on a specific position on the page. Unlike fixed, the element does not stay in the same place on the screen when scrolling—it scrolls with the page.**

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

**The notice appears on top of the content because it has a higher z-index value than the content. The z-index controls which element is displayed in front when elements overlap. If the z-index values are swapped, then the content will appear on top of the notice.**

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?

- Challenge Answers:

**1. To place the .notice at the top-right corner of .content, .content must be set to relative position so that .notice can use it as some sort of reference.**

**2. When .content is set to relative, the .notice stays positioned inside the .content box. And when .content is set to fixed, the .content stays in the same place on the screen even when scrolling, and the .notice also stays with it.**

**3. The z-index determines which element appears on top when elements overlap. The element with the higher z-index will be displayed in front, while the lower one will appear behind.**

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    - **Static: Default position, follows normal page flow.**
    - **Relative: Moves from its original position but still keeps its space.**
    - **Absolute: Positioned relative to its nearest positioned parent, removed from the normal flow.**
    - **Fixed: Stays in the same place on the screen even when scrolling.**

    b. How does absolute positioning depend on its parent element?

    - **Absolute positioning depends on the nearest parent element that has a position set (like relative, absolute, or fixed). If no parent has a position, it will be positioned relative to the whole page.**

    c. How do you differentiate sticky from fixed (you can research on sticky)?

    - **Fixed: Always stays in the same position on the screen.**
    - **Sticky: Acts like relative at first, but becomes fixed when you scroll to a certain point.**

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.

    - **I would use fixed for the navigation bar so it stays visible while scrolling.**
    - **I would use absolute to place labels like "Important" on announcements.**