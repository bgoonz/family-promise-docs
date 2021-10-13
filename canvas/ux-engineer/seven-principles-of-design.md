---
description: >-
  There are really lots of useful ways to categorize and talk about design. You
  could come up with any arbitrary way of grouping these topics together,
  listing them out, and exploring them.
---

# Seven Principles of Design

## Seven Principles of Design

There are really _lots_ of useful ways to categorize and talk about design. You could come up with any arbitrary way of grouping these topics together, listing them out, and exploring them.

For our purposes, we're going to focus on **seven principles of design** that combine to give us a solid foundation for approaching problems:

* [ ] Unity
* [ ] Balance
* [ ] Alignment
* [ ] Hierarchy
* [ ] Emphasis
* [ ] Proportion
* [ ] White Space

In this module, we'll dive into each of these design principles. We'll refer to each of them throughout the rest of this course, during our Design Critiques, and throughout Labs.

## Unity

### What's Unity?

**Unity** is **oneness**.

It's not so much about grouping things into one group, but more **making things **_**one**_** thing**. When we're talking about a group of truly independent things, unity means they fit together into a clear, logical, simple whole.

In a way, unity encapsulates all the other design principles—the rest of the concepts we'll explore need to work together to **present one seamless user experience**.

### Achieving Unity

Unity takes significant conscious effort to achieve—it won't happen on its own!

A good general approach to achieve unity is to focus on **top-down design, bottom-up implementation**.

Why? Think about this for a moment.

If we think about something with many parts as a whole _first_—even if we only have some high-level, general information to start—it gives us the perspective and context we need as we proceed to implement the parts themselves.

One example would be first focusing on developing a user flow for a product, then moving on to develop wireframes for each screen, then moving on to develop individual components.

### Types of Unity

Note that the design artifact workflow we just described (user flow → wireframes → components) incorporates two kinds of unity: **conceptual** and **visual** unity.

#### Conceptual Unity

Conceptual unity means that _ideas_ fit together. In the context of a product, this could mean that as a user, if I need to perform a certain action in multiple ways, maybe I can do those actions from a single place.

It could also mean using consistent layouts across pages in an application, or ensuring that everything contained on a page is addressing the same set of user problems.

#### Visual Unity

Visual unity means that _visual elements_ fit together. In many practical situations, it means we're working to eliminate redundancy and simplify what's presented to the user.

One example of visual unity might be to decide to only use one primary action color throughout an entire product—whether it be on buttons, links, or other interactive elements—to provide an abundantly clear message to the user across contexts: "Here's how you can do something."

Another example might be that all of the elements on a page are consistently styled.

Using a design system like Ant Design helps us achieve both conceptual and visual unity by standardizing both our approaches to solve user problems and our visual implementation of those solutions.

## Balance

### What's Balance?

Let's turn to Merriam Webster's for this one: balance is "a state in which different things occur in equal or proper amounts or have an equal or proper amount of importance" ([source (Links to an external site.)](https://www.merriam-webster.com/dictionary/balance)).

Note a key distinction here: balance doesn't necessarily mean that all sides of something are _equal_—it could just mean that everything involved has the _proper_ amount of _x_, where _x_ is something we care about. _x_ might itself be a principle of design!

### Symmetry

**Symmetry** is a _type_ of balance in which all sides of something have an _equal_ amount of something.

![Screen%20Shot%202021-08-29%20at%207.45.52%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388974/preview)

Symmetry can be visual (e.g., both columns of a page are the same height) or conceptual (e.g., if there are two major topics addressed in a web application, I can navigate a similar structure for each one).

### Achieving Balance

Ultimately, balance is something you'll develop an intuition for as you gain experience seeing how users react to how concepts and visual elements are arranged and presented.

To start, though, make it a point to think about balance for each design principle we'll examine. That means, for example, going out of your way to critique your own designs for balance in proportion, balance in emphasis, and balance in white space.

Does your design "feel" balanced in each of these ways?

## Alignment

### What's Alignment?

Alignment is one of the most critical principles of design we'll talk about, because it will apply to almost everything you design, build, and compose together in Labs.

**Alignment** means that things **line up**—two or more elements presented together **share visual boundaries and/or centers**. You should be able to draw a few straight, imaginary lines over the visual elements you've arranged, and find that they either **share a common border with** or **have symmetry across** those lines.

### Achieving Alignment

Achieving alignment results from paying conscious attention to those imaginary lines. You should **draw those lines during the wireframing stage** for each page or view. You don't need to _literally_ draw the lines, but make sure you could draw them if you wanted to.

![Screen%20Shot%202021-08-29%20at%207.51.13%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388975/preview)

A very common pattern for achieving alignment in a web application is to ensure you've got **consistent margins**. For example, let's say you've got a header, a main block of content, and a footer. Impose a maximum width for the total content of the page—then make sure the left edges of each content container line up with all the rest, and likewise with the right edges. Then do the same for the **vertical space** (padding + margin) within and between each container. See how we can draw lines here?

![Screen%20Shot%202021-08-29%20at%207.55.21%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388976/preview)

## Proportion

### What's Proportion?

**Proportion** is **balance in scale**.

Remember how we said balance would apply everywhere? Proportion is explicitly a balance property of scale—is there balance in the way elements scale?

**Scale** is when the same or similar elements change size or show up in different sizes.

So for proportion, we want similar elements that change size or show up in different sizes to do so in a balanced way.

![Screen%20Shot%202021-08-29%20at%207.59.05%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388977/preview)

### Using Proportion

One way to work to achieve proportion in your product is to ensure **responsiveness**. Responsive design attempts to adjust content fluidly as the screen size changes. You could call this an example of **dynamic** proportion.

Another way to work toward proportion is with what you might call **static** proportion. If one set of elements shows up in multiple places in different sizes, the way that size has changed across instances should be consistent and balanced.

## Hierarchy

### What's Hierarchy?

**Hierarchy** is the effective management of **layers of abstraction**.

Ok—_what on earth does that mean_?

You're certainly familiar with the notion of hierarchy in other contexts—you've got multiple levels of something, from top to bottom. Maybe it's a filesystem with folders containing folders. Perhaps it's an organization with a CEO on the first level, then a COO on the second level, then Vice Presidents on the third level...

![Screen%20Shot%202021-08-29%20at%208.02.25%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388978/preview)

This is the _concept_ of hierarchy, and a chart like the above is one way to illustrate hierarchy visually as well.

### Using Hierarchy

Really, though, hierarchy goes way beyond that in design. For example, think about heading levels in HTML or a text editor—this is a form of hierarchy, right?

![Screen%20Shot%202021-08-29%20at%208.05.26%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388979/preview)

To leverage hierarchy effectively in design, **think about how you can organize—first conceptually, then visually—your content into layers of abstraction.**

This also includes **the actions a user can take** on the page—maybe there's one main, "primary" action they can take, a few still-significant "secondary" actions they can take... how can you make this hierarchy of action importance clear to your user?

## Emphasis

### What's Emphasis?

**Emphasis** is effectively directing your users' attention.

What word in this sentence are you **drawn** to? Does reading this **sentence** feel natural?

You can influence where your users direct their attention in many ways—some quite subtle.

### Using Emphasis

Emphasis isn't just emphasizing words with tools like font size and weight, italics, and underlining. It's also the choices you make about what visual elements to include where, the use of color, the use of borders, and the incorporation of all the other principles of design to consciously control the flow of attention.

For example, where is your attention drawn in the following image:

![Screen%20Shot%202021-08-29%20at%208.11.20%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388980/preview)

How about this one?

![Screen%20Shot%202021-08-29%20at%208.13.59%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388981/preview)

Notice how principles like hierarchy, proportion, and balance factor into leveraging emphasis to achieve your design goals.

## White Space

### What's White Space?

**White space** (or **negative space**) is the space between and around elements.

The concept of white space has been explored and leveraged by artists for millennia—the conscious use of "nothing" is a way to incorporate all the other design principles.

Notice how white space influences our attention and our perception in the following layout:

![Screen%20Shot%202021-08-29%20at%208.20.07%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388982/preview)

### Using White Space

The key to using white space is to remember to use it in the first place!

Since white space is the absence of an element, you can use it to direct your user's attention to the elements that \_are_present. Ensure there's enough space between elements to make each stand out (emphasis!), that your patterns of using white space are consistent (unity and balance!), and that any visual hierarchies (!) use spacing in predictable ways.
