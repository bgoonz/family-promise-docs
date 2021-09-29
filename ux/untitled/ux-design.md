# UX-Design

## Accessibility:

This checklist uses [The Web Content Accessibility Guidelines \(WCAG\)](https://www.w3.org/WAI/standards-guidelines/wcag/) as a reference point. The WCAG is a shared standard for web content accessibility for individuals, organizations, and governments.

There are three levels of accessibility compliance in the WCAG, which reflect the priority of support:

![](https://www.a11yproject.com/img/checklist/wcag-level-a-small.svg)

A: EssentialIf this isn't met, assistive technology may not be able to read, understand, or fully operate the page or view.

![](https://www.a11yproject.com/img/checklist/wcag-level-aa-small.svg)

AA: Ideal SupportRequired for [multiple government and public body websites](https://www.w3.org/WAI/policies/). The A11Y Project strives for AA compliance.

![](https://www.a11yproject.com/img/checklist/wcag-level-aaa-small.svg)

AAA: Specialized SupportThis is typically reserved for parts of websites and web apps that serve a specialized audience.

This checklist targets many, but not all level A and AA concerns. Note that the different levels of WCAG support do not necessarily indicate an increased level of difficulty to implement.

### Success criteria

Each item on this checklist has a corresponding WCAG "success criterion." Success criterion are the specific, testable rules that power the WCAG, described by a reference number and short title. For example, the rule about text resizing is called [1.4.4 Resize text](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html).

Some accessibility issues may have multiple success criterion apply to them. We have identified the one most relevant for each checklist item.

### Does this checklist guarantee my site is accessible?

No. However, addressing the issues called out in this checklist will help improve the experience for everyone who uses your site.

The issues this checklist prompts you to check for covers a wide range of disability conditions. There is no such thing as "perfect accessibility" or a site being "100% accessible." You should be wary of companies and services that make such promises. If you need professional accessibility help, use [professional accessibility services](https://www.a11yproject.com/resources/#professional-help).

### Content

Content is the most important part of your site.

Task: Use plain language and avoid figures of speech, idioms, and complicated metaphors.

Use plain language and avoid figures of speech, idioms, and complicated metaphors.

[3.1.5 READING LEVEL](https://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-supplements.html)

Write content at [an 8th grade reading level](https://datayze.com/readability-analyzer.php).

[SHARE LINKTO CHECKLIST ITEM: USE PLAIN LANGUAGE AND AVOID FIGURES OF SPEECH, IDIOMS, AND COMPLICATED METAPHORS.](https://www.a11yproject.com/checklist/#use-plain-language-and-avoid-figures-of-speech-idioms-and-complicated-metaphors)

Task: Make sure that `button`, `a`, and `label` element content is unique and descriptive.

Make sure that `button`, `a`, and `label` element content is unique and descriptive.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Terms like "click here" and "read more" do not provide any context. Some people navigate using a list of all buttons or links on a page or view. When using this mode, the terms indicate what will happen if navigated to or activated.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT `BUTTON`, `A`, AND `LABEL` ELEMENT CONTENT IS UNIQUE AND DESCRIPTIVE.](https://www.a11yproject.com/checklist/#make-sure-that-button-a-and-label-element-content-is-unique-and-descriptive)

Task: Use left-aligned text for left-to-right \(LTR\) languages, and right-aligned text for right-to-left \(RTL\) languages.

Use left-aligned text for left-to-right \(LTR\) languages, and right-aligned text for right-to-left \(RTL\) languages.

[1.4.8 VISUAL PRESENTATION](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Centered-aligned or justified text is difficult to read.

[SHARE LINKTO CHECKLIST ITEM: USE LEFT-ALIGNED TEXT FOR LEFT-TO-RIGHT \(LTR\) LANGUAGES, AND RIGHT-ALIGNED TEXT FOR RIGHT-TO-LEFT \(RTL\) LANGUAGES.](https://www.a11yproject.com/checklist/#use-left-aligned-text-for-left-to-right-ltr-languages-and-right-aligned-text-for-right-to-left-rtl-languages)

### Global code

Global code is code that affects your entire website or web app.

Task: Validate your HTML.

Validate your HTML.

Task: Use a `lang` attribute on the `html` element.

Use a `lang` attribute on the `html` element.

Task: Provide a unique `title` for each page or view.

Provide a unique `title` for each page or view.

Task: Ensure that viewport zoom is not disabled.

Ensure that viewport zoom is not disabled.

Task: Use landmark elements to indicate important content regions.

Use landmark elements to indicate important content regions.

[4.1.2 NAME, ROLE, VALUE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

[Landmark regions](https://www.w3.org/TR/wai-aria-practices/examples/landmarks/HTML5.html) help communicate the layout and important areas of a page or view, and can allow quick access to these regions. For example, use the `nav` element to wrap a site's navigation, and the `main` element to contain the primary content of a page.

[SHARE LINKTO CHECKLIST ITEM: USE LANDMARK ELEMENTS TO INDICATE IMPORTANT CONTENT REGIONS.](https://www.a11yproject.com/checklist/#use-landmark-elements-to-indicate-important-content-regions)

Task: Ensure a linear content flow.

Ensure a linear content flow.

[2.4.3 FOCUS ORDER](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-order.html)

Remove `tabindex` attribute values that aren't either `0` or `-1`. Elements that are inherently focusable, such as links or `button` elements, do not require a `tabindex`. Elements that are not inherently focusable should not have a `tabindex` applied to them outside of very specific use cases.

[SHARE LINKTO CHECKLIST ITEM: ENSURE A LINEAR CONTENT FLOW.](https://www.a11yproject.com/checklist/#ensure-a-linear-content-flow)

Task: Avoid using the `autofocus` attribute.

Avoid using the `autofocus` attribute.

[2.4.3 FOCUS ORDER](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-order.html)

People who are blind or who have low vision may be disoriented when focus is moved without their permission. Additionally, `autofocus` can be problematic for people with motor control disabilities, as it may create extra work for them to navigate out from the autofocused area and to other locations on the page/view.

[SHARE LINKTO CHECKLIST ITEM: AVOID USING THE `AUTOFOCUS` ATTRIBUTE.](https://www.a11yproject.com/checklist/#avoid-using-the-autofocus-attribute)

Task: Allow extending session timeouts

Allow extending session timeouts

[2.2.1 TIMING ADJUSTABLE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html)

If you cannot remove session timeouts altogether, then let the person using your site easily turn off, adjust, or extend their session well before it ends.

[SHARE LINKTO CHECKLIST ITEM: ALLOW EXTENDING SESSION TIMEOUTS](https://www.a11yproject.com/checklist/#allow-extending-session-timeouts)

Task: Remove `title` attribute tooltips.

Remove `title` attribute tooltips.

[4.1.2 NAME, ROLE, VALUE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

[The `title` attribute has numerous issues](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title#Accessibility_concerns), and should not be used if the information provided is important for all people to access. An acceptable use for the `title` attribute would be labeling an `iframe` element to indicate what content it contains.

[SHARE LINKTO CHECKLIST ITEM: REMOVE `TITLE` ATTRIBUTE TOOLTIPS.](https://www.a11yproject.com/checklist/#remove-title-attribute-tooltips)

### Keyboard

It is important that your interface and content can be operated, and navigated by use of a keyboard. Some people cannot use a mouse, or may be using other assistive technologies that may not allow for hovering or precise clicking.

Task: Make sure there is a visible focus style for interactive elements that are navigated to via keyboard input.

Make sure there is a visible focus style for interactive elements that are navigated to via keyboard input.

[2.4.7 FOCUS VISIBLE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-visible.html)

Can a person navigating with a keyboard, [switch](https://axesslab.com/switches/), voice control, or screen reader see where they currently are on the page?

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THERE IS A VISIBLE FOCUS STYLE FOR INTERACTIVE ELEMENTS THAT ARE NAVIGATED TO VIA KEYBOARD INPUT.](https://www.a11yproject.com/checklist/#make-sure-there-is-a-visible-focus-style-for-interactive-elements-that-are-navigated-to-via-keyboard-input)

Task: Check to see that keyboard focus order matches the visual layout.

Check to see that keyboard focus order matches the visual layout.

Task: Remove invisible focusable elements.

Remove invisible focusable elements.

### Images

Images are a very common part of most websites. Help make sure they can be enjoyed by all.

Task: Make sure that all `img` elements have an `alt` attribute.

Make sure that all `img` elements have an `alt` attribute.

[1.1.1 NON-TEXT CONTENT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

`alt` attributes \(alt text\) give a description of an image for people who may not be able to view them. When an `alt` attribute isn't present on an image, a screen reader may announce the image's file name and path instead. This fails to communicate the image's content.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT ALL `IMG` ELEMENTS HAVE AN `ALT` ATTRIBUTE.](https://www.a11yproject.com/checklist/#make-sure-that-all-img-elements-have-an-alt-attribute)

Task: Make sure that decorative images use null `alt` \(empty\) attribute values.

Make sure that decorative images use null `alt` \(empty\) attribute values.

[1.1.1 NON-TEXT CONTENT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

Null `alt` attributes are also sometimes known as empty `alt` attributes. They are made by including no information between the opening and closing quotes of an `alt` attribute. Decorative images do not communicate information that is required to understand the website's overall meaning. Historically they were used for flourishes and [spacer gif](https://en.wikipedia.org/wiki/Spacer_GIF) images, but tend to be less relevant for modern websites and web apps.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT DECORATIVE IMAGES USE NULL `ALT` \(EMPTY\) ATTRIBUTE VALUES.](https://www.a11yproject.com/checklist/#make-sure-that-decorative-images-use-null-alt-empty-attribute-values)

Task: Provide a text alternative for complex images such as charts, graphs, and maps.

Provide a text alternative for complex images such as charts, graphs, and maps.

[1.1.1 NON-TEXT CONTENT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

Is there a plain text which lists points on the map or sections of a flowchart? Describe all visible information. This includes graph axes, data points and labels, and the overall point the graphic is communicating.

[SHARE LINKTO CHECKLIST ITEM: PROVIDE A TEXT ALTERNATIVE FOR COMPLEX IMAGES SUCH AS CHARTS, GRAPHS, AND MAPS.](https://www.a11yproject.com/checklist/#provide-a-text-alternative-for-complex-images-such-as-charts-graphs-and-maps)

Task: For images containing text, make sure the alt description includes the image's text.

For images containing text, make sure the alt description includes the image's text.

[1.1.1 NON-TEXT CONTENT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

For example, the FedEx logo should have an alt value of "FedEx."

[SHARE LINKTO CHECKLIST ITEM: FOR IMAGES CONTAINING TEXT, MAKE SURE THE ALT DESCRIPTION INCLUDES THE IMAGE'S TEXT.](https://www.a11yproject.com/checklist/#for-images-containing-text-make-sure-the-alt-description-includes-the-images-text)

### Headings

Heading elements \(h1, h2, h3, etc.\) help break up the content of the page into related "chunks" of information. They are incredibly important for helping people who use assistive technology to understand the meaning of a page or view.

Task: Use heading elements to introduce content.

Use heading elements to introduce content.

[2.4.6 HEADINGS OR LABELS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)

Heading elements construct a document outline, and should not be used for purely visual design.

[SHARE LINKTO CHECKLIST ITEM: USE HEADING ELEMENTS TO INTRODUCE CONTENT.](https://www.a11yproject.com/checklist/#use-heading-elements-to-introduce-content)

Task: Use only one `h1` element per page or view.

Use only one `h1` element per page or view.

[2.4.6 HEADINGS OR LABELS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)

The `h1` element should be used to communicate the high-level purpose of the page or view. Do not use the `h1` element for a heading that does not change between pages or views \(for example, the site's name\).

[SHARE LINKTO CHECKLIST ITEM: USE ONLY ONE `H1` ELEMENT PER PAGE OR VIEW.](https://www.a11yproject.com/checklist/#use-only-one-h1-element-per-page-or-view)

Task: Heading elements should be written in a logical sequence.

Heading elements should be written in a logical sequence.

[2.4.6 HEADINGS OR LABELS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)

[The order of heading elements](https://webdesign.tutsplus.com/articles/the-importance-of-heading-levels-for-assistive-technology--cms-31753) should descend, based on the "depth" of the content. For example, a `h4` element should not appear on a page before the first `h3` element declaration. A tool such as [headingsMap](https://www.a11yproject.com/resources/#headingsmap) can help you evaluate this.

[SHARE LINKTO CHECKLIST ITEM: HEADING ELEMENTS SHOULD BE WRITTEN IN A LOGICAL SEQUENCE.](https://www.a11yproject.com/checklist/#heading-elements-should-be-written-in-a-logical-sequence)

Task: Don't skip heading levels.

Don't skip heading levels.

[2.4.6 HEADINGS OR LABELS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)

For example, don't jump from a `h2` to a `h4`, skipping a `h3` element. If heading levels are being skipped for a specific visual treatment, use CSS classes instead.

[SHARE LINKTO CHECKLIST ITEM: DON'T SKIP HEADING LEVELS.](https://www.a11yproject.com/checklist/#dont-skip-heading-levels)

### Lists

Lists elements let people know a collection of items are related and if they are sequential, and how many items are present in the list grouping.

Task: Use list elements \(`ol`, `ul`, and `dl` elements\) for list content.

Use list elements \(`ol`, `ul`, and `dl` elements\) for list content.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

This may include sections of related content, items visually displayed in a grid-like layout, or sibling a elements.

[SHARE LINKTO CHECKLIST ITEM: USE LIST ELEMENTS \(`OL`, `UL`, AND `DL` ELEMENTS\) FOR LIST CONTENT.](https://www.a11yproject.com/checklist/#use-list-elements-ol-ul-and-dl-elements-for-list-content)

### Controls

Controls are interactive elements such as links and buttons that let a person navigate to a destination or perform an action.

Task: Use the `a` element for links.

Use the `a` element for links.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Links should always have a `href` attribute, even when used in Single Page Applications \(SPAs\). Without a `href` attribute, the link will not be properly exposed to assistive technology. An example of this would be a link that uses an `onclick` event, in place of a `href` attribute.

[SHARE LINKTO CHECKLIST ITEM: USE THE `A` ELEMENT FOR LINKS.](https://www.a11yproject.com/checklist/#use-the-a-element-for-links)

Task: Ensure that links are recognizable as links.

Ensure that links are recognizable as links.

[1.4.1 USE OF COLOR](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

Color alone is not sufficient to indicate the presence of a link. Underlines are a popular and commonly-understood way to communicate the presence of link content.

[SHARE LINKTO CHECKLIST ITEM: ENSURE THAT LINKS ARE RECOGNIZABLE AS LINKS.](https://www.a11yproject.com/checklist/#ensure-that-links-are-recognizable-as-links)

Task: Ensure that controls have `:focus` states.

Ensure that controls have `:focus` states.

[2.4.7 FOCUS VISIBLE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-visible.html)

Visible focus styles help people determine which interactive element has keyboard focus. This lets them know that they can perform actions like activating a button or navigating to a link's destination.

[SHARE LINKTO CHECKLIST ITEM: ENSURE THAT CONTROLS HAVE `:FOCUS` STATES.](https://www.a11yproject.com/checklist/#ensure-that-controls-have-focus-states)

Task: Use the `button` element for buttons.

Use the `button` element for buttons.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Buttons are used to submit data or perform an on-screen action which does not shift keyboard focus. You can add `type="button"` to a `button` element to prevent the browser from attempting to submit form information when activated.

[SHARE LINKTO CHECKLIST ITEM: USE THE `BUTTON` ELEMENT FOR BUTTONS.](https://www.a11yproject.com/checklist/#use-the-button-element-for-buttons)

Task: Provide a skip link and make sure that it is visible when focused.

Provide a skip link and make sure that it is visible when focused.

[2.4.1 BYPASS BLOCKS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

A [skip link](https://www.a11yproject.com/posts/2013-05-11-skip-nav-links/) can be used to provide quick access to the main content of a page or view. This allows a person to easily bypass globally repeated content such as a website's primary navigation, or persistent search widget.

[SHARE LINKTO CHECKLIST ITEM: PROVIDE A SKIP LINK AND MAKE SURE THAT IT IS VISIBLE WHEN FOCUSED.](https://www.a11yproject.com/checklist/#provide-a-skip-link-and-make-sure-that-it-is-visible-when-focused)

Task: Identify links that open in a new tab or window.

Identify links that open in a new tab or window.

[G201: GIVING USERS ADVANCED WARNING WHEN OPENING A NEW WINDOW](https://www.w3.org/TR/WCAG20-TECHS/G201.html)

Ideally, avoid links that open in a new tab or window. If a link does, ensure the link's behavior will be communicated in a way that is apparent to all users. Doing this will help people understand what will happen before activating the link. While this technique is technically not required for compliance, it is an often-cited area of frustration for many different kinds of assistive technology users.

[SHARE LINKTO CHECKLIST ITEM: IDENTIFY LINKS THAT OPEN IN A NEW TAB OR WINDOW.](https://www.a11yproject.com/checklist/#identify-links-that-open-in-a-new-tab-or-window)

### Tables

Tables are a structured set of data that help people understand the relationships between different types of information.

Task: Use the `table` element to describe tabular data.

Use the `table` element to describe tabular data.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Do you need to display data in rows and columns? Use the `table` element.

[SHARE LINKTO CHECKLIST ITEM: USE THE `TABLE` ELEMENT TO DESCRIBE TABULAR DATA.](https://www.a11yproject.com/checklist/#use-the-table-element-to-describe-tabular-data)

Task: Use the `th` element for table headers \(with appropriate `scope` attributes\).

Use the `th` element for table headers \(with appropriate `scope` attributes\).

[4.1.1 PARSING](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-parses.html)

Depending on [how complex your table is](https://www.w3.org/WAI/tutorials/tables/), you may also consider using `scope="col"` for column headers, and `scope="row"` for row headers. Many different kinds of assistive technology still use the `scope` attribute to help them understand and describe the structure of a table.

[SHARE LINKTO CHECKLIST ITEM: USE THE `TH` ELEMENT FOR TABLE HEADERS \(WITH APPROPRIATE `SCOPE` ATTRIBUTES\).](https://www.a11yproject.com/checklist/#use-the-th-element-for-table-headers-with-appropriate-scope-attributes)

Task: Use the `caption` element to provide a title for the table.

Use the `caption` element to provide a title for the table.

[2.4.6 HEADINGS OR LABELS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)

The table's `caption` should describe what kind of information the table contains.

[SHARE LINKTO CHECKLIST ITEM: USE THE `CAPTION` ELEMENT TO PROVIDE A TITLE FOR THE TABLE.](https://www.a11yproject.com/checklist/#use-the-caption-element-to-provide-a-title-for-the-table)

### Forms

Forms allow people to enter information into a site for processing and manipulation. This includes things like sending messages and placing orders.

Task: All inputs in a form are associated with a corresponding `label` element.

All inputs in a form are associated with a corresponding `label` element.

[3.2.2 ON INPUT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-unpredictable-change.html)

Use a `for`/`id` pairing to guarantee the highest level of browser/assistive technology support.

[SHARE LINKTO CHECKLIST ITEM: ALL INPUTS IN A FORM ARE ASSOCIATED WITH A CORRESPONDING `LABEL` ELEMENT.](https://www.a11yproject.com/checklist/#all-inputs-in-a-form-are-associated-with-a-corresponding-label-element)

Task: Use `fieldset` and `legend` elements where appropriate.

Use `fieldset` and `legend` elements where appropriate.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Does your form contain multiple sections of related inputs? Use `fieldset` to group them, and `legend` to provide a label for what this section is for.

[SHARE LINKTO CHECKLIST ITEM: USE `FIELDSET` AND `LEGEND` ELEMENTS WHERE APPROPRIATE.](https://www.a11yproject.com/checklist/#use-fieldset-and-legend-elements-where-appropriate)

Task: Inputs use `autocomplete` where appropriate.

Inputs use `autocomplete` where appropriate.

[1.3.5 IDENTIFY INPUT PURPOSE](https://www.w3.org/WAI/WCAG21/Understanding/identify-input-purpose.html)

[Providing a mechanism](https://www.w3.org/TR/html52/sec-forms.html#sec-autofill) to help people more quickly, easily, and accurately fill in form fields that ask for common information \(for example, name, address, phone number\).

[SHARE LINKTO CHECKLIST ITEM: INPUTS USE `AUTOCOMPLETE` WHERE APPROPRIATE.](https://www.a11yproject.com/checklist/#inputs-use-autocomplete-where-appropriate)

Task: Make sure that form input errors are displayed in list above the form after submission.

Make sure that form input errors are displayed in list above the form after submission.

[3.3.1 ERROR IDENTIFICATION](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-identified.html)

This provides a way for assistive technology users to quickly have a high-level understanding of what issues are present in the form. This is especially important for larger forms with many inputs. Make sure that each reported error also has a link to the corresponding field with invalid input.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT FORM INPUT ERRORS ARE DISPLAYED IN LIST ABOVE THE FORM AFTER SUBMISSION.](https://www.a11yproject.com/checklist/#make-sure-that-form-input-errors-are-displayed-in-list-above-the-form-after-submission)

Task: Associate input error messaging with the input it corresponds to.

Associate input error messaging with the input it corresponds to.

[3.3.1 ERROR IDENTIFICATION](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-identified.html)

Techniques such as [using `aria-describedby`](https://developer.paciellogroup.com/blog/2018/09/describing-aria-describedby/) allow people who use assistive technology to more easily understand the difference between the input and the error message associated with it.

[SHARE LINKTO CHECKLIST ITEM: ASSOCIATE INPUT ERROR MESSAGING WITH THE INPUT IT CORRESPONDS TO.](https://www.a11yproject.com/checklist/#associate-input-error-messaging-with-the-input-it-corresponds-to)

Task: Make sure that error, warning, and success states are not visually communicated by just color.

Make sure that error, warning, and success states are not visually communicated by just color.

[1.4.1 USE OF COLOR](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

People who are color blind, who have other low vision conditions, or different cultural understandings for color may not see the state change, or understand what kind of feedback the state represents if color is the only indicator.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT ERROR, WARNING, AND SUCCESS STATES ARE NOT VISUALLY COMMUNICATED BY JUST COLOR.](https://www.a11yproject.com/checklist/#make-sure-that-error-warning-and-success-states-are-not-visually-communicated-by-just-color)

### Media

Media includes content such as pre-recorded and live audio and video.

Task: Make sure that media does not autoplay.

Make sure that media does not autoplay.

[1.4.2 AUDIO CONTROL](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-dis-audio.html)

Unexpected video and audio can be distracting and disruptive, especially for certain kinds of cognitive disability such as ADHD. Certain kinds of autoplaying video and animation can be a trigger for vestibular and seizure disorders.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE THAT MEDIA DOES NOT AUTOPLAY.](https://www.a11yproject.com/checklist/#make-sure-that-media-does-not-autoplay)

Task: Ensure that media controls use appropriate markup.

Ensure that media controls use appropriate markup.

[1.3.1 INFO AND RELATIONSHIPS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Examples include making sure an audio mute button has [a pressed toggle state](https://www.w3.org/WAI/PF/aria/states_and_properties#aria-pressed) when active, or that a volume slider uses `<input type="range">`.

[SHARE LINKTO CHECKLIST ITEM: ENSURE THAT MEDIA CONTROLS USE APPROPRIATE MARKUP.](https://www.a11yproject.com/checklist/#ensure-that-media-controls-use-appropriate-markup)

Task: Check to see that all media can be paused.

Check to see that all media can be paused.

[2.1.1 KEYBOARD](https://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation-keyboard-operable.html)

Provide a global pause function on any media element. If the device has a keyboard, ensure that pressing the `Space` key can pause playback. Make sure you also don't interfere with the `Space` key's ability to scroll the page/view when not focusing on a form control.

[SHARE LINKTO CHECKLIST ITEM: CHECK TO SEE THAT ALL MEDIA CAN BE PAUSED.](https://www.a11yproject.com/checklist/#check-to-see-that-all-media-can-be-paused)

### Video

Video-specific checks.

Task: Confirm the presence of captions.

Confirm the presence of captions.

[1.2.2 CAPTIONS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-captions.html)

Captions allow a person who cannot hear the audio content of a video to still understand its content.

[SHARE LINKTO CHECKLIST ITEM: CONFIRM THE PRESENCE OF CAPTIONS.](https://www.a11yproject.com/checklist/#confirm-the-presence-of-captions)

Task: Remove seizure triggers.

Remove seizure triggers.

[2.3.1 THREE FLASHES OR BELOW THRESHOLD](https://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure-does-not-violate.html)

Certain kinds of strobing or flashing animations will trigger seizures.

[SHARE LINKTO CHECKLIST ITEM: REMOVE SEIZURE TRIGGERS.](https://www.a11yproject.com/checklist/#remove-seizure-triggers)

### Audio

Audio-specific checks.

Task: Confirm that transcripts are available.

Confirm that transcripts are available.

[1.1.1 NON-TEXT CONTENT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

Transcripts allow people who cannot hear to still understand the audio content. It also allows people to digest audio content at a pace that is comfortable to them.

[SHARE LINKTO CHECKLIST ITEM: CONFIRM THAT TRANSCRIPTS ARE AVAILABLE.](https://www.a11yproject.com/checklist/#confirm-that-transcripts-are-available)

### Appearance

How your website app content looks in any given situation.

Task: Check your content in specialized browsing modes.

Check your content in specialized browsing modes.

[1.4.1 USE OF COLOR](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

Activate [modes such as Windows High Contrast or Inverted Colors](https://www.a11yproject.com/posts/2020-01-23-operating-system-and-browser-accessibility-display-modes/). Is your content still legible? Are your icons, borders, links, form fields, and other content still present? Can you distinguish foreground content from the background?

[SHARE LINKTO CHECKLIST ITEM: CHECK YOUR CONTENT IN SPECIALIZED BROWSING MODES.](https://www.a11yproject.com/checklist/#check-your-content-in-specialized-browsing-modes)

Task: Increase text size to 200%.

Increase text size to 200%.

[1.4.4 RESIZE TEXT](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Is the content still readable? Does increasing the text size cause content to overlap?

[SHARE LINKTO CHECKLIST ITEM: INCREASE TEXT SIZE TO 200%.](https://www.a11yproject.com/checklist/#increase-text-size-to-200percent)

Task: Double-check that good proximity between content is maintained.

Double-check that good proximity between content is maintained.

[1.3.3 SENSORY CHARACTERISTICS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-understanding.html)

Use [the straw test](https://www.youtube.com/watch?v=S1j6CYT3kWA&feature=youtu.be) to ensure people who depend on screen zoom software can still easily discover all content.

[SHARE LINKTO CHECKLIST ITEM: DOUBLE-CHECK THAT GOOD PROXIMITY BETWEEN CONTENT IS MAINTAINED.](https://www.a11yproject.com/checklist/#double-check-that-good-proximity-between-content-is-maintained)

Task: Make sure color isn't the only way information is conveyed.

Make sure color isn't the only way information is conveyed.

[1.4.1 USE OF COLOR](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-without-color.html)

Can you still see where links are among body content if everything is grayscale?

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE COLOR ISN'T THE ONLY WAY INFORMATION IS CONVEYED.](https://www.a11yproject.com/checklist/#make-sure-color-isnt-the-only-way-information-is-conveyed)

Task: Make sure instructions are not visual or audio-only.

Make sure instructions are not visual or audio-only.

[1.3.3 SENSORY CHARACTERISTICS](https://www.w3.org/WAI/WCAG21/Understanding/sensory-characteristics.html)

Use a combination of characteristics to write cues, particularly the actual names of sections and elements, rather than just descriptions like location \("on the right"\) or audio \("after the tone"\).

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE INSTRUCTIONS ARE NOT VISUAL OR AUDIO-ONLY.](https://www.a11yproject.com/checklist/#make-sure-instructions-are-not-visual-or-audio-only)

Task: Use a simple, straightforward, and consistent layout.

Use a simple, straightforward, and consistent layout.

[1.4.10 REFLOW](https://www.w3.org/WAI/WCAG21/Understanding/reflow.html)

A complicated layout can be confusing to understand and use.

[SHARE LINKTO CHECKLIST ITEM: USE A SIMPLE, STRAIGHTFORWARD, AND CONSISTENT LAYOUT.](https://www.a11yproject.com/checklist/#use-a-simple-straightforward-and-consistent-layout)

### Animation

Content that moves, either on its own, or when triggered by a person activating a control.

Task: Ensure animations are subtle and do not flash too much.

Ensure animations are subtle and do not flash too much.

[2.3.1 THREE FLASHES OR BELOW THRESHOLD](https://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure-does-not-violate.html)

Certain kinds of strobing or flashing animations will trigger seizures. Others may be distracting and disruptive, especially for certain kinds of cognitive disability such as ADHD.

[SHARE LINKTO CHECKLIST ITEM: ENSURE ANIMATIONS ARE SUBTLE AND DO NOT FLASH TOO MUCH.](https://www.a11yproject.com/checklist/#ensure-animations-are-subtle-and-do-not-flash-too-much)

Task: Provide a mechanism to pause background video.

Provide a mechanism to pause background video.

[2.2.2 PAUSE, STOP, HIDE](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-pause.html)

Background video can be distracting, especially if content is placed over it.

[SHARE LINKTO CHECKLIST ITEM: PROVIDE A MECHANISM TO PAUSE BACKGROUND VIDEO.](https://www.a11yproject.com/checklist/#provide-a-mechanism-to-pause-background-video)

Task: Make sure all animation obeys the `prefers-reduced-motion` media query.

Make sure all animation obeys the `prefers-reduced-motion` media query.

[2.3.3 ANIMATION FROM INTERACTIONS](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions.html)

Remove animations when the "reduce motion" setting is activated. If an animation is necessary to communicate meaning for a concept, slow its duration down.

[SHARE LINKTO CHECKLIST ITEM: MAKE SURE ALL ANIMATION OBEYS THE `PREFERS-REDUCED-MOTION` MEDIA QUERY.](https://www.a11yproject.com/checklist/#make-sure-all-animation-obeys-the-prefers-reduced-motion-media-query)

### Color contrast

[Color contrast](https://www.a11yproject.com/posts/2015-01-05-what-is-color-contrast/) is how legible colors are when placed next to, and on top of each other.

Task: Check the contrast for all normal-sized text.

Check the contrast for all normal-sized text.

[1.4.3 CONTRAST](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Level AA compliance requires a contrast ratio of 4.5:1.

[SHARE LINKTO CHECKLIST ITEM: CHECK THE CONTRAST FOR ALL NORMAL-SIZED TEXT.](https://www.a11yproject.com/checklist/#check-the-contrast-for-all-normal-sized-text)

Task: Check the contrast for all large-sized text.

Check the contrast for all large-sized text.

[1.4.3 CONTRAST](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Level AA compliance requires a contrast ratio of 3:1.

[SHARE LINKTO CHECKLIST ITEM: CHECK THE CONTRAST FOR ALL LARGE-SIZED TEXT.](https://www.a11yproject.com/checklist/#check-the-contrast-for-all-large-sized-text)

Task: Check the contrast for all icons.

Check the contrast for all icons.

[1.4.11 NON-TEXT CONTRAST](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html)

Level AA compliance requires a contrast ratio of 3.0:1.

[SHARE LINKTO CHECKLIST ITEM: CHECK THE CONTRAST FOR ALL ICONS.](https://www.a11yproject.com/checklist/#check-the-contrast-for-all-icons)

Task: Check the contrast of borders for input elements \(text input, radio buttons, checkboxes, etc.\).

Check the contrast of borders for input elements \(text input, radio buttons, checkboxes, etc.\).

[1.4.11 NON-TEXT CONTRAST](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html)

Level AA compliance requires a contrast ratio of 3.0:1.

[SHARE LINKTO CHECKLIST ITEM: CHECK THE CONTRAST OF BORDERS FOR INPUT ELEMENTS \(TEXT INPUT, RADIO BUTTONS, CHECKBOXES, ETC.\).](https://www.a11yproject.com/checklist/#check-the-contrast-of-borders-for-input-elements-text-input-radio-buttons-checkboxes-etc)

Task: Check text that overlaps images or video.

Check text that overlaps images or video.

[1.4.3 CONTRAST](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Is text still legible?

[SHARE LINKTO CHECKLIST ITEM: CHECK TEXT THAT OVERLAPS IMAGES OR VIDEO.](https://www.a11yproject.com/checklist/#check-text-that-overlaps-images-or-video)

Task: Check custom `::selection` colors.

Check custom `::selection` colors.

[1.4.3 CONTRAST](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

Is the color contrast you set in your [`::selection` CSS declaration](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection) sufficient? Otherwise someone may not be able read it if they highlight it.

[SHARE LINKTO CHECKLIST ITEM: CHECK CUSTOM `::SELECTION` COLORS.](https://www.a11yproject.com/checklist/#check-custom-selection-colors)

### Mobile and touch

Things to check mobile experiences for.

Task: Check that the site can be rotated to any orientation.

Check that the site can be rotated to any orientation.

[1.3.4 ORIENTATION](https://www.w3.org/WAI/WCAG21/Understanding/orientation.html)

Does the site only allow portrait orientation?

[SHARE LINKTO CHECKLIST ITEM: CHECK THAT THE SITE CAN BE ROTATED TO ANY ORIENTATION.](https://www.a11yproject.com/checklist/#check-that-the-site-can-be-rotated-to-any-orientation)

Task: Remove horizontal scrolling.

Remove horizontal scrolling.

[1.4.10 REFLOW](https://www.w3.org/WAI/WCAG21/Understanding/reflow.html)

Requiring someone to scroll horizontally can be difficult for some, irritating for all.

[SHARE LINKTO CHECKLIST ITEM: REMOVE HORIZONTAL SCROLLING.](https://www.a11yproject.com/checklist/#remove-horizontal-scrolling)

Task: Ensure that button and link icons can be activated with ease.

Ensure that button and link icons can be activated with ease.

[2.5.5 TARGET SIZE](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)

It's good to make sure things like hamburger menus, social icons, gallery viewers, and other touch controls are usable by a wide range of hand and stylus sizes.

[SHARE LINKTO CHECKLIST ITEM: ENSURE THAT BUTTON AND LINK ICONS CAN BE ACTIVATED WITH EASE.](https://www.a11yproject.com/checklist/#ensure-that-button-and-link-icons-can-be-activated-with-ease)

Task: Ensure sufficient space between interactive items in order to provide a scroll area.

Ensure sufficient space between interactive items in order to provide a scroll area.

[2.4.1 BYPASS BLOCKS](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

Some people who experience motor control issues such as [hand tremors](https://axesslab.com/hand-tremors/) may have a very difficult time scrolling past interactive items which feature zero spacing.

[SHARE LINKTO CHECKLIST ITEM: ENSURE SUFFICIENT SPACE BETWEEN INTERACTIVE ITEMS IN ORDER TO PROVIDE A SCROLL AREA.](https://www.a11yproject.com/checklist/#ensure-sufficient-space-between-interactive-items-in-order-to-provide-a-scroll-area)

### Next steps

Remember to periodically check your site to ensure it is still accessible. The A11Y Project also strongly encourages you to verify your testing by [hiring a professional tester](https://www.a11yproject.com/resources/#professional-testers).

### Further reading

TetraLogical has a good in-depth, yet still [high-level explanation of the WCAG](https://tetralogical.com/articles/wcag-primer/). Check it out if you want to learn more about its history and principles.

[![InVision Design Forward Fund. Apply now.](https://www.a11yproject.com/img/sponsors/invision-design-forward-fund.svg)](https://www.invisionapp.com/design-forward-fund)[![Go make things. Learn Vanilla JavaScript. Get daily developer tips.](https://www.a11yproject.com/img/sponsors/go-make-things.svg)](https://vanillajsacademy.com/)[![Assistiv Labs. Instantly test with real screen readers and more. Get started.](https://www.a11yproject.com/img/sponsors/assistiv-labs.svg)](https://assistivlabs.com/?utm_source=the_a11y_project&utm_medium=sponsored_ad)[![Fable.](https://www.a11yproject.com/img/sponsors/fable.png)](https://makeitfable.com/?utm_source=partnerships&utm_medium=website&utm_campaign=a11yproject)[![A11Y Collective. Online courses in web accessibility. Increase your knowledge base and add accessible code, design, or content to your skill set. Sign up for a course.](https://www.a11yproject.com/img/sponsors/a11y-collective.svg)](https://a11y-collective.com/?utm_medium=website&utm_source=a11y_project&utm_campaign=banner)[![Be Inclusive. Tired of tracking audits in spreadsheets? Focus on what really matters, let us simplify the rest. Try it free for a week!](https://www.a11yproject.com/img/sponsors/be-inclusive.svg)](https://beinclusive.app/?mtm_campaign=Sponsorship&mtm_kwd=A11yProject)[![Sponsor The A11Y Project. Learn how.](https://www.a11yproject.com/img/sponsors/sponsor-the-a11y-project.svg)](https://www.a11yproject.com/sponsorship/)

### FEATURES

* [Posts](https://www.a11yproject.com/posts/)
* [Checklist](https://www.a11yproject.com/checklist/)
* [Resources](https://www.a11yproject.com/resources/)
* [About](https://www.a11yproject.com/about/)
* [Contribute](https://www.a11yproject.com/contribute/)

### PROJECT

* [Values](https://www.a11yproject.com/values/)
* [Team](https://www.a11yproject.com/team/)
* [Authors](https://www.a11yproject.com/authors/)
* [Announcements](https://www.a11yproject.com/announcements/)
* [Spotlight](https://www.a11yproject.com/spotlight/)

### SITE

* [Code of Conduct](https://www.a11yproject.com/code-of-conduct/)
* [Accessibility Statement](https://www.a11yproject.com/accessibility-statement/)
* [Contributing Guidelines](https://www.a11yproject.com/contributing-guidelines/)
* [Content Style Guide](https://www.a11yproject.com/content-style-guide/)
* [Privacy and Security](https://www.a11yproject.com/privacy-and-security/)

### SOCIAL

* [Contact](https://www.a11yproject.com/contact/)
* [Twitter](https://twitter.com/A11YProject)
* [LinkedIn](https://www.linkedin.com/company/the-a11y-project/)
* [Newsletter](https://www.a11yproject.com/newsletter/)
* [RSS](https://www.a11yproject.com/feed/feed.xml)

### SUPPORT

* [Sponsorship](https://www.a11yproject.com/sponsorship/)
* [Open Collective](https://opencollective.com/the-a11y-project)
* [Write for Us](https://www.a11yproject.com/write-for-us/)
* [Good First Issues](https://github.com/a11yproject/a11yproject.com/issues?q=is%3Aissue+is%3Aopen+label%3A%22Good+First+Issue%22)
* [Project Roadmap](https://github.com/a11yproject/a11yproject.com/projects/1)

Accessibility helps everyone.

© 2013--2020 The Accessibility Project. [APLv2](https://www.apache.org/licenses/LICENSE-2.0). [Sitemap](https://www.a11yproject.com/sitemap.xml).

Powered by [Eleventy](https://www.11ty.io/), [Netlify](https://www.netlify.com/), and [GitHub](https://github.com/a11yproject/a11yproject.com).

[Back to top](https://www.a11yproject.com/checklist/#header)

