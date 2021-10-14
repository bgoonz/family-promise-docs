---
description: >-
  In Figma, you can add layers directly to the Canvas. If you're designing for a
  specific device or screen size, you may want to create a container for your
  designs. This is where frames come in.
---

# Frames in Figma

Who can use this feature

 

Anyone on [any team or plan](https://help.figma.com/hc/en-us/articles/360040328273) can use frames.

 

Anyone with can edit access to a file can create and edit frames.

In Figma, you can add layers directly to the Canvas. If you're designing for a specific device or screen size, you may want to create a container for your designs. This is where **frames** come in.

If you've used design tools before, you'll be familiar with artboards. Like artboards, frames allow you to choose an area of the canvas to create your designs in.

Unlike traditional artboards, you can also nest frames within other frames. This allows to create more complex design that work together.

Frames also give you access to extra functionality, like [Layout Grids](https://help.figma.com/hc/en-us/articles/360040450513), [Auto Layout](https://help.figma.com/hc/en-us/articles/360040451373), [Constraints](https://help.figma.com/hc/en-us/articles/360039957734), and [prototyping](https://help.figma.com/hc/en-us/articles/360040314193).

## Create frames <a href="create_frames" id="create_frames"></a>

Create frames in the canvas using the frame tool. There are a few ways to select the frame tool:

* Use the keyboard shortcuts F or A
* Select the  **frame tool** in the toolbar:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de9216d2c7d3a7e9ae4c613/file-ilSbP1YKfF.png)

Then you can create a variety of frame sizes in the canvas:

* Click in the canvas to create a default frame with 100 x 100 dimensions
* Click and drag in the canvas to create a frame with custom dimensions
* Use the dropdown in the right sidebar to select a frame preset.
  1. Choose presets for popular device and assets templates:
     * Phone
     * Tablet
     * Desktop
     * Watch
     * Paper
     * Social Media
     * Figma Community
  2. Click the arrow to expand the section and select a preset from the list.

Identify frames by the  in the Layers Panel.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de921e02c7d3a7e9ae4c61d/file-VNyRVP9Yfq.png)

**Tip!**  You can also create a frame around existing objects, whether it's a single layer or selection of layers. Use the frame selection keyboard shortcut:

* **MacOS**: ⌥ Option ⌘ Command G
* **Windows**: Ctrl + Alt + G

## Frame properties <a href="frame_properties" id="frame_properties"></a>

There are a few properties associated with frames. Frames support the following properties.

* **Corner Radius**: Round the corner of a frame to create softer edges.
* **Clip Content**: Hide any objects within the frame that extend beyond the frame's bounds.
* **Layout Grids**: Create guidelines to help with the visual structure to your designs.
* **Auto Layout:** Create dynamic Frames that respond to their contents
* **Fill**: Apply a Solid Fill, Gradient, [Images](https://help.figma.com/hc/en-us/articles/360040028034) (PNG, JPEG, GIF, TIFF and WEBP) to a Frame.
* **Stroke**: Add strokes to a Frame to create a border or outline
* **Effects**: Add a shadow or blurs to a Frame

### Extra functionality <a href="h_3c11a618-988c-4bd5-aa63-78f24d518927" id="h_3c11a618-988c-4bd5-aa63-78f24d518927"></a>

Frames allow you to access extra functionality in Figma. You will need to use Frames to use the following features or functions:

* [**Layout Grids**](https://help.figma.com/hc/en-us/articles/360040450513): Apply transparent grids, columns, and/or rows to Frames to provide visual structure
* [**Constraints**](https://help.figma.com/hc/en-us/articles/360039957734) : Define how child objects respond when you resize a Frame. Apply Constraints to **objects** within a Frame.
* [**Auto Layout**](https://help.figma.com/hc/en-us/articles/360040451373): Add Auto Layout to Frames to create dynamic layouts that respond to their contents
* [**Prototyping**](https://help.figma.com/hc/en-us/articles/360040314193): Create interactive prototypes that move between Frames in your Canvas

A Frame is a **parent** object. This means that it can control or influence any **child** objects you place within it.

[**Learn more about parent/child relationships in Figma →**](https://help.figma.com/hc/en-us/articles/360039959014)

### Adjust properties of the frame <a href="h_90ab60a4-5e94-49bd-8d06-24b48506896a" id="h_90ab60a4-5e94-49bd-8d06-24b48506896a"></a>

In the past, it was possible to adjust the properties of child objects when you selected the Frame. Now, you can adjust the properties of the frame itself.

* Select a child object by using the keyboard shortcut: Enter or Return.
* Press the Tab key to select the next sibling.
* Press Shift + Tab to select the previous sibling.
* Press Shift + Enter to select the parent

If you want to adjust the fill and stroke properties of a frame and it's children, you can use **Selection colors** to [view or adjust colors in a mixed selection](https://help.figma.com/hc/en-us/articles/360042553434).

## Nest frames within other frames <a href="nest_frames_within_other_frames" id="nest_frames_within_other_frames"></a>

In Figma, you can create frames within other frames. We call this process nesting. This allows you to combine frames with different properties to build complex interfaces.

This creates new hierarchies or relationships:

* **Top-level frames:** Any frame that is directly on the canvas. For a frame to be a top-level frame, you can't nest it within another frame, group, or object.
* **Nested frame**: Any frame that is placed within another frame. You can place frames within top-level frames, or within other nested frames. Nested frames are both a parent and a child.
* **Children:** Any object that is within a frame. 

Learn more about [parent, child, and sibling relationships](https://help.figma.com/hc/en-us/articles/360039959014).

### Top-level frames <a href="top-level_frames" id="top-level_frames"></a>

Figma **bolds** top-level frames in the Layers Panel and shows the name of any top-level frames on the canvas:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de9222504286364bc92889e/file-MDfX7gA6Aq.png)

### Nested frames <a href="nested_frames" id="nested_frames"></a>

Nested frames are frames that you place within another frame or object. This makes them both a parent and a child. You can place frames within:

* Top-level frames
* Other nested frames
* In groups

In our example below, each of our elements are in their own frame. We have a status bar at the top and a navigation menu at the bottom. We also have a card that includes the details of our Upcoming Tickets.

Using one of our device presets, we can create a top-level frame for our elements. We can add our elements to the top-level frame to build a single screen in our mobile app.

![Image of an example app design in the canvas, where you can see the individual frames by themselves on the left and then combined into a single frame on the right](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de9254c04286364bc9288d9/file-vwL7ueP9ts.png)

## Resize frames <a href="resize_frames" id="resize_frames"></a>

You can interact with frames like any other object on the canvas, including change the size or scale of frames. There are a few ways to change the size of a Frame:

### Drag the frame <a href="drag_the_frame" id="drag_the_frame"></a>

Drag to resize a frame manually.

1. Select the frame in the canvas, or Layers Panel in the left sidebar.
2. Click the handle in one of the corners and drag to resize. Or, click one of the edges and drag.

**Tip! **To ignore any [Constraints](https://help.figma.com/hc/en-us/articles/360039957734) on child objects, hold down the modifier key:

* macOS: ⌘ Command
* Windows: Ctrl

### Change the frame preset <a href="change_the_frame_preset" id="change_the_frame_preset"></a>

Select another frame preset to change the frame's size. 

1. Select the frame.
2. In the Properties Panel in the right sidebar, select the frame field.
3. Select a preset from the list. 
4. Choose presets for popular device and assets templates:
   * Phone
   * Tablet
   * Desktop
   * Watch
   * Paper
   * Social Media
   * Figma Community
5. Figma will update your frame's dimensions to match the preset.

**Note:** If you have applied [Constraints](https://help.figma.com/hc/en-us/articles/360039957734) to any child objects, Figma will resize them to match the new frame preset. Otherwise, objects inside the frame will stay at the original dimensions and position.

### Properties Panel <a href="properties_panel" id="properties_panel"></a>

Update the Frame's **Width** and **Height** using the Properties Panel in the right sidebar.

Enter a new number in the **W **and **H** fields, or hover over the icon to scrub the field. Drag left to decrease and right to increase.

Toggle on the link button next to the **W**idth and **H**eight to constraint resizing to the current proportions.

![Image of the top-right corner of the Design tab in the right sidebar. The width and height fields have a blue dashed rectangle around them](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de9224004286364bc9288a0/file-GYdlkOZ1i2.png)

**Tip!** You can use the dimension fields to perform calculations. This allows you to quickly scale or resize objects.

* % Percentage e.g. 50% 
* \+ Add e.g. +100 
* \-  Subtract, e.g. -20 
* \*  Multiply, e.g. \*4 
* /  Divide, e.g. /8 

It's not possible to **multiply** a width or height by a **percentage** e.g. \*50% will result in a value 50x the original, not 50%.

### Resize to Fit <a href="resize_to_fit" id="resize_to_fit"></a>

You can resize a Frame so that it shrinks or grows to fit its child objects. This will redraw the Frame around the outermost bounds of the objects within it.

* Use the keyboard shortcut:
  * macOS: ⌥ Option Shift ⌘ Command R
  * Windows:
* Click in the top-right corner of the Properties Panel
*

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5de9224b04286364bc9288a4/file-Uo58OhBfHe.png)

Was this article helpful?
