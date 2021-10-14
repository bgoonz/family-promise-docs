# Tables In Figma

A ‘blow-up’ diagram view of how single cells in this approach can create a table.

![](https://miro.medium.com/max/626/1\*cwK2HtxugiZ_cfjMv8wnIg.png)

Tables are often harder to prototype than to code, but taking a single cell design strategy can make them responsive and maintainable. What’s more, all you need are Components, duplication and Auto-Layout techniques. I’ve experimented with a few ways and this method seems to have the best trade-offs. I’ll give you the whirlwind tour of the core visual styles of tables, how to build the single cell design, and the reasons why I opted for this as my preferred method of prototyping tables in Figma.

## Visual styles of tables <a href="5aab" id="5aab"></a>

There are a few different visual styles that are floating around on the internet today. Most tables you see are variations of one of these three.

### Classic table <a href="b4ed" id="b4ed"></a>

![Screenshot of a basic HTML table, two cells wide and three cells deep.](https://miro.medium.com/max/27/1\*-Mwy0jJIt\_6A6-XeKXkhmQ.png?q=20)A simple table with a 1px, black border and basic padding keeping the content readable.

![](https://miro.medium.com/max/380/1\*-Mwy0jJIt\_6A6-XeKXkhmQ.png)

This is the table you learn about in high school IT— humble and versatile to get your point across. With some minor tweaks to the vanilla HTML of good table design you can get an easily readable table. If you don’t know about how tables are created in code I recommend you read up on the [w3schools documentation](https://www.w3schools.com/tags/tag_table.asp).

### Striped tables <a href="6c66" id="6c66"></a>

![Screenshot of a table, using alternatively shaded rows and no border lines. Some white, some grey.](https://miro.medium.com/max/27/1\*50RBS9kbCjdQNcGk06WeuA.png?q=20)Alternative shading of rows lets the data stand out, yet still has a clear distinction between each line.

![](https://miro.medium.com/max/630/1\*50RBS9kbCjdQNcGk06WeuA.png)

Used in places like Apple’s Pages application, these are an eye catching alternative that let the data stand out. Again, [w3schools](https://www.w3schools.com/howto/howto_css_table_zebra.asp) is a fantastic resource to learn more about them.

### ‘Lined’ tables <a href="e203" id="e203"></a>

![A screenshot of Material Design’s Simple Table from the default documentation, using the dark theme.](https://miro.medium.com/max/27/1\*yd0wRIn5BX9bZpLLK-qsUA.png?q=20)The dark themed version of Material Design’s Simple Table.

![](https://miro.medium.com/max/630/1\*yd0wRIn5BX9bZpLLK-qsUA.png)

Looking at the [Simple Table](https://material-ui.com/components/tables/#simple-table) from Material Design as an example, you can see that each row is separated by a single line and each column is separated using generous spacing. Also known as a ‘horizontally divided table’.

## Single-cell design <a href="124d" id="124d"></a>

Now that we have an idea of the different major styles of table design, we can move forward to setting up Components to quickly build one in Figma. Compared to all other methods I’ve tried, the single-cell design approach is perhaps the most versatile.

### Cell types <a href="c56c" id="c56c"></a>

In total you can use three cell Components to develop the vast majority of your designs:

* Default cell—this makes up the bulk of your table data
* Header cell—usually with bold text, it makes up the top row or the left-hand column
* Selected cell—only essential if you want to conduct user research on this state

### Building the cells <a href="e788" id="e788"></a>

![Figma screenshot showing the three cell types, and the Auto layout options of 5px left-right and 4px top-bottom padding.](https://miro.medium.com/max/27/1\*J2aP0bseDjhS1IqliV39YA.png?q=20)Showcasing the three cell types using the classic visual style, revealing the layers makeup and Auto layout options.

![](https://miro.medium.com/max/630/1\*J2aP0bseDjhS1IqliV39YA.png)

We’ll be using the classic table visual style for simplicity for this walkthrough. Starting with the Default cell, create a text layer, add in some text, then adjust the width of the text layer to 50px. This should automatically change it to an Auto Height text layer — don’t worry, we can adjust this later. It forms the basis of the ‘responsive’ nature of these tables.

![Screenshot showing where the Auto Height option is for a text layer in the Design tab on the right.](https://miro.medium.com/max/27/1\*sVftaK3eZMaoWUDTA2ktYg.png?q=20)Showing where the Auto Height option is for a text layer in the Design tab on the right.

![](https://miro.medium.com/max/409/1\*sVftaK3eZMaoWUDTA2ktYg.png)

Next, turn it into a Component with `Cmd + Option + K` on Mac or `Ctrl + Alt + K` on Windows. Set the horizontal padding to 5px and the vertical to 4px. Reveal the Fill colour by clicking the eye icon, and click the plus ‘+’ button on the Stroke settings and use black as the colour. My screenshot says ‘Inside’ on the draw line option but you’ll want to use ‘Center’ or ‘Outside’ so that it displays properly later.

> **Hint**: if you’re using the Striped visual style, you’ll want two types of Default cell with differing Fill colours. I like to name them ‘default flip’ and ‘default flop’.

Next, we can create the Header cell and the Selected cell if needed. Make copies of your Default cell by holding down `Option` on Mac or `Alt` on Windows and dragging, or use the copy and paste shortcuts. Header cells usually will need the text to be bold, and the Selected cell can have its Fill colour changed to a light shade of blue. Turn these into new Components so that any style updates to the Default cell are propagated downwards, but the text bolding and Fill colour overrides are maintained.

> **Hint**: check the screenshot above if you aren’t sure you’ve set up your layers and Component subclassing correctly.

### Sizing your cells <a href="d0b6" id="d0b6"></a>

Before we start making tables it’s worth noting that in your working Design System or Palette, you’ll need a few different sizes of cells. I find it easiest to make a few using your underlying grid system as a guide. With a 12 column grid system I like to use 2, 3, and 4 column width cells, including internal guttering. Adjust the width of the text layer appropriately, and don’t forget to include the horizontal padding in your calculation.

> Hint: for those that aren’t well versed in grid systems, you can use the large [Bootstrap grid system](https://getbootstrap.com/docs/4.0/layout/grid/) as a starting point; this would result in cells of 130px, 210px, and 290px.

## Constructing the table <a href="af7a" id="af7a"></a>

With all that set up complete, we can now start to reap the benefits of a single cell design approach to making tables in Figma. Make sure you’ve written out the table data somewhere as it’s easier to work it out first on paper or a text editor beforehand.

### Create the ‘strips’ <a href="186e" id="186e"></a>

![Screenshot of Figma’s editor view with two rows of an example table.](https://miro.medium.com/max/27/1\*JMDE5JQQEi9pSuWD2PNSwA.png?q=20)You should end up with two ‘strip’ Frames— the header row, and the first data row.

![](https://miro.medium.com/max/630/1\*JMDE5JQQEi9pSuWD2PNSwA.png)

I’m going to go by row, but you can also go by column. Assuming the first row is the header, create enough instances of your Header cell to create all the headings. The first or last cell can be larger than the rest to emphasise it. Highlight them all, Frame your selection, and add Auto layout. Ensure that there’s 0px spacing between each item in the Auto layout settings. Repeat this for a row of Default cells.

### Glue it together <a href="7fbe" id="7fbe"></a>

![Screenshot in Figma’s editor demonstrating how quickly duplication and Auto layout of cells can make a table.](https://miro.medium.com/max/27/1\*om8cgdg26WSTrtVPmOdbwQ.png?q=20)If your table doesn’t look right, double-check the Auto layout spacing and ensure the cell’s Stroke is not ‘Inside’.

![](https://miro.medium.com/max/630/1\*om8cgdg26WSTrtVPmOdbwQ.png)

Duplicate your data row until you have enough data rows, select all the rows, Frame it, then add Auto layout again. Once you’ve set it to 0px spacing, it should look something like the above. All that’s left to do is add the correct data to the remaining cells and then use your table in your prototype. Congratulations, you have a table!

### Handling multiple lines <a href="87ab" id="87ab"></a>

![A row with misaligned cells, above, and the fixed row below using the shift-enter trick, below.](https://miro.medium.com/max/27/1\*NBTegp-9r4QZncRNCw_xeQ.png?q=20)If one cell becomes larger than the other, there’s a quick fix to line them up again.

![](https://miro.medium.com/max/630/1\*NBTegp-9r4QZncRNCw_xeQ.png)

One small problem with this approach is when text runs across multiple lines, it misaligns your table and leaves gaps. It’s easy to fix though. In the other cells within the same row, double-click until the cursor is at the end of the text then press `Shift + Enter` for each extra line needed. You can also use the text tool and click once, or use the shortcut `t`. It’s the least elegant part of this approach, but in my opinion, it’s a small price to pay for the speed it offers.

## Why it works <a href="6da4" id="6da4"></a>

There are three main principles I believe that make the single-cell design approach worthwhile.

### Flexible <a href="321d" id="321d"></a>

By building with the smallest unit possible, we can mix and match as much as we want to create tables that work. We don’t need to consider ‘merged’ cells either, as long as your cell Components all meet some standard sizing pattern you can put them together and grow the table as large as needed.

### Consistent <a href="ade7" id="ade7"></a>

By designing the small set of cells to all be compatible with each other, you ensure your tables remain consistent. With consistency in how it looks and how it fits together at creation time, we allow the user to do what they came for: read and understand the data written inside.

### Maintainable <a href="ae67" id="ae67"></a>

Above all, it’s maintainable. Keeping your Design System up to date is no easy feat and is a major driver of the DesignOps function. When there’s less parts, the job is smaller, and that opens up you and your team to iterate and evolve your design language much more easily.

> One final advantage that the single cell design has is the ability to introduce other cell types. If you want a checkbox cell for example, you can more easily swap out cells in older prototypes using the single cell approach.

The single-cell approach is my favourite method for everyday prototyping of tables in Figma. It requires a bit of work to make the tables using single cells, but it means that they’re flexible, consistent, and most importantly maintainable in a Design System. Once you know the basics, you can quickly make a wide variety of tables. For larger or more complex tables you may be better off using a different approach. It’s crucial for you to consider your day-to-day use cases and select an approach that suits your most common use cases.

\


### Introduction [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#introduction) <a href="introduction" id="introduction"></a>

Imagine the table as an organism. The table cell is then a molecule which is comprised of individual atoms. In design terms, they’re **cell properties**.

So, let’s start with the cell. It has three properties:

1. [Background](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#background)
2. [Border](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#border)
3. [Content](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#content)

Now we’ll take a closer look at each one of them.

### Background [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#background) <a href="background" id="background"></a>

The background will be a separate component in Figma. The size doesn’t really matter since we can stretch the component as we need, but let’s begin with setting the size to 100×36 pixels.

In this component, add a rectangle of the same size as the component itself. It will be the only object inside the component. We need to attach the rectangle’s borders to the component’s borders by using constraints (set constraints to “Left & Right” and “Top & Bottom” at the right panel in the _Constraints_ section), so that the rectangle stretches automatically to the size of the component.

_If you’d like to see this in action, _[_watch this tutorial_](https://www.youtube.com/watch?v=rRQAQ1d9q9w)_ on how the constraints work in Figma._

The Background Component (the ‘atom’) ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/1d9f3aff-354f-4617-baa1-d7bc36380613/1-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/1d9f3aff-354f-4617-baa1-d7bc36380613/1-tables-in-figma.png)

The fill color of the rectangle will determine the background color of the cell. Let’s pick the white color for it. I recommend choosing that color from the color styles that are configured at the beginning of the project.

Changing the background color ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/2308ca98-afed-435b-8e82-8cbba004eee9/samplebg.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/59a371cc-8aa0-4278-a220-785319f141c5/sample-bg-800w.gif)

### Border [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#border) <a href="border" id="border"></a>

This one is a bit trickier than the background. You can’t just create one rectangle with a stroke. We may need different kinds of borders: one for the separate cells (with borders around), one for the whole row of cells with only top and bottom borders, or one for the table header that we might want to separate from the rest with a wider line. There are many options.

Border properties:

* Border line (left, right, top, bottom, or absence of any of them)
* Line width
* Line color
* Line style

Each line within the cell border might havea different width, color, and style. For example, the left one could be a continuous red line, and the top one a dotted grey line.

Let’s create a component with a size of 100×36 pixels (the same as we did before). Inside the component, we need to add 4 lines for each border. Now pay attention to how we are going to do this.

1. Add a line for the **bottom border** with the length of the component width;
2. Set its position to the bottom border and constraints to stretch horizontally and stick to the bottom border;
3. For the **top border**, duplicate the line for the bottom border, rotate it by 180 degrees and stick to the top of the component. (Don’t forget to change its constraints to stick to the top and stretch horizontally.);
4. Next, for the **left border**, simply rotate by -90 degrees and set its position and constraints to be at the left side sticking to the left border and stretching vertically;
5. Last but not least, you can create the **right border** by rotating it by 90 degrees and setting its position and constraints. Set stroke color and stroke width for each line to gray (select from the color styles) and 1 pixel respectively.

**Note**: _You may be asking yourself why we rotated the line for the bottom border. Well, when you change the stroke width for a line in Figma, it will rise. So we had to set this “rise” direction to the center of the component. Changing the line’s stroke width (in our case it is the border size) won’t expand outside the component (cell)._

* [![WIX Partners](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/afd39be6-d836-4837-9f1d-3029c1da21ea/wix-logo.svg)Increase your clients’ conversion rates by applying user behavior psychology to their websites.GET THE ARTICLE!](https://bit.ly/wix_oct)

Now we can hide or customize the styles separately for every border in the cell.

A border component with 1px stroke ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/54b7d486-ca47-47a4-bdc4-a088de0b3539/3-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/54b7d486-ca47-47a4-bdc4-a088de0b3539/3-tables-in-figma.png)

If your project has several styles for table borders (a few border examples shown below), you should create a separate component for each style. Simply create a new master component as we did before and customize it the way you need.

A few extra examples of border styles. Note that the white background is not included in the component. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/5ca426bd-c59a-4376-b627-d3f80b6b4e5e/2-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/5ca426bd-c59a-4376-b627-d3f80b6b4e5e/2-tables-in-figma.png)

The separate stroke component will save up lots of your time and add _scalability_. If you change the stroke color inside the master component, the whole table will adjust. Same as with the background color above, each individual cell can have its own stroke parameters.

Changing border’s width and color ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/bbda009b-fa59-4c9f-af9e-3337707ee54c/sampleborder.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/d455ecc1-fe02-4f43-9b02-ff3c6c698f1d/sampleborder-800w.gif)

### Content [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#content) <a href="content" id="content"></a>

This is the most complex component of all.

We need to create all possible variations of the table content in the project: plain text, a text with an icon (left or right, different alignment), checkboxes, switches, and any other content that a cell may possibly contain. To simplify this tutorial, please check the components in the [mockup file](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#figma-table-mockup-download). How to create and organize components in Figma is a topic for another article.

However, there are a few requirements for content components:

* Components should stretch easily both vertically and horizontally to fit inside a cell;
* The minimum size of the component should be less than the default cell size (especially height, keep in mind possible cell paddings);
* Avoid any margins, so the components can align properly inside a cell;
* Avoid unnecessary backgrounds because a cell itself has it already.

Examples of cell content in components. This is not a complete list; you can use most of the components of your design system inside a table. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/410e6284-f976-4e1a-a6e6-98bd6745ff3e/4-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/410e6284-f976-4e1a-a6e6-98bd6745ff3e/4-tables-in-figma.png)

Content components can be created gradually: start with the basic ones like text components and add new ones as the project grows in size.

The reason we want the content to be in components is the same as with other elements — it saves uptime. To change the cell’s content, we just need to switch it in the component.

Editing the table using cells components ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/49b7a4e1-48c1-4a5f-a63b-f133462c09df/table-components.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/bb5cbc4a-fb8f-4a2e-b927-8f8cddaee391/table-components-800w.gif)

### Creating A Cell Component [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#creating-a-cell-component) <a href="creating-a-cell-component" id="creating-a-cell-component"></a>

We created all the atoms we need: background, border, content. It’s time to create a cell component, i.e. the molecule made from atoms. Let’s gather all the components in a cell.

The cell component (the ‘molecule’) ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/40f14761-70b7-40ba-85d0-5cfbcc963b5a/5-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/40f14761-70b7-40ba-85d0-5cfbcc963b5a/5-tables-in-figma.png)

Set the background component as the bottom layer and stretch it to the whole cell size (set constraints to “Left & Right” and “Top & Bottom”).

Add the border component with the same constraints as the background component.

Now to the most complicated part — the **content content**.

The cell has paddings, so you need to make a frame with the component’s content. That frame should be stretched to the whole cell size except for the paddings. The content component should also be stretched to the whole frame size. The content itself needs to be deprived of any margins, so all paddings will be set by the cell.

At the end of the day, cell paddings are the only property in a component that we will set only once without an opportunity to change it later. In the example above, I made it 4px for all sides.

**Note**: _As a fix, you can create columns with empty cells (with no content and width of 16px for example) left and right to the column where extra margin is needed. Or if your table’s design allows, you can add horizontal paddings inside the cell component. For example, cells in Google Material Design have 16px paddings by default._

Don’t forget to remove the “**Clip content**” option for the cell and frame (this can be done at the right-hand panel in the Properties section). The cell’s content can go out of its borders; for example, when a dropdown is inside your cell and you want to show its state with a popup.

**Note**: _We’ll be using this cell style as the main one. Don’t worry if your table has additional styles — we’ll cover that in the _[_Table States_](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#table-states)_ and _[_Components, Not Overrides_](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#components-not-overrides)_ sections._

### Cell Options For A Standard Table [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#cell-options-for-a-standard-table) <a href="cell-options-for-a-standard-table" id="cell-options-for-a-standard-table"></a>

This step could be optional but if your table needs states then you can’t go without it. And even more so if there is more than one border style in the table.

So let’s create additional cell components from which it’d be easier to build up a table. When working with a table, we will select the appropriate component depending on its position in the table (e.g. depending on the type of borders).

In order to do that, let’s take our cell component and create eight more masters from it. We also need to disable the appropriate layers responsible for borders. The result should look like the image below.

The cell options we need to build a table. Note that there could be a few extra depending on your table borders styles. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/8d920eee-827a-4d44-954b-e98746099914/6-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/8d920eee-827a-4d44-954b-e98746099914/6-tables-in-figma.png)

The top row is for the cells on top and in the middle of the table. The bottom row is only for the cells at the bottom. This way we’ll be able to put the cells one after another with no gaps and keep the same stroke width.

A few examples:

If each cell in the table has a border, we’d only need cells 1, 4, 5 and 8. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/27f1d254-3322-4fdd-9611-9deeda2eaa6e/7-tables-in-figma.png))If there are merged cells or border absence, we must apply the rest 2 and 3 cells as well as 6 and 7 to the bottom row. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/152b96b5-3fd3-4160-9515-3fec6569e2a5/8-tables-in-figma.png))If the table design considers the absence of vertical borders, cells 2 and 6 would be enough. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/19f7ea7d-8017-474b-87f6-14dab7d5e8f3/9-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/19f7ea7d-8017-474b-87f6-14dab7d5e8f3/9-tables-in-figma.png)

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/152b96b5-3fd3-4160-9515-3fec6569e2a5/8-tables-in-figma.png)

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/27f1d254-3322-4fdd-9611-9deeda2eaa6e/7-tables-in-figma.png)

**Note**: _For each border style created above, it’d be good to add master components like the ones described earlier._

So we have excluded the necessity of overriding cell’s instances (disabling the appropriate layers, to be precise). Instead of that, we use various components. Now if, for example, a column uses a different style from the default (the fill color or border), you can choose this column and simply change the relative component. And everything will be alright. On the opposite side, changing a border of each cell manually (disabling the appropriate borders) is a pain you don’t want to bother with.

Now we are ready to create tables (in terms of Atomic Design — organisms) from the various cell components (molecules) we made.



### Customizing The Table [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#customizing-the-table) <a href="customizing-the-table" id="customizing-the-table"></a>

Changing the row’s height in the whole table is relatively easy: highlight the table, change the element height (in this case, the cell’s height, H in the right-hand panel in the Properties section), and then change the vertical margin from the element to 0. That’s it: changing the line height took two clicks!

Changing the row height for the whole table ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/3391eda3-42c3-44c1-8b81-ec711788e8df/table-size.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/ba448d33-0336-41b1-8c4a-c75582d53cdf/table-size-800w.gif)

Changing the column width: highlight the column and change the width size. After moving the rest of the table close up, select the whole table by using the _Tide Up_ option in the _Alignment_ panel as well as the first item in the dropdown list under the rightmost icon.

Changing the column width. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/33c9658c-55f6-48db-849a-7890cc31b1e0/13-tables-in-figma.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/9e9eed10-3054-4a56-bb14-0f4449d74f1c/13-tables-figma-800w.gif)

**Note:** _I wouldn’t recommend grouping rows and columns. If you change the column size extending the elements, you’ll get fractional values for width and height. If you don’t group them and snap to the pixel grid, the cell size will remain an integer number._

The background color, stroke type, and content data can be changed in the appropriate component or in one of the eight cells master components (cells that had different stroke styles). The only parameter that can’t be changed right away is the cell margins, e.g. **content paddings**. The rest are easily customizable.

### Components, Not Overrides [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#components-not-overrides) <a href="components-not-overrides" id="components-not-overrides"></a>

Looking at what we got in the end, it might seem like overkill. And it is if there is only one table in your project. In this case, you can simply create one cell component and leave the background and stroke components off. Simply include them in the cell component, create the table and do the necessary customization for each separate cell.

But if components are included in a library that is used by a number of other files, here comes the most interesting stuff.

**Note**: \*I do not recommend changing the background color and stroke in components’ instances. Change them **only in the master**. By doing so, those instances with overrides won’t get updated. This means you would have to do that manually and that’s what we’re trying to avoid. So let’s stick to the master components.\*

If we need to create an additional type of table cells (e.g. the table header), we add the necessary set of master components for cells with the appropriate styles (just like we did above with the eight cells that had different stroke styles), and use it. Yes, it takes longer than overriding components’ instances but this way you will avoid the case when changing the masters will apply those changes to all layouts.

### Table States [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#table-states) <a href="table-states" id="table-states"></a>

Let’s talk about the states of the table’s elements. A cell can have three states: default, hover, and selected. Same for columns and rows.

If your project is relatively small, all states can be set by overrides inside instances of your table components. But if it’s a big one, and you’d want to be able to change the look of the states in the future, you’ll have to create separate components for everything.

You’ll need to add all eight cells with different stroke variants for each of the states (maybe less, depends on the stroke style). And yes, we’ll need separate components for the background color and the stroke for the states as well.

In the end, it’ll look similar to this:

The cells’ states (hover and selected) ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/5360264b-077f-42c7-b8cc-a7ce88618e2a/10-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/5360264b-077f-42c7-b8cc-a7ce88618e2a/10-tables-in-figma.png)

Here’s where a bit of trouble comes in. Unfortunately, if we do everything as described above (when changing the component’s state from one to another), there is a risk of losing the cell’s content. We’ll have to update it apart from the case when the content type is the same as in the master cell. At this point, we can’t do anything about it.

Table with various rows’ states. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/bb4b162f-c9ba-4e2d-9c04-839a3e13eb33/11-tables-in-figma.png))

![](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/bb4b162f-c9ba-4e2d-9c04-839a3e13eb33/11-tables-in-figma.png)

I added tables in the [mockup file](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#figma-table-mockup-download) that were made in a few different ways:

* Using this tutorial (separate components for cells’ styles);
* Using the cell component (components for borders, background, and content);
* Using the cell component that unites everything (with only content components in addition).

Try to play around and change the cell’s styles.

Changing the state of the row. ([Large preview](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/aee8ffc8-8a0e-4e1f-9cda-360fa5ba9644/12-tables-in-figma.gif))

![](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/783ea21b-7d19-442b-945b-aa41e6bbe640/12-tables-in-figma-800w.gif)

### Conclusion [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#conclusion) <a href="conclusion" id="conclusion"></a>

If you’re using the same components library in several projects and you’ve got a reasonable number of tables in each of them, you can create a local copy of components (cells components with stroke styles and, if needed, cells components with different states), customize them, and use them in the project. The cell content can be set based on local components.

Also, if you’re using the table for one large project with different kinds of tables, all the above-mentioned components are easily scaled. The table components can be improved to infinity and beyond, like creating the cell states when hovering and other kinds of interactions.

Questions, feedback, thoughts? Leave a comment below, and I’ll do my best to help you!

#### FIGMA TABLE MOCKUP DOWNLOAD [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#figma-table-mockup-download) <a href="figma-table-mockup-download" id="figma-table-mockup-download"></a>

As promised, I created a complete version of the Figma table mockup that you’re welcome to use for learning purposes or anything else you like. Enjoy!

[![Tables in Figma mockup design](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q\_80/w\_400/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/9d08b37a-9f74-4ec9-9cd9-acfdc924a4e8/tables-in-figma-mockup.png)](https://www.figma.com/file/PDmebscR4YRI42oMVjolz7j6/Table-\(Article\)?node-id=0%3A1)Here’s a [Figma table mockup](https://www.figma.com/file/PDmebscR4YRI42oMVjolz7j6/Table-\(Article\)?node-id=0%3A1) that you can use for learning purposes — let the creativity begin!

#### RELATED READING [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#related-reading) <a href="related-reading" id="related-reading"></a>

* “[Atomic Design](http://atomicdesign.bradfrost.com/table-of-contents/),” Brad Frost
* “[How To Architect A Complex Web Table](https://www.smashingmagazine.com/2019/02/complex-web-tables/),” Slava Shestopalov, Smashing Magazine
* “[Creating Atomic Components In Figma](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/link),” Design & Engineering team, littleBits
* “[Figma Tables: Data Grid Design By A Single Cell-Component](https://setproduct.com/blog/figma-tables-data-grid-design),” Roman Kamushken, Setproduct

#### USEFUL RESOURCES [#](https://www.smashingmagazine.com/2019/09/creating-tables-in-figma/#useful-resources) <a href="useful-resources" id="useful-resources"></a>

* [Figma YouTube Channel](https://www.youtube.com/channel/UCQsVmhSa4X-G3lHlUtejzLA/videos)\
  _The official Figma channel on YouTube — it’s the first thing to watch if you are new to Figma._
* [Google Sheets Sync](https://www.figma.com/c/plugin/735770583268406934/Google-Sheets-Sync)\
  _A Figma plugin that helps you get data from Google Sheets into your Figma file. This should work fine with the techniques from this tutoria, but you’ll need to invest some time into renaming all the text layers for this to work properly._
