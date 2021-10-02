# Accessibility

## So what is accessibility?

Accessibility is the practice of making your websites usable by as many people as possible. We traditionally think of this as being about people with disabilities, but the practice of making sites accessible also benefits other groups such as those using mobile devices, or those with slow network connections.

You might also think of accessibility as treating everyone the same, and giving them equal opportunities, no matter what their ability or circumstances. Just as it is wrong to exclude someone from a physical building because they are in a wheelchair \(modern public buildings generally have wheelchair ramps or elevators\), it is also not right to exclude someone from a website because they have a visual impairment. We are all different, but we are all human, and therefore have the same human rights.

Accessibility is the right thing to do. Providing accessible sites is part of the law in some countries, which can open up some significant markets that otherwise would not be able to use your services or buy your products.

Building accessible sites benefit everyone:

* Semantic HTML, which improves accessibility, also improves SEO, making your site more findable.
* Caring about accessibility demonstrates good ethics and morals, which improves your public image.
* Other good practices that improve accessibility also make your site more usable by other groups, such as mobile phone users or those on low network speed. In fact, everyone can benefit from many such improvements.
* Did we mention it is also the law in some places?

### [What kinds of disability are we looking at?](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#what_kinds_of_disability_are_we_looking_at) <a id="what_kinds_of_disability_are_we_looking_at"></a>

People with disabilities are just as diverse as people without disabilities, and so are their disabilities. The key lesson here is to think beyond your own computer and how you use the web, and start learning about how others use it — _you are not your users_. The main types of disability to consider are explained below, along with any special tools they use to access web content \(known as **assistive technologies**, or **ATs**\).

**Note:** The World Health Organization's [Disability and health](https://www.who.int/en/news-room/fact-sheets/detail/disability-and-health) fact sheet states that "Over a billion people, about 15% of the world's population, have some form of disability", and "Between 110 million and 190 million adults have significant difficulties in functioning."

#### [People with visual impairments](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#people_with_visual_impairments) <a id="people_with_visual_impairments"></a>

People with visual impairments include people with blindness, low-level vision, and color blindness. Many people with visual impairments use screen magnifiers that are either physical magnifiers or software zoom capabilities. Most browsers and operating systems these days have zoom capabilities. Some users will rely on screen readers, which is software that reads digital text aloud. Some screen reader examples include:

* Paid commercial products, like [JAWS](https://www.freedomscientific.com/Products/software/JAWS/) \(Windows\) and [Dolphin Screen Reader](https://yourdolphin.com/screenreader) \(Windows\).
* Free products, like [NVDA](https://www.nvaccess.org/) \(Windows\), [ChromeVox](https://www.chromevox.com/) \(Chrome\), and [Orca](https://wiki.gnome.org/Projects/Orca) \(Linux\).
* Software built into the operating system, like [VoiceOver](https://www.apple.com/accessibility/mac/vision/) \(macOS, iPadOS, iOS\), [Narrator](https://support.microsoft.com/en-us/help/22798/windows-10-narrator-get-started) \(Windows\), [ChromeVox](https://www.chromevox.com/) \(on Chrome OS\), and [TalkBack](https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback) \(Android\).

It is a good idea to familiarize yourself with screen readers; you should also set up a screen reader and have a play around with it, to get an idea of how it works. See our [cross-browser testing screen readers guide](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#screenreaders) for more details on using them. The below video also provides a brief example of what the experience is like.

In terms of statistics, the World Health Organization estimates that "285 million people are estimated to be visually impaired worldwide: 39 million are blind and 246 million have low vision." \(see [Visual impairment and blindness](https://www.who.int/mediacentre/factsheets/fs282/en/)\). That's a large and significant population of users to just miss out on because your site isn't coded properly — almost the same size as the population of the United States of America.

#### [People with hearing impairments](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#people_with_hearing_impairments) <a id="people_with_hearing_impairments"></a>

[Deaf and hard-of-hearing \(DHH\)](https://www.nad.org/resources/american-sign-language/community-and-culture-frequently-asked-questions/) people have various levels of hearing loss ranging from mild to profound. Although some do use AT \(see [Assistive Devices for People with Hearing, Voice, Speech, or Language Disorders](https://www.nidcd.nih.gov/health/assistive-devices-people-hearing-voice-speech-or-language-disorders)\), they are not widespread..

To provide access, textual alternatives must be provided. Videos should be manually captioned, and transcripts should be provided for audio content. Furthermore, due to high levels of [language deprivation](https://therapytravelers.com/language-deprivation/#:~:text=Language%20deprivation%20is%20the%20term,therefore%20not%20exposed%20to%20language.) in DHH populations, [text simplification should be considered](https://circlcenter.org/collaborative-research-automatic-text-simplification-and-reading-assistance-to-support-self-directed-learning-by-deaf-and-hard-of-hearing-computing-workers/).

Deaf and hard-of-hearing people also represent a significant userbase — "466 million people worldwide have disabling hearing loss", says the World Health Organization's [Deafness and hearing loss](https://www.who.int/mediacentre/factsheets/fs300/en/) fact sheet.

#### [People with mobility impairments](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#people_with_mobility_impairments) <a id="people_with_mobility_impairments"></a>

These people have disabilities concerning movement, which might involve purely physical issues \(such as loss of limb or paralysis\), or neurological/genetic disorders that lead to weakness or loss of control in limbs. Some people might have difficulty making the exact hand movements required to use a mouse, while others might be more severely affected, perhaps being significantly paralyzed to the point where they need to use a [head pointer](https://www.performancehealth.com/baseball-cap-head-pointer) to interact with computers.

This kind of disability can also be a result of old age, rather than any specific trauma or condition, and it could also result from hardware limitations — some users might not have a mouse.

The way this usually affects web development work is the requirement that controls be accessible by the keyboard — we'll discuss keyboard accessibility in later articles in the module, but it is a good idea to try out some websites using just the keyboard to see how you get on. Can you use the Tab key to move between the different controls of a web form, for example? You can find more details about keyboard controls in our [Cross browser testing Using native keyboard accessibility](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#using_native_keyboard_accessibility) section.

In terms of statistics, a significant number of people have mobility impairments. The US Centers for Disease Control and Prevention [Disability and Functioning \(Non-institutionalized Adults 18 Years and Over\)](https://www.cdc.gov/nchs/fastats/disability.htm) reports the USA "Percent of adults with any physical functioning difficulty: 16.1%".

#### [People with cognitive impairments](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#people_with_cognitive_impairments) <a id="people_with_cognitive_impairments"></a>

Cognitive impairment refers to a broad range of disabilities, from people with intellectual disabilities who have the most-limited capabilities, to all of us as we age and have difficulty thinking and remembering. The range includes people with mental illnesses, such as [depression](https://www.nimh.nih.gov/health/topics/depression/index.shtml) and [schizophrenia](https://www.nimh.nih.gov/health/topics/schizophrenia/index.shtml). It also includes people with learning disabilities, such as [dyslexia](https://www.ninds.nih.gov/Disorders/All-Disorders/Learning-Disabilities-Information-Page) and [attention deficit hyperactivity disorder](https://www.nimh.nih.gov/health/topics/attention-deficit-hyperactivity-disorder-adhd/index.shtml). Importantly, though there is a lot of diversity within clinical definitions of cognitive impairments, people with them experience a common set of functional problems. These include difficulty with understanding content, remembering how to complete tasks, and confusion caused by inconsistent webpage layouts.

A good foundation of accessibility for people with cognitive impairments includes:

* Delivering content in more than one way, such as by text-to-speech or by video.
* Easily understood content, such as text written using plain-language standards.
* Focusing attention on important content.
* Minimizing distractions, such as unnecessary content or advertisements.
* Consistent webpage layout and navigation.
* Familiar elements, such as underlined links blue when not visited and purple when visited.
* Dividing processes into logical, essential steps with progress indicators.
* Website authentication as easy as possible without compromising security.
* Making forms easy to complete, such as with clear error messages and simple error recovery.

#### [Notes](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#notes) <a id="notes"></a>

* Designing with [cognitive accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Cognitive_accessibility) will lead to good design practices. They will benefit everyone.
* Many people with cognitive impairments also have physical disabilities. Websites must conform with the W3C’s [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/), including [cognitive accessibility guidelines](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Cognitive_accessibility#guidelines).
* The W3C’s [Cognitive and Learning Disabilities Accessibility Task Force](https://www.w3.org/WAI/GL/task-forces/coga/) produces web accessibility guidelines for people with cognitive impairments.
* WebAIM has a [Cognitive page](https://webaim.org/articles/cognitive/) of relevant information and resources.
* The United States Centers for Disease Control estimate that, as of 2018, 1 in 4 US citizens have a disability and, of them, [cognitive impairment is the most common for young people](https://www.cdc.gov/media/releases/2018/p0816-disability.html).
* In the US, some intellectual disabilities have historically been referred to as "mental retardation." Many now consider this term disparaging, so its use should be avoided.
* In the UK, some intellectual disabilities are referred to as "learning disabilities" or "learning difficulties".

### [Implementing accessibility into your project](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#implementing_accessibility_into_your_project) <a id="implementing_accessibility_into_your_project"></a>

A common accessibility myth is that accessibility is an expensive "added extra" to implement on a project. This myth actually _can_ be true if either:

* You are trying to "retrofit" accessibility onto an existing website that has significant accessibility issues.
* You have only started to consider accessibility and uncovered related issues in the late stages of a project.

If however, you consider accessibility from the start of a project, the cost of making most content accessible should be fairly minimal.

When planning your project, factor accessibility testing into your testing regime, just like testing for any other important target audience segment \(e.g., target desktop or mobile browsers\). Test early and often, ideally running automated tests to pick up on programmatically detectable missing features \(such as missing image [alternative text](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#text_alternatives) or bad link text — see [Element relationships and context](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#element_relationships_and_context)\) and doing some testing with disabled user groups to see how well more complex site features work for them. For example:

* Is my date picker widget usable by people using screen readers?
* If content updates dynamically, do visually impaired people know about it?
* Are my UI buttons accessible using the keyboard and on touch interfaces?

You can and should keep a note of potential problem areas in your content that will need work to make it accessible, make sure it is tested thoroughly, and think about solutions/alternatives. Text content \(as you'll see in the next article\) is easy, but what about your multimedia content, and your whizzy 3D graphics? You should look at your project budget and think about what solutions you have available to make such content accessible. Having all your multimedia content transcribed is one option which, while expensive, is possible.

Also, be realistic. "100% accessibility" is an unobtainable ideal — you will always come across some kind of edge case that results in a certain user finding certain content difficult to use — but you should do as much as you can. If you are planning to include a whizzy 3D pie chart graphic made using WebGL, you might want to include a data table as an accessible alternative representation of the data. Or, you might want to just include the table and get rid of the 3D pie chart — the table is accessible by everyone, quicker to code, less CPU-intensive, and easier to maintain.

On the other hand, if you are working on a gallery website showing interesting 3D art, it would be unreasonable to expect every piece of art to be perfectly accessible to visually impaired people, given that it is an entirely visual medium.

To show that you care and have thought about accessibility, publish an accessibility statement on your site that details what your policy is toward accessibility, and what steps you have taken toward making the site accessible. If someone does notify you that your site has an accessibility problem, start a dialog with them, be empathetic, and take reasonable steps to try to fix the problem.

**Note:** Our [Handling common accessibility problems article](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility) covers accessibility specifics that should be tested in more detail.

To summarize:

* Consider accessibility from the start of a project, and test early and often. Just like any other bug, an accessibility problem becomes more expensive to fix the later it is discovered.
* Bear in mind that a lot of accessibility best practices benefit everyone, not just users with disabilities. For example, lean semantic markup is not only good for screen readers, but it is also fast to load and performant. This benefits everyone, especially those on mobile devices and/or slow connections.
* Publish an accessibility statement on your site and engage with people having problems.

### [Accessibility guidelines and the law](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law) <a id="accessibility_guidelines_and_the_law"></a>

There are numerous checklists and sets of guidelines available for basing accessibility tests on, which might seem overwhelming at first glance. Our advice is to familiarize yourself with the basic areas in which you need to take care, as well as understanding the high-level structures of the guidelines that are most relevant to you.

* For a start, the W3C has published a large and very detailed document that includes very precise, technology-agnostic criteria for accessibility conformance. These are called the [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) \(WCAG\), and they are not a short read by any means. The criteria are split up into four main categories, which specify how implementations can be made perceivable, operable, understandable, and robust. The best place to get a light introduction and start learning is [WCAG at a Glance](https://www.w3.org/WAI/standards-guidelines/wcag/glance/). There is no need to learn all of the WCAG criteria — be aware of the major areas of concern, and use a variety of techniques and tools to highlight any areas that don't conform to the WCAG criteria \(see below for more\).
* Your country may also have specific legislation governing the need for websites serving their population to be accessible — for example [EN 301 549](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/02.01.02_60/en_301549v020102p.pdf) in the EU, [Section 508 of the Rehabilitation Act](https://www.section508.gov/training) in the US, [Federal Ordinance on Barrier-Free Information Technology](https://www.einfach-fuer-alle.de/artikel/bitv_english/) in Germany, the [Accessibility Regulations 2018](https://www.legislation.gov.uk/uksi/2018/952/introduction/made) in the UK, [Accessibilità](https://www.agid.gov.it/it/design-servizi/accessibilita-siti-web) in Italy, the [Disability Discrimination Act](https://www.humanrights.gov.au/world-wide-web-access-disability-discrimination-act-advisory-notes-ver-41-2014) in Australia, etc. The W3C keeps a list of [Web Accessibility Laws & Policies](https://www.w3.org/WAI/policies/) by country.

So while the WCAG is a set of guidelines, your country will probably have laws governing web accessibility, or at least the accessibility of services available to the public \(which could include websites, television, physical spaces, etc.\) It is a good idea to find out what your laws are. If you make no effort to check that your content is accessible, you could be legally liable if people complain.

This sounds serious, but really you just need to consider accessibility as the main priority of your web development practices, as outlined above. If in doubt, get advice from a qualified lawyer. We're not going to offer any more advice than this, because we're not lawyers.

### [Accessibility APIs](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis) <a id="accessibility_apis"></a>

Web browsers make use of special **accessibility APIs** \(provided by the underlying operating system\) that expose information useful for assistive technologies \(ATs\) — ATs mostly tend to make use of semantic information, so this information doesn't include things like styling information, or JavaScript. This information is structured in a tree of information called the **accessibility tree**.

Different operating systems have different accessibility APIs available :

* Windows: MSAA/IAccessible, UIAExpress, IAccessible2
* Mac OS X: NSAccessibility
* Linux: AT-SPI
* Android: Accessibility framework
* iOS: UIAccessibility

Where the native semantic information provided by the HTML elements in your web apps falls down, you can supplement it with features from the [WAI-ARIA specification](https://www.w3.org/TR/wai-aria/), which add semantic information to the accessibility tree to improve accessibility. You can learn a lot more about WAI-ARIA in our [WAI-ARIA basics](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics) article.

### [Summary](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#summary) <a id="summary"></a>

This article should have given you a useful high-level overview of accessibility, shown you why it's important, and looked at how you can fit it into your workflow. You should now also have a thirst to learn about the implementation details that can make sites accessible, and we'll start on that in the next section, looking at why HTML is a good basis for accessibility.





### [HTML and accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#html_and_accessibility) <a id="html_and_accessibility"></a>

As you learn more about HTML — read more resources, look at more examples, etc. — you'll keep seeing a common theme: the importance of using semantic HTML \(sometimes called POSH, or Plain Old Semantic HTML\). This means using the correct HTML elements for their intended purpose as much as possible.

You might wonder why this is so important. After all, you can use a combination of CSS and JavaScript to make just about any HTML element behave in whatever way you want. For example, a control button to play a video on your site could be marked up like this:

```text
<div>Play video</div>
```

Copy to Clipboard

But as you'll see in greater detail later on, it makes sense to use the correct element for the job:

```text
<button>Play video</button>
```

Copy to Clipboard

Not only do HTML `<button>`s have some suitable styling applied by default \(which you will probably want to override\), they also have built-in keyboard accessibility — users can navigate between buttons using the Tab key and activate their selection using Return or Enter.

Semantic HTML doesn't take any longer to write than non-semantic \(bad\) markup if you do it consistently from the start of your project. Even better, semantic markup has other benefits beyond accessibility:

1. **Easier to develop with** — as mentioned above, you get some functionality for free, plus it is arguably easier to understand.
2. **Better on mobile** — semantic HTML is arguably lighter in file size than non-semantic spaghetti code, and easier to make responsive.
3. **Good for SEO** — search engines give more importance to keywords inside headings, links, etc. than keywords included in non-semantic `<div>`s, etc., so your documents will be more findable by customers.

Let's get on and look at accessible HTML in more detail.

**Note:** It is a good idea to have a screen reader set up on your local computer so that you can do some testing of the examples shown below. See our [Screen readers guide](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#screenreaders) for more details.

### [Good semantics](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#good_semantics) <a id="good_semantics"></a>

We've already talked about the importance of proper semantics, and why we should use the right HTML element for the job. This cannot be ignored, as it is one of the main places that accessibility is badly broken if not handled properly.

Out there on the web, the truth is that people do some very strange things with HTML markup. Some abuses of HTML are due to legacy practices that have not been completely forgotten, and some are just plain ignorance. Whatever the case, you should replace such bad code.

Sometimes you are not in the position to get rid of lousy markup — your pages might be generated by some kind of server-side framework over which you don't have full control, or you might have third party content on your page \(such as ad banners\) over which you have no control.

The goal isn't "all or nothing"; every improvement you can make will help the cause of accessibility.

#### [Text content](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_content) <a id="text_content"></a>

One of the best accessibility aids a screen reader user can have is an excellent content structure with headings, paragraphs, lists, etc. An excellent semantic example might look something like the following:

```text
<h1>My heading</h1>

<p>This is the first section of my document.</p>

<p>I'll add another paragraph here too.</p>

<ol>
  <li>Here is</li>
  <li>a list for</li>
  <li>you to read</li>
</ol>

<h2>My subheading</h2>

<p>This is the first subsection of my document. I'd love people to be able to find this content!</p>

<h2>My 2nd subheading</h2>

<p>This is the second subsection of my content. I think is more interesting than the last one.</p>
```

Copy to Clipboard

We've prepared a version with longer text for you to try out with a screen reader \(see [good-semantics.html](https://mdn.github.io/learning-area/accessibility/html/good-semantics.html)\). If you try navigating through this, you'll see that this is pretty easy to navigate:

1. The screen reader reads each header out as you progress through the content, notifying you what a heading is, what is a paragraph, etc.
2. It stops after each element, letting you go at whatever pace is comfortable for you.
3. You can jump to the next/previous heading in many screen readers.
4. You can also bring up a list of all headings in many screen readers, allowing you to use them as a handy table of contents to find specific content.

People sometimes write headings, paragraphs, etc. using presentational HTML and line breaks, something like the following:

```text
<font size="7">My heading</font>
<br><br>
This is the first section of my document.
<br><br>
I'll add another paragraph here too.
<br><br>
1. Here is
<br><br>
2. a list for
<br><br>
3. you to read
<br><br>
<font size="5">My subheading</font>
<br><br>
This is the first subsection of my document. I'd love people to be able to find this content!
<br><br>
<font size="5">My 2nd subheading</font>
<br><br>
This is the second subsection of my content. I think is more interesting than the last one.
```

Copy to Clipboard

If you try our longer version out with a screen reader \(see [bad-semantics.html](https://mdn.github.io/learning-area/accessibility/html/bad-semantics.html)\), you'll not have a very good experience — the screen reader hasn't got anything to use as signposts, so you can't retrieve a useful table of contents, and the whole page is seen as a single giant block, so it is just read out in one go, all at once.

There are other issues too beyond accessibility — it is harder to style the content using CSS, or manipulate it with JavaScript, for example, because there are no elements to use as selectors.

**Using clear language**

The language you use can also affect accessibility. In general, you should use clear language that is not overly complex and doesn't use unnecessary jargon or slang terms. This not only benefits people with cognitive or other disabilities; it benefits readers for whom the text is not written in their first language, younger people ... everyone, in fact! Apart from this, you should try to avoid using language and characters that don't get read out clearly by the screen reader. For example:

* Don't use dashes if you can avoid it. Instead of writing 5–7, write 5 to 7.
* Expand abbreviations — instead of writing Jan, write January.
* Expand acronyms, at least once or twice. Instead of writing HTML in the first instance, write Hypertext Markup Language.

#### [Page layouts](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#page_layouts) <a id="page_layouts"></a>

In the bad old days, people used to create page layouts using HTML tables — using different table cells to contain the header, footer, sidebar, main content column, etc. This is not a good idea because a screen reader will likely give out confusing readouts, especially if the layout is complex and has many nested tables.

Try our example [table-layout.html](https://mdn.github.io/learning-area/accessibility/html/table-layout.html) example, which looks something like this:

```text
<table width="1200">
      <!-- main heading row -->
      <tr id="heading">
        <td colspan="6">

          <h1 align="center">Header</h1>

        </td>
      </tr>
      <!-- nav menu row  -->
      <tr id="nav" bgcolor="#ffffff">
        <td width="200">
          <a href="#" align="center">Home</a>
        </td>
        <td width="200">
          <a href="#" align="center">Our team</a>
        </td>
        <td width="200">
          <a href="#" align="center">Projects</a>
        </td>
        <td width="200">
          <a href="#" align="center">Contact</a>
        </td>
        <td width="300">
          <form width="300">
            <input type="search" name="q" placeholder="Search query" width="300">
          </form>
        </td>
        <td width="100">
          <button width="100">Go!</button>
        </td>
      </tr>
      <!-- spacer row -->
      <tr id="spacer" height="10">
        <td>

        </td>
      </tr>
      <!-- main content and aside row -->
      <tr id="main">
        <td id="content" colspan="4" bgcolor="#ffffff">

          <!-- main content goes here -->
        </td>
        <td id="aside" colspan="2" bgcolor="#ff80ff" valign="top">
          <h2>Related</h2>

          <!-- aside content goes here -->

        </td>
      </tr>
      <!-- spacer row -->
      <tr id="spacer" height="10">
        <td>

        </td>
      </tr>
      <!-- footer row -->
      <tr id="footer" bgcolor="#ffffff">
        <td colspan="6">
          <p>©Copyright 2050 by nobody. All rights reversed.</p>
        </td>
      </tr>
    </table>
```

Copy to Clipboard

If you try to navigate this using a screen reader, it will probably tell you that there's a table to be looked at \(although some screen readers can guess the difference between table layouts and data tables\). You'll then likely \(depending on which screen reader you're using\) have to go down into the table as an object and look at its features separately, then get out of the table again to carry on navigating the content.

Table layouts are a relic of the past — they made sense back when CSS support was not widespread in browsers, but now they just create confusion for screen reader users. Additionally, their source code requires more markup, which makes them less flexible and more difficult to maintain. You can verify these claims by comparing your previous experience with a [more modern website structure example](https://mdn.github.io/learning-area/html/introduction-to-html/document_and_website_structure/), which could look something like this:

```text
<header>
  <h1>Header</h1>
</header>

<nav>
  <!-- main navigation in here -->
</nav>

<!-- Here is our page's main content -->
<main>

  <!-- It contains an article -->
  <article>
    <h2>Article heading</h2>

    <!-- article content in here -->
  </article>

  <aside>
    <h2>Related</h2>

    <!-- aside content in here -->
  </aside>

</main>

<!-- And here is our main footer that is used across all the pages of our website -->

<footer>
  <!-- footer content in here -->
</footer>
```

Copy to Clipboard

If you try our more modern structure example with a screen reader, you'll see that the layout markup no longer gets in the way and confuses the content readout. It is also much leaner and smaller in terms of code size, which means easier to maintain code, and less bandwidth for the user to download \(particularly prevalent for those on slow connections\).

Another consideration when creating layouts is using HTML5 semantic elements as seen in the above example \(see [content sectioning](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning)\) — you can create a layout using only nested [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements, but it is better to use appropriate sectioning elements to wrap your main navigation \([`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)\), footer \([`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)\), repeating content units \([`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)\), etc. These provide extra semantics for screen readers \(and other tools\) to give user extra clues about the content they are navigating \(see [Screen Reader Support for new HTML5 Section Elements](https://www.weba11y.com/blog/2016/04/22/screen-reader-support-for-new-html5-section-elements/) for an idea of what screen reader support is like\).

**Note:** In addition to having good semantics and an attractive layout, your content should make logical sense in its source order — you can always place it where you want using CSS later on, but you should get the source order right to start with, so what screen reader users get read out to them will make sense.

#### [UI controls](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#ui_controls) <a id="ui_controls"></a>

By UI controls, we mean the main parts of web documents that users interact with — most commonly buttons, links, and form controls. In this section, we'll look at the basic accessibility concerns to be aware of when creating such controls. Later articles on WAI-ARIA and multimedia will look at other aspects of UI accessibility.

One key aspect of the accessibility of UI controls is that by default, browsers allow them to be manipulated by the keyboard. You can try this out using our [native-keyboard-accessibility.html](https://mdn.github.io/learning-area/tools-testing/cross-browser-testing/accessibility/native-keyboard-accessibility.html) example \(see the [source code](https://github.com/mdn/learning-area/blob/master/tools-testing/cross-browser-testing/accessibility/native-keyboard-accessibility.html)\). Open this in a new tab, and try pressing the tab key; after a few presses, you should see the tab focus start to move through the different focusable elements. The focused elements are given a highlighted default style in every browser \(it differs slightly between different browsers\) so that you can tell what element is focused.

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/button-focused-unfocused.png)

From Firefox 84 you can also enable an overlay that shows the page tabbing order. For more information see: [Accessibility Inspector &gt; Show web page tabbing order](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector#show_web_page_tabbing_order).

You can then press Enter/Return to follow a focused link or press a button \(we've included some JavaScript to make the buttons alert a message\), or start typing to enter text in a text input. Other form elements have different controls, for example, the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element can have its options displayed and cycled between using the up and down arrow keys.

**Note:** Different browsers may have different keyboard control options available. See [Using native keyboard accessibility](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#using_native_keyboard_accessibility) for more details.

You essentially get this behavior for free, just by using the appropriate elements, e.g.

```text
<h1>Links</h1>

<p>This is a link to <a href="https://www.mozilla.org">Mozilla</a>.</p>

<p>Another link, to the <a href="https://developer.mozilla.org">Mozilla Developer Network</a>.</p>

<h2>Buttons</h2>

<p>
  <button data-message="This is from the first button">Click me!</button>
  <button data-message="This is from the second button">Click me too!</button>
  <button data-message="This is from the third button">And me!</button>
</p>

<h2>Form</h2>

<form>
  <div>
    <label for="name">Fill in your name:</label>
    <input type="text" id="name" name="name">
  </div>
  <div>
    <label for="age">Enter your age:</label>
    <input type="text" id="age" name="age">
  </div>
  <div>
    <label for="mood">Choose your mood:</label>
    <select id="mood" name="mood">
      <option>Happy</option>
      <option>Sad</option>
      <option>Angry</option>
      <option>Worried</option>
    </select>
  </div>
</form>
```

Copy to Clipboard

This means using links, buttons, form elements, and labels appropriately \(including the [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) element for form controls\).

However, it is again the case that people sometimes do strange things with HTML. For example, you sometimes see buttons marked up using [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s, for example:

```text
<div data-message="This is from the first button">Click me!</div>
<div data-message="This is from the second button">Click me too!</div>
<div data-message="This is from the third button">And me!</div>
```

Copy to Clipboard

But using such code is not advised — you immediately lose the native keyboard accessibility you would have had if you'd just used [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements, plus you don't get any of the default CSS styling that buttons get.

**Building keyboard accessibility back in**

Adding such advantages back in takes a bit of work \(you can see an example in our [fake-div-buttons.html](https://mdn.github.io/learning-area/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html) example — also see the [source code](https://github.com/mdn/learning-area/blob/master/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html)\). Here we've given our fake `<div>` buttons the ability to be focused \(including via tab\) by giving each one the attribute `tabindex="0"`:

```text
<div data-message="This is from the first button" tabindex="0">Click me!</div>
<div data-message="This is from the second button" tabindex="0">Click me too!</div>
<div data-message="This is from the third button" tabindex="0">And me!</div>
```

Copy to Clipboard

Basically, the [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-tabindex) attribute is primarily intended to allow tabbable elements to have a custom tab order \(specified in positive numerical order\), instead of just being tabbed through in their default source order. This is nearly always a bad idea, as it can cause major confusion. Use it only if you really need to, for example, if the layout shows things in a very different visual order to the source code, and you want to make things work more logically. There are two other options for `tabindex`:

* `tabindex="0"` — as indicated above, this value allows elements that are not normally tabbable to become tabbable. This is the most useful value of `tabindex`.
* `tabindex="-1"` — this allows not normally tabbable elements to receive focus programmatically, e.g., via JavaScript, or as the target of links. 

Whilst the above addition allows us to tab to the buttons, it does not allow us to activate them via the Enter/Return key. To do that, we had to add the following bit of JavaScript trickery:

```text
document.onkeydown = function(e) {
  if(e.keyCode === 13) { // The Enter/Return key
    document.activeElement.click();
  }
};
```

Copy to Clipboard

Here we add a listener to the `document` object to detect when a button has been pressed on the keyboard. We check what button was pressed via the event object's [`keyCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode) property; if it is the keycode that matches Return/Enter, we run the function stored in the button's `onclick` handler using `document.activeElement.click()`. [`activeElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement) which gives us the element that is currently focused on the page.

This is a lot of extra hassle to build the functionality back in. And there's bound to be other problems with it. **Better to just use the right element for the right job in the first place.**

**Meaningful text labels**

UI control text labels are very useful to all users, but getting them right is particularly important to users with disabilities.

You should make sure that your button and link text labels are understandable and distinctive. Don't just use "Click here" for your labels, as screen reader users sometimes get up a list of buttons and form controls. The following screenshot shows our controls being listed by VoiceOver on Mac.

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/voiceover-formcontrols.png)

Make sure your labels make sense out of context, read on their own, as well as in the context of the paragraph they are in. For example, the following shows an example of good link text:

```text
<p>Whales are really awesome creatures. <a href="whales.html">Find out more about whales</a>.</p>
```

Copy to Clipboard

but this is bad link text:

```text
<p>Whales are really awesome creatures. To find more out about whales, <a href="whales.html">click here</a>.</p>
```

Copy to Clipboard

**Note:** You can find a lot more about link implementation and best practices in our [Creating hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks) article. You can also see some good and bad examples at [good-links.html](https://mdn.github.io/learning-area/accessibility/html/good-links.html) and [bad-links.html](https://mdn.github.io/learning-area/accessibility/html/bad-links.html).

Form labels are also important for giving you a clue about what you need to enter into each form input. The following seems like a reasonable enough example:

```text
Fill in your name: <input type="text" id="name" name="name">
```

Copy to Clipboard

However, this is not so useful for disabled users. There is nothing in the above example to associate the label unambiguously with the form input and make it clear how to fill it in if you cannot see it. If you access this with some screen readers, you may only be given a description along the lines of "edit text."

The following is a much better example:

```text
<div>
  <label for="name">Fill in your name:</label>
  <input type="text" id="name" name="name">
</div>
```

Copy to Clipboard

With code like this, the label will be clearly associated with the input; the description will be more like "Fill in your name: edit text."

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/voiceover-good-form-label.png)

As an added bonus, in most browsers associating a label with a form input means that you can click the label to select or activate the form element. This gives the input a bigger hit area, making it easier to select.

**Note:** you can see some good and bad form examples in [good-form.html](https://mdn.github.io/learning-area/accessibility/html/good-form.html) and [bad-form.html](https://mdn.github.io/learning-area/accessibility/html/bad-form.html).

You can find a nice explanation of the importance of proper text labels, and how to investigate text label issues using the [Firefox Accessibility Inspector](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector), in the following video:

### [Accessible data tables](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#accessible_data_tables) <a id="accessible_data_tables"></a>

A basic data table can be written with very simple markup, for example:

```text
<table>
  <tr>
    <td>Name</td>
    <td>Age</td>
    <td>Gender</td>
  </tr>
  <tr>
    <td>Gabriel</td>
    <td>13</td>
    <td>Male</td>
  </tr>
  <tr>
    <td>Elva</td>
    <td>8</td>
    <td>Female</td>
  </tr>
  <tr>
    <td>Freida</td>
    <td>5</td>
    <td>Female</td>
  </tr>
</table>
```

Copy to Clipboard

But this has problems — there is no way for a screen reader user to associate rows or columns together as groupings of data. To do this, you need to know what the header rows are and if they are heading up rows, columns, etc. This can only be done visually for the above table \(see [bad-table.html](https://mdn.github.io/learning-area/accessibility/html/bad-table.html) and try the example out yourself\).

Now have a look at our [punk bands table example](https://github.com/mdn/learning-area/blob/master/css/styling-boxes/styling-tables/punk-bands-complete.html) — you can see a few accessibility aids at work here:

* Table headers are defined using [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) elements — you can also specify if they are headers for rows or columns using the `scope` attribute. This gives you complete groups of data that can be consumed by screen readers as single units.
* The [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) element and `<table>` `summary` attribute both do similar jobs — they act as alt text for a table, giving a screen reader user a useful quick summary of the table's contents. The `<caption>` element is generally preferred as it makes it's content accessible to sighted users too, who might also find it useful. You don't really need both.

**Note:** See our [HTML table advanced features and accessibility](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced) article for more details about accessible data tables.

### [Text alternatives](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_alternatives) <a id="text_alternatives"></a>

Whereas textual content is inherently accessible, the same cannot necessarily be said for multimedia content — image and video content cannot be seen by visually-impaired people, and audio content cannot be heard by hearing-impaired people. We cover video and audio content in detail in the [Accessible multimedia](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia), but for this article we'll look at accessibility for the humble [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

We have a simple example written up, [accessible-image.html](https://mdn.github.io/learning-area/accessibility/html/accessible-image.html), which features four copies of the same image:

```text
<img src="dinosaur.png">

<img src="dinosaur.png"
     alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.">

<img src="dinosaur.png"
     alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth."
     title="The Mozilla red dinosaur">

<img src="dinosaur.png" aria-labelledby="dino-label">

<p id="dino-label">The Mozilla red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.</p>
```

Copy to Clipboard

The first image, when viewed by a screen reader, doesn't really offer the user much help — VoiceOver for example reads out "/dinosaur.png, image". It reads out the filename to try to provide some help. In this example the user will at least know it is a dinosaur of some kind, but often files may be uploaded with machine-generated file names \(e.g. from a digital camera\) and these file names would likely provide no context to the image's content.

**Note:** This is why you should never include text content inside an image — screen readers can't access it. There are other disadvantages too — you can't select it and copy/paste it. Just don't do it!

When a screen reader encounters the second image, it reads out the full alt attribute — "A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.".

This highlights the importance of not only using meaningful file names in case so-called **alt text** is not available, but also making sure that alt text is provided in `alt` attributes wherever possible. Note that the contents of the `alt` attribute should always provide a direct representation of the image and what it conveys visually. Any personal knowledge or extra description shouldn't be included here, as it is not useful for people who have not come across the image before.

One thing to consider is whether your images have meaning inside your content, or whether they are purely for visual decoration, and thus have no meaning. If they are decorative, it is better to write an empty text as a value for `alt` attribute \(see [Empty alt attributes](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#empty_alt_attributes)\) or to just include them in the page as CSS background images.

**Note:** Read [Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML) and [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) for a lot more information about image implementation and best practices.

If you do want to provide extra contextual information, you should put it in the text surrounding the image, or inside a `title` attribute, as shown above. In this case, most screen readers will read out the alt text, the title attribute, and the filename. In addition, browsers display title text as tooltips when moused over.

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/title-attribute.png)

Let's have another quick look at the fourth method:

```text
<img src="dinosaur.png" aria-labelledby="dino-label">

<p id="dino-label">The Mozilla red Tyrannosaurus ... </p>
```

Copy to Clipboard

In this case, we are not using the `alt` attribute at all — instead, we have presented our description of the image as a regular text paragraph, given it an `id`, and then used the `aria-labelledby` attribute to refer to that `id`, which causes screen readers to use that paragraph as the alt text/label for that image. This is especially useful if you want to use the same text as a label for multiple images — something that isn't possible with `alt`.

**Note:** `aria-labelledby` is part of the [WAI-ARIA](https://www.w3.org/TR/wai-aria-1.1/) spec, which allows developers to add in extra semantics to their markup to improve screen reader accessibility where needed. To find out more about how it works, read our [WAI-ARIA Basics](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics) article.

#### [Other text alternative mechanisms](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#other_text_alternative_mechanisms) <a id="other_text_alternative_mechanisms"></a>

Images also have another mechanisms available for providing descriptive text. For example, there is a `longdesc` attribute that is meant to point to a separate web document containing an extended description of the image, for example:

```text
<img src="dinosaur.png" longdesc="dino-info.html">
```

Copy to Clipboard

This sounds like a good idea, especially for infographics like big charts with lots of information on them that could perhaps be represented as an accessible data table instead \(see [Accessible data tables](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#accessible_data_tables)\). However, `longdesc` is not supported consistently by screen readers, and the content is completely inaccessible to non-screen reader users. It is arguably much better to include the long description on the same page as the image, or link to it with a regular link.

HTML5 includes two new elements — [`<figure>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure) and [`<figcaption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption) — which are supposed to associate a figure of some kind \(it could be anything, not necessarily an image\) with a figure caption:

```text
<figure>
  <img src="dinosaur.png" alt="The Mozilla Tyrannosaurus">
  <figcaption>A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.</figcaption>
</figure>
```

Copy to Clipboard

Unfortunately, most screen readers don't seem to associate figure captions with their figures yet. That said, the element structure is useful for CSS styling, plus it provides a way to place a description of the image next to it in the source.

#### [Empty alt attributes](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#empty_alt_attributes) <a id="empty_alt_attributes"></a>

```text
<h3>
  <img src="article-icon.png" alt="">
  Tyrannosaurus Rex: the king of the dinosaurs
</h3>
```

Copy to Clipboard

There may be times where an image is included in a page's design, but its primary purpose is for visual decoration. You'll notice in the code example above that the image's `alt` attribute is empty — this is to make screen readers recognize the image, but not attempt to describe the image \(instead they'd just say "image", or similar\).

The reason to use an empty `alt` instead of not including it is because many screen readers announce the whole image URL if no `alt` is provided. In the above example, the image is acting as a visual decoration to the heading it's associated with. In cases like this, and in cases where an image is only decoration and has no content value, you should include an empty `alt` in your `img` elements. Another alternative is to use the aria [`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles) attribute [`role="presentation"`](https://developer.mozilla.org/en-US/docs/Web/accessibility/ARIA/roles/presentation_role) as this also stops screen readers from reading out alternative text.

**Note:** if possible you should use CSS to display images that are only decorative.

### [More on links](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#more_on_links) <a id="more_on_links"></a>

Links \( the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element with an `href` attribute \), depending on how they are used, can help or harm accessibility. By default, links are accessible in appearance. They can improve accessibility by helping a user quickly navigate to different sections of a document. They can also harm accessibility if their accessible styling is removed or if JavaScript causes them to behave in unexpected ways.

#### [Link styling](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#link_styling) <a id="link_styling"></a>

By default, links are visually different from other text in both color and [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration), with links being blue and underlined by default, purple and underlined if visited, and with a [focus-ring](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) when they receive keyboard focus. 

Color should not be used as the sole method of distinguishing links from non-linking content. Link text color, like all text, has to be significantly different from the background color \([a 4.5:1 contrast](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable/Color_contrast)\). In addition, links should visually be significantly different from non-linking text. With a minimum contrast requirement of 3:1 between link text and surrounding text and between default, visited, and focus/active states and a 4:5 contrast between all those state colors and the background color.

#### [`onclick` events](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#onclick_events) <a id="onclick_events"></a>

Anchor tags are often abused with the `onclick` event to create pseudo-buttons by setting **href** to `"#"` or `"javascript:void(0)"` to prevent the page from refreshing.

These values cause unexpected behavior when copying or dragging links, opening links in a new tab or window, bookmarking, and when JavaScript is still downloading, errors out, or is disabled. This also conveys incorrect semantics to assistive technologies \(e.g., screen readers\). In these cases, it is recommended to use a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) instead. In general you should only use an anchor for navigation using a proper URL.

#### [External links and linking to non-HTML resources](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#external_links_and_linking_to_non-html_resources) <a id="external_links_and_linking_to_non-html_resources"></a>

Links that open in a new tab or window via the `target="_blank"` declaration and links to whose `href` value points to a file resource should include an indicator about the behavior that will occur when the link is activated.

People experiencing low vision conditions, who are navigating with the aid of screen reading technology, or who have cognitive concerns may become confused when the new tab, window, or application is opened unexpectedly. Older versions of screen reading software may not even announce the behavior.

**Link that opens a new tab or window**

```text
<a target="_blank" href="https://www.wikipedia.org/">Wikipedia (opens in a new window)</a>
```

Copy to Clipboard

**Link to a non-HTML resource**

```text
<a target="_blank" href="2017-annual-report.ppt">2017 Annual Report (PowerPoint)</a>
```

Copy to Clipboard

If an icon is used in place of text to signify this kind of links behavior, make sure it includes an [alternate description](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-alt).

* [WebAIM: Links and Hypertext - Hypertext Links](https://webaim.org/techniques/hypertext/hypertext_links)
* [MDN Understanding WCAG, Guideline 3.2 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.2_%E2%80%94_predictable_make_web_pages_appear_and_operate_in_predictable_ways)
* [G200: Opening new windows and tabs from a link only when necessary \| W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/G200.html)
* [G201: Giving users advanced warning when opening a new window \| W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/G201.html)

#### [Skip links](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#skip_links) <a id="skip_links"></a>

A skip link, also known as skipnav, is an `a` element placed as close as possible to the opening [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element that links to the beginning of the page's main content. This link allows people to bypass content repeated throughout multiple pages on a website, such as a website's header and primary navigation.

Skip links are especially useful for people who navigate with the aid of assistive technology such as switch control, voice command, or mouth sticks/head wands, where the act of moving through repetitive links can be a laborious task.

* [WebAIM: "Skip Navigation" Links](https://webaim.org/techniques/skipnav/)
* [How–to: Use Skip Navigation links - The A11Y Project](https://www.a11yproject.com/posts/2013-05-11-skip-nav-links/)
* [MDN Understanding WCAG, Guideline 2.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.4_%e2%80%94_navigable_provide_ways_to_help_users_navigate_find_content_and_determine_where_they_are)
* [Understanding Success Criterion 2.4.1 \| W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

#### [Proximity](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#proximity) <a id="proximity"></a>

Large amounts of interactive content—including anchors—placed in close visual proximity to each other should have space inserted to separate them. This spacing is beneficial for people who suffer from fine motor control issues and may accidentally activate the wrong interactive content while navigating.

Spacing may be created using CSS properties such as [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin).

* [Hand tremors and the giant-button-problem - Axess Lab](https://axesslab.com/hand-tremors/)

### [Test your skills!](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#test_your_skills!) <a id="test_your_skills!"></a>

You've reached the end of this article, but can you remember the most important information? See [Test your skills: HTML Accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Test_your_skills:_HTML_accessibility) to verify that you've retained this information before you move on.

### [Summary](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#summary) <a id="summary"></a>

You should now be well-versed in writing accessible HTML for most occasions. Our WAI-ARIA basics article will help to fill gaps in this knowledge, but this article has taken care of the basics. Next up we'll explore CSS and JavaScript, and how accessibility is affected by their good or bad use.



### [CSS and JavaScript are accessible?](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#css_and_javascript_are_accessible) <a id="css_and_javascript_are_accessible"></a>

CSS and JavaScript don't have the same immediate importance for accessibility as HTML, but they are still able to help or damage accessibility, depending on how they are used. To put it another way, it is important that you consider some best practice advice to make sure that your use of CSS and JavaScript doesn't ruin the accessibility of your documents.

### [CSS](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#css) <a id="css"></a>

Let's start off by looking at CSS.

#### [Correct semantics and user expectation](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#correct_semantics_and_user_expectation) <a id="correct_semantics_and_user_expectation"></a>

It is possible to use CSS to make any HTML element look like _anything_, but this doesn't mean that you should. As we frequently mentioned in our [HTML: A good basis for accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML) article, you should use the appropriate semantic element for the job, whenever possible. If you don't, it can cause confusion and usability issues for everyone, but particularly users with disabilities. Using correct semantics has a lot to do with user expectations — elements look and behave in certain ways, according to their functionality, and these common conventions are expected by users.

As an example, a screen reader user can't navigate a page via heading elements if the developer hasn't appropriately used heading elements to markup the content. By the same token, a heading loses its visual purpose if you style it so it doesn't look like a heading.

The rule of thumb is that you can update the styling of a page feature to fit in your design, but don't change it so much that it no longer looks or behaves as expected. The following sections summarize the main HTML features to consider.

**"Standard" text content structure**

Headings, paragraphs, lists — the core text content of your page:

```text
<h1>Heading</h1>

<p>Paragraph</p>

<ul>
  <li>My list</li>
  <li>has two items.</li>
</ul>
```

Copy to Clipboard

Some typical CSS might look like this:

```text
h1 {
  font-size: 5rem;
}

p, li {
  line-height: 1.5;
  font-size: 1.6rem;
}
```

Copy to Clipboard

You should:

* Select sensible font sizes, line heights, letter spacing, etc. to make your text logical, legible, and comfortable to read.
* Make sure your headings stand out from your body text, typically big and bold like the default styling. Your lists should look like lists.
* Your text color should contrast well with your background color.

See [HTML text fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals) and [Styling text](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text) for more information.

**Emphasised text**

Inline markup that confers specific emphasis to the text that it wraps:

```text
<p>The water is <em>very hot</em>.</p>

<p>Water droplets collecting on surfaces is called <strong>condensation</strong>.</p>
```

Copy to Clipboard

You might want to add some simple coloring to your emphasised text:

```text
strong, em {
  color: #a60000;
}
```

Copy to Clipboard

You will however rarely need to style emphasis elements in any significant way. The standard conventions of bold and italic text are very recognisable, and changing the style can cause confusion. For more on emphasis, see [Emphasis and importance](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#emphasis_and_importance).

**Abbreviations**

An element that allows an abbreviation, acronym, or initialization to be associated with its expansion:

```text
<p>Web content is marked up using <abbr title="Hypertext Markup Language">HTML</abbr>.</p>
```

Copy to Clipboard

Again, you might want to style it in some simple way:

```text
abbr {
  color: #a60000;
}
```

Copy to Clipboard

The recognized styling convention for abbreviations is a dotted underline, and it is unwise to significantly deviate from this. For more on abbreviations, see [Abbreviations](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#abbreviations).

**Links**

Hyperlinks — the way you get to new places on the web:

```text
<p>Visit the <a href="https://www.mozilla.org">Mozilla homepage</a>.</p>
```

Copy to Clipboard

Some very simple link styling is shown below:

```text
a {
  color: #ff0000;
}

a:hover, a:visited, a:focus {
  color: #a60000;
  text-decoration: none;
}

a:active {
  color: #000000;
  background-color: #a60000;
}
```

Copy to Clipboard

The standard link conventions are underlined and a different color \(default: blue\) in their standard state, another color variation when the link has previously been visited \(default: purple\), and yet another color when the link is activated \(default: red\). In addition, the mouse pointer changes to a pointer icon when links are moused over, and the link receives a highlight when focused \(e.g. via tabbing\) or activated. The following image shows the highlight in both Firefox \(a dotted outline\) and Chrome \(a blue outline\):

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/focus-highlight-firefox.png)

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/focus-highlight-chrome.png)

You can be creative with link styles, as long as you keep giving users feedback when they interact with the links. Something should definitely happen when states change, and you shouldn't get rid of the pointer cursor or the outline — both are very important accessibility aids for those using keyboard controls.

**Form elements**

Elements to allow users to input data into websites:

```text
<div>
  <label for="name">Enter your name</label>
  <input type="text" id="name" name="name">
</div>
```

Copy to Clipboard

You can see some good example CSS in our [form-css.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/form-css.html) example \([see it live](https://mdn.github.io/learning-area/accessibility/css/form-css.html) also\).

Most of the CSS you'll write for forms will be for sizing the elements, lining up labels and inputs, and getting them looking neat and tidy.

You shouldn't however deviate too much from the expected visual feedback form elements receive when they are focused, which is basically the same as links \(see above\). You could style form focus/hover states to make this behavior more consistent across browsers or fit in better with your page design, but don't get rid of it altogether — again, people rely on these clues to help them know what is going on.

**Tables**

Tables for presenting tabular data.

You can see a good, simple example of table HTML and CSS in our [table-css.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/table-css.html) example \([see it live also](https://mdn.github.io/learning-area/accessibility/css/table-css.html)\).

Table CSS generally serves to make the table fit better into your design and look less ugly. It is a good idea to make sure the table headers stand out \(normally using bold\), and use zebra striping to make different rows easier to parse.

#### [Color and color contrast](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#color_and_color_contrast) <a id="color_and_color_contrast"></a>

When choosing a color scheme for your website, make sure that the text \(foreground\) color contrasts well with the background color. Your design might look cool, but it is no good if people with visual impairments like color blindness can't read your content.

There is an easy way to check whether your contrast is large enough to not cause problems. There are a number of contrast checking tools online that you can enter your foreground and background colors into, to check them. For example WebAIM's [Color Contrast Checker](https://webaim.org/resources/contrastchecker/) is simple to use, and provides an explanation of what you need to conform to the WCAG criteria around color contrast.

**Note:** A high contrast ratio will also allow anyone using a smartphone or tablet with a glossy screen to better read pages when in a bright environment, such as sunlight.

Another tip is to not rely on color alone for signposts/information, as this will be no good for those who can't see the color. Instead of marking required form fields in red, for example, mark them with an asterisk and in red.

#### [Hiding things](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#hiding_things) <a id="hiding_things"></a>

There are many instances where a visual design will require that not all content is shown at once. For example, in our [Tabbed info box example](https://mdn.github.io/learning-area/css/css-layout/practical-positioning-examples/info-box.html) \(see [source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/practical-positioning-examples/info-box.html)\) we have three panels of information, but we are [positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning) them on top of one another and providing tabs that can be clicked to show each one \(it is also keyboard accessible — you can alternatively use Tab and Enter/Return to select them\).

![](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/tabbed-info-box.png)

Screen reader users don't care about any of this — they are happy with the content as long as the source order makes sense, and they can get to it all. Absolute positioning \(as used in this example\) is generally seen as one of the best mechanisms of hiding content for visual effect, because it doesn't stop screen readers from getting to it.

On the other hand, you shouldn't use [`visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility)`:hidden` or [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)`:none`, because they do hide content from screen readers. Unless of course, there is a good reason why you want this content to be hidden from screen readers.

**Note:** [Invisible Content Just for Screen Reader Users](https://webaim.org/techniques/css/invisiblecontent/) has a lot more useful detail surrounding this topic.

#### [Accept that users can override styles](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#accept_that_users_can_override_styles) <a id="accept_that_users_can_override_styles"></a>

**Accept that users can override your styles**

It is possible for users to override your styles with their own custom styles, for example:

* See Sarah Maddox's [How to use a custom style sheet \(CSS\) with Firefox](https://www.itsupportguides.com/knowledge-base/computer-accessibility/how-to-use-a-custom-style-sheet-css-with-firefox/) for a useful guide covering how to do this manually in Firefox, and [How to use a custom style sheet \(CSS\) with Internet Explorer](https://www.itsupportguides.com/knowledge-base/computer-accessibility/how-to-use-a-custom-style-sheet-css-with-internet-explorer/) by Adrian Gordon for the equivalent IE instructions.
* It is probably easier to do it using an extension, for example the Stylish extension is available for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/stylish/), [Safari](https://safari-extensions.apple.com/details/?id=com.sobolev.stylish-5555L95H45), [Opera](https://addons.opera.com/en/extensions/details/stylish/), and [Chrome](https://chrome.google.com/webstore/detail/stylish/fjnbnpbmkenffdnngjfgmeleoegfcffe).

Users might do this for a variety of reasons. A visually impaired user might want to make the text bigger on all websites they visit, or a user with severe color deficiency might want to put all websites in high contrast colors that are easy for them to see. Whatever the need, you should be comfortable with this, and make your designs flexible enough so that such changes will work in your design. As an example, you might want to make sure your main content area can handle bigger text \(maybe it will start to scroll to allow it all to be seen\), and won't just hide it, or break completely.

### [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#javascript) <a id="javascript"></a>

JavaScript can also break accessibility, depending on how it is used.

Modern JavaScript is a powerful language, and we can do so much with it these days, from simple content and UI updates to fully-fledged 2D and 3D games. There is no rule that says all content has to be 100% accessible to all people — you just need to do what you can, and make your apps as accessible as possible.

Simple content and functionality is arguably easy to make accessible — for example text, images, tables, forms and push button that activate functions. As we looked at in our [HTML: A good basis for accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML) article, the key considerations are:

* Good semantics: Using the right element for the right job. For example, making sure you use headings and paragraphs, and [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) and [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements
* Making sure content is available as text, either directly as text content, good text labels for form elements, or [text alternatives](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_alternatives), e.g. alt text for images.

We also looked at an example of how to use JavaScript to build in functionality where it is missing — see [Building keyboard accessibility back in](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in). This is not ideal — really you should just use the right element for the right job — but it shows that it is possible in situations where for some reason you can't control the markup that is used. Another way to improve accessibility for non-semantic JavaScript-powered widgets is to use WAI-ARIA to provide extra semantics for screen reader users. The next article will also cover this in detail.

Complex functionality like 3D games are not so easy to make accessible — a complex 3D game created using [WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) will be rendered on a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element, which has no facility at this time to provide text alternatives or other information for severely visually impaired users to make use of. It is arguable that such a game doesn't really have this group of people as a part of its main target audience, and it would be unreasonable to expect you to make it 100% accessible to blind people, however you could implement [keyboard controls](https://developer.mozilla.org/en-US/docs/Games/Techniques/Control_mechanisms/Desktop_with_mouse_and_keyboard) so it is usable by non-mouse users, and make the color scheme contrasting enough to be usable by those with color deficiencies.

#### [The problem with too much JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#the_problem_with_too_much_javascript) <a id="the_problem_with_too_much_javascript"></a>

The problem often comes when people rely on JavaScript too much. Sometimes you'll see a website where everything has been done with JavaScript — the HTML has been generated by JavaScript, the CSS has been generated by JavaScript, etc. This has all kinds of accessibility and other issues associated with it, so it is not advised.

As well as using the right element for the right job, you should also make sure you are using the right technology for the right job! Think carefully about whether you need that shiny JavaScript-powered 3D information box, or whether plain old text would do. Think carefully about whether you need a complex non-standard form widget, or whether a text input would do. And don't generate all your HTML content using JavaScript if at all possible.

#### [Keeping it unobtrusive](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#keeping_it_unobtrusive) <a id="keeping_it_unobtrusive"></a>

You should keep **unobtrusive JavaScript** in mind when creating your content. The idea of unobtrusive JavaScript is that it should be used wherever possible to enhance functionality, not build it in entirely — basic functions should ideally work without JavaScript, although it is appreciated that this is not always an option. But again, a large part of it is using built-in browser functionality where possible.

Good example uses of unobtrusive JavaScript include:

* Providing client-side form validation, which alerts users to problems with their form entries quickly, without having to wait for the server to check the data. If it isn't available, the form will still work, but validation might be slower.
* Providing custom controls for HTML5 `<video>`s that are accessible to keyboard-only users, along with a direct link to the video that can be used to access it if JavaScript is not available \(the default `<video>` browser controls aren't keyboard accessible in most browsers\).

As an example, we've written a quick and dirty client-side form validation example — see [form-validation.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/form-validation.html) \(also [see the demo live](https://mdn.github.io/learning-area/accessibility/css/form-validation.html)\). Here you'll see a simple form; when you try to submit the form with one or both fields left empty, the submit fails, and an error message box appears to tell you what is wrong.

This kind of form validation is unobtrusive — you can still use the form absolutely fine without the JavaScript being available, and any sensible form implementation will have server-side validation active as well, because it is too easy for malicious users to bypass client-side validation \(for example, by turning JavaScript off in the browser\). The client-side validation is still really useful for reporting errors — users can know about mistakes they make instantly, rather than having to wait for a round trip to the server and a page reload. This is a definite usability advantage.

**Note:** Server-side validation has not been implemented in this simple demo.

We've made this form validation pretty accessible too. We've used [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements to make sure the form labels are unambiguously linked to their inputs, so screen readers can read them out alongside:

```text
<label for="name">Enter your name:</label>
<input type="text" name="name" id="name">
```

Copy to Clipboard

We only do the validation when the form is submitted — this is so that we don't update the UI too often and potentially confuse screen reader \(and possibly other\) users:

```text
form.onsubmit = validate;

function validate(e) {
  errorList.innerHTML = '';
  for(let i = 0; i < formItems.length; i++) {
    const testItem = formItems[i];
    if(testItem.input.value === '') {
      errorField.style.left = '360px';
      createLink(testItem);
    }
  }

  if(errorList.innerHTML !== '') {
    e.preventDefault();
  }
}
```

Copy to Clipboard

**Note:** In this example, we are hiding and showing the error message box using absolute positioning rather than another method such as visibility or display, because it doesn't interfere with the screen reader being able to read content from it.

Real form validation would be much more complex than this — you'd want to check that the entered name actually looks like a name, the entered age is actually a number and is realistic \(e.g. nonnegative and less than 4 digits\). Here we've just implemented a simple check that a value has been filled in to each input field \(`if(testItem.input.value === '')`\).

When the validation has been performed, if the tests pass then the form is submitted. If there are errors \(`if(errorList.innerHTML !== '')`\) then we stop the form submitting \(using [`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)\), and display any error messages that have been created \(see below\). This mechanism means that the errors will only be shown if there are errors, which is better for usability.

For each input that doesn't have a value filled in when the form is submitted, we create a list item with a link and insert it in the `errorList`.

```text
function createLink(testItem) {
  const listItem = document.createElement('li');
  const anchor = document.createElement('a');

  anchor.textContent = testItem.input.name + ' field is empty: fill in your ' + testItem.input.name + '.';
  anchor.href = '#' + testItem.input.name;
  anchor.onclick = function() {
    testItem.input.focus();
  };
  listItem.appendChild(anchor);
  errorList.appendChild(listItem);
}
```

Copy to Clipboard

Each link serves a dual purpose — it tells you what the error is, plus you can click on it/activate it to jump straight to the input element in question and correct your entry.

**Note:** The `focus()` part of this example is a bit tricky. Chrome and Edge \(and newer versions of IE\) will focus the element when the link is clicked, without needing the `onclick`/`focus()` block. Safari will only highlight the form element with the link on its own, so needs the `onclick`/`focus()` block to actually focus it. Firefox doesn't focus the inputs properly at all in this context, so Firefox users can't take advantage of this at present \(although everything else works fine\). The Firefox issue should be fixed soon — work is being done to give Firefox behavior parity with other browsers \(see [bug 277178](https://bugzilla.mozilla.org/show_bug.cgi?id=277178)\).

In addition, the `errorField` is placed at the top of the source order \(although it is positioned differently in the UI using CSS\), meaning that users can find out exactly what's wrong with their form submissions and get to the input elements in question by going back up to the start of the page.

As a final note, we have used some WAI-ARIA attributes in our demo to help solve accessibility problems caused by areas of content constantly updating without a page reload \(screen readers won't pick this up or alert users to it by default\):

```text
<div class="errors" role="alert" aria-relevant="all">
  <ul>
  </ul>
</div>
```

We will explain these attributes in our next article, which covers [WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics) in much more detail.

**Note:** Some of you will probably be thinking about that fact that HTML5 forms have built-in validation mechanisms like the `required`, `min`/`minlength`, and `max`/`maxlength` attributes \(see the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element reference for more information\). We didn't end up using these in the demo because cross-browser support for them is patchy \(for example IE10 and above only\).

**Note:** WebAIM's [Usable and Accessible Form Validation and Error Recovery](https://webaim.org/techniques/formvalidation/) provides some further useful information about accessible form validation.

#### [Other JavaScript accessibility concerns](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#other_javascript_accessibility_concerns) <a id="other_javascript_accessibility_concerns"></a>

There are other things to be aware of when implementing JavaScript and thinking about accessibility. We will add more as we find them.

**mouse-specific events**

As you will be aware, most user interactions are implemented in client-side JavaScript using event handlers, which allow us to run functions in response to certain events happening. Some events can have accessibility issues. The main example you'll come across is mouse-specific events like [mouseover](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event), [mouseout](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event), [dblclick](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event), etc. Functionality that runs in response to these events will not be accessible using other mechanisms, like keyboard controls.

To mitigate such problems, you should double up these events with similar events that can be activated by other means \(so-called device-independent event handlers\) — [focus](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event) and [blur](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event) would provide accessibility for keyboard users.

Let's look at an example that highlights when this could be useful. Maybe we want to provide a thumbnail image that shows a larger version of the image when it is moused over or focused \(like you'd see on an e-commerce product catalog.\)

We've made a very simple example, which you can find at [mouse-and-keyboard-events.html](https://mdn.github.io/learning-area/accessibility/css/mouse-and-keyboard-events.html) \(see also the [source code](https://github.com/mdn/learning-area/blob/master/accessibility/css/mouse-and-keyboard-events.html)\). The code features two functions that show and hide the zoomed-in image; these are run by the following lines that set them as event handlers:

```text
imgThumb.onmouseover = showImg;
imgThumb.onmouseout = hideImg;

imgThumb.onfocus = showImg;
imgThumb.onblur = hideImg;
```

Copy to Clipboard

The first two lines run the functions when the mouse pointer hovers over and stops hovering over the thumbnail, respectively. This won't allow us to access the zoomed view by keyboard though — to allow that, we've included the last two lines, which run the functions when the image is focused and blurred \(when focus stops\). This can be done by tabbing over the image, because we've included `tabindex="0"` on it.

The [click](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) event is interesting — it sounds mouse-dependent, but most browsers will activate [onclick](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick) event handlers after Enter/Return is pressed on a link or form element that has focus, or when such an element is tapped on a touchscreen device. This doesn't work by default however when you allow a non-default-focusable event to have focus using tabindex — in such cases you need to detect specifically when that exact key is pressed \(see [Building keyboard accessibility back in](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in)\).

### [Test your skills!](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#test_your_skills!) <a id="test_your_skills!"></a>

You've reached the end of this article, but can you remember the most important information? You can find some further tests to verify that you've retained this information before you move on — see [Test your skills: CSS and JavaScript accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/Test_your_skills:_CSS_and_JavaScript_accessibility).





