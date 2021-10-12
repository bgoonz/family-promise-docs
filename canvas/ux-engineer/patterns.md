# Patterns

## What are Patterns?

### Design Patterns

A **design pattern** is a **recipe for a solution to a common problem**.

"Design pattern" is an overarching term covering more than just UI/UX design, and more than just software. For example, you'll probably hear the term most frequently in the context of approaching problems using object-oriented programming—and it has its origins in the realm of [architecture and civil engineering (Links to an external site.)](https://en.wikipedia.org/wiki/A_Pattern_Language).

Usually, you won't even see the term "design pattern" used to refer to UI/UX, since there are specific types of user interface and user experience patterns.

We're going to focus on those user-facing patterns here—approaches to recognizing common user situations, and accommodating them with well-established, repeatable solutions.



## UX Patterns

### UX Patterns: Modeling an Experience

Once we narrow our focus to UI/UX, the difference between a UX pattern and a UI pattern becomes subtle. Why is that?

Think about our definition of _pattern_—a recipe for a solution to a common problem.

So much of what we design and build for a user experience is via a user interface. So naturally, a pattern to solve a _user experience_ problem will often involve a _user interface_ pattern.

But let's start by considering the general ways we can understand and start to model a user _experience_—the knowledge we have about what drives positive product experiences.

### Jakob's Law

In 2000, Jakob Nielsen of the Nielsen Norman Group [posited (Links to an external site.)](https://www.nngroup.com/articles/end-of-web-design/):

> **Users spend most of their time on **_**other**_** sites.** This means that users prefer your site to work the same way as all the other sites they already know.

Note that Nielsen isn't just talking about the way websites _look_—he's referring to how they _work_. In other words, in general, a user's experience with a website will be better if they don't have to learn new ways to interact with it. What's the takeaway here? **Use UX patterns!**

Naturally, there's [some controversy (Links to an external site.)](https://medium.cobeisfresh.com/jakobs-law-e368d03c7636) about taking Jakob's Law to its absolute conclusion. If we all want users to avoid having to experience different sites differently, then will all websites end up exactly the same?

Nonetheless, when you're designing a product and thinking about your user's experience, it can be a very useful rule of thumb: _**don't reinvent the wheel**_. Default to the "boring" way to let your user experience your product—_then_ think about ways to tweak that experience if it makes sense for your product's goals.

### The Hook Model

In his influential 2014 book _Hooked: How to Build Habit-Forming Products_, Nir Eyal proposed [**the Hook Model (Links to an external site.)**](https://www.nirandfar.com/how-to-manufacture-desire/).

The Hook model divides a user's interaction and experience with a product into four phases:

1. A trigger to start using it
2. An action that "satisfies" the trigger
3. A reward for the action
4. An "investment" that makes the product more valuable to the user

Taken together, these phases of the Hook Model are a UX pattern. We're predicting ways that users will become engaged with our product via an experience we can engineer.

One thing to note here, however—the Hook Model focuses on optimizing products for _engagement_—it doesn't necessarily optimize products for _quality_. In any case, though, keep it in mind as a valuable way to build a product experience that will keep users coming back.

### Gamification

**Gamification** is incorporating game-like reward features into a product that isn't nominally a game.

One example of gamification is the Wikimedia Foundation's [donation badges (Links to an external site.)](https://donate.wikimedia.org/wiki/Template:DonationBadges)—users who donate get recognized with a public badge (this also incorporates another useful concept: **social proof**—giving your users examples of other people using your product in a certain way to encourage them to do so, too). Another frequent example is giving users points for completing certain actions, like filling in their profile information.

To drive positive product experiences, you'll want to ensure you're **motivating** your users, not manipulating them—and that you're not relying on gamification alone to make the user experience great.

### The List Goes On...

There are hundreds of UX patterns out there, like:

* ways to give feedback to the user
* ways to increase or decrease choices for the user
* ways to rely on or assist users' memory

If you want to read more about UX patterns, check out [**Laws of UX (Links to an external site.)**](https://lawsofux.com), a really cool site laying out a bunch of research-driven UX principles and best practices.

We've barely scratched the surface—but hopefully, these examples give you an idea of the work that has been done to understand user experiences, and to synthesize that knowledge into formulas for product success.





## UI Patterns

### UI Patterns: Implementing Paradigms

Now that we've examined general approaches to user experience problems, we can take some of those **paradigms**—models for thinking about things—and see how we can implement them via user interfaces.

### Common UI Patterns

These frequently-used UI patterns combine structure, organization, and interaction behavior to meet users where they are and provide predictable, minimum-friction experiences. You'll almost certainly immediately recognize them!

#### Pagination

**Pagination** is splitting content up into pages. These aren't necessary separate screens or webpages—you'll usually deal with pagination when you're working with tables:

![Screen%20Shot%202021-08-29%20at%208.27.19%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388983/preview)

Pagination helps us avoid putting too much information in front of our users at once.

Note that to implement pagination, your product will often need to adjust the way it queries a database—we'll probably only want to retrieve the "page" of data we're interested in displaying. This is called **query pagination**. Pagination is thus a great example of how designing a user interface based on a user experience can result in a full-stack engineering feature—the frontend and the backend will need to accommodate paginated queries in order to present this experience to the user.

#### Progressive Disclosure

**Progressive disclosure** is waiting to show content and/or prompt the user for action until it's needed. As the user continues toward a goal, they complete the process gradually. Pagination is an example of progressive disclosure!

Another example of progressive disclosure is using **lazy forms**—forms whose fields only appear once the user has filled in the previous field (or set of fields):

![Screen%20Shot%202021-08-29%20at%208.35.39%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388984/preview)

A related concept is using **wizards**—walking the user through a process, with input fields or other required actions showing over multiple pages or screens:

![Screen%20Shot%202021-08-29%20at%208.39.19%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388985/preview)

Progressive disclosure prevents users from being intimidated by having to go through a lot of information or perform a lot of actions at once.

#### Breadcrumbs

**Breadcrumbs** are a very common UI pattern where we display a "secondary" navigation system to the user based on where they are in a hierarchy of pages or screens.

Note the breadcrumbs below (`New Items` → `Popular` → `On Sale`):

![Screen%20Shot%202021-08-29%20at%208.46.56%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388986/preview)

Breadcrumbs both **orient the user** and allow them to **navigate in context**.

In order to be usefully orienting, breadcrumbs should be based on the actual page or screen hierarchy (the way the content is actually organized) rather than whatever way the user has happened to navigate around (their **history**). That's because showing the hierarchy gives the user more information about how your product's content is structured.

#### Empty States

**Empty states** are an extremely useful pattern that tells the user: "There's nothing here _right now_—but there could be!"

![Screen%20Shot%202021-08-29%20at%208.52.28%20PM.png](https://lambdaschool.instructure.com/courses/1562/files/388987/preview)

Empty states are highly orienting for users, because it tells them both how they should be interacting with your product, and what to expect both in the short term and the long term.

If your users will land on a screen where data _could_ be displayed, but there currently isn't anything to show them—you'll _almost certainly_ want to show them an empty state.

### Further Reading

There's no way we could list out all the possible UI patterns available—there are probably thousands!

To see more and learn more about UI patterns, check out these resources:

* [**ui-patterns.com (Links to an external site.)**](http://ui-patterns.com): A library of UI design patterns
* [**uipatterns.io (Links to an external site.)**](http://uipatterns.io): An interactive list of UI design patterns
* [**Map UI Patterns (Links to an external site.)**](https://www.mapuipatterns.com): A big collection of UI design patterns specific to maps
