---
title: Writing Accessible Technical Documentation
description: Learn how to create technical documentation that is accessible to users with disabilities, following WCAG guidelines and inclusive design principles.
---

# Writing for Accessibility

Accessible documentation works for everyone, including users with visual, auditory, motor, or cognitive disabilities. This is not optional—it is professional practice and often legal requirement.

Accessible writing also improves documentation for all users. Clear structure, plain language, and good contrast benefit everyone. Accessibility is not a separate concern; it is good documentation practice.

## Why Accessibility Matters

### The User Case

Millions of users rely on assistive technologies:

- Screen readers that convert text to speech
- Screen magnifiers for low vision users
- Voice control for users with motor disabilities
- Specialized displays for deaf-blind users

Documentation that does not work with these technologies excludes these users entirely.

### The Legal Case

Accessibility requirements exist in many jurisdictions:

- **Americans with Disabilities Act (ADA)**: US accessibility requirements
- **Section 508**: US federal agency requirements
- **European Accessibility Act**: EU requirements
- **WCAG 2.1/2.2**: International guidelines (often legally referenced)

Non-compliance creates legal risk and excludes customers.

### The Quality Case

Accessible documentation is better documentation:

- Clear headings improve navigation for everyone
- Alt text descriptions help when images fail to load
- Plain language benefits non-native speakers
- Good contrast reduces eye strain

Accessibility improvements have broad benefits.

## WCAG Principles

The Web Content Accessibility Guidelines (WCAG) organize accessibility into four principles: Perceivable, Operable, Understandable, and Robust (POUR).

### Perceivable

Users must be able to perceive content.

**Text alternatives**: Provide alt text for images, transcripts for audio, captions for video.

**Adaptable content**: Structure content so it can be presented in different ways without losing meaning.

**Distinguishable**: Make content easy to see and hear—sufficient contrast, resizable text, no audio-only information.

### Operable

Users must be able to operate the interface.

**Keyboard accessible**: All functionality available via keyboard.

**Enough time**: Users can control time limits on reading or interaction.

**No seizure triggers**: Avoid flashing content that could cause seizures.

**Navigable**: Help users navigate and find content.

### Understandable

Content and interface must be understandable.

**Readable**: Text is readable and understandable.

**Predictable**: Pages operate in predictable ways.

**Input assistance**: Help users avoid and correct mistakes.

### Robust

Content must work with current and future technologies.

**Compatible**: Maximize compatibility with assistive technologies.

## Accessible Document Structure

Structure is fundamental to accessibility.

### Heading Hierarchy

Screen reader users navigate by headings. Proper hierarchy is essential:

```markdown
# Page Title (H1)
## Main Section (H2)
### Subsection (H3)
### Another Subsection (H3)
## Another Main Section (H2)
```

**Rules:**

- One H1 per page (the page title)
- Never skip levels (H2 to H4 without H3)
- Use headings for structure, not styling
- Headings should describe section content

### Lists

Use proper list markup:

```markdown
- First item
- Second item
- Third item
```

Screen readers announce "list of 3 items" and allow navigation between items. Fake lists (lines starting with dashes in paragraphs) lose this functionality.

### Tables

Tables need proper markup for accessibility:

**Accessible table:**

```html
<table>
  <caption>Server Configuration Options</caption>
  <thead>
    <tr>
      <th scope="col">Option</th>
      <th scope="col">Default</th>
      <th scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>timeout</td>
      <td>30</td>
      <td>Connection timeout in seconds</td>
    </tr>
  </tbody>
</table>
```

**Table accessibility requirements:**

- Header cells marked with `<th>`
- Scope attributes for complex tables
- Caption or summary describing the table
- Avoid using tables for layout

### Links

Link text should describe the destination:

**Inaccessible:**
> Click [here](#) to download the configuration guide.
> For more information, see [this page](#).

**Accessible:**
> Download the [configuration guide](#).
> For more information, see [configuring authentication](#).

Screen reader users often navigate by links. "Click here" provides no context about the destination.

## Writing for Screen Readers

Screen readers process content linearly. Write with this in mind.

### Alt Text for Images

Every image needs alt text describing its content or function.

**Informative images:**
```html
<img src="architecture.png"
     alt="System architecture diagram showing web server connected to application server and database">
```

**Decorative images:**
```html
<img src="decorative-line.png" alt="">
```

Empty alt text (`alt=""`) tells screen readers to skip decorative images.

**Complex images:**
For complex diagrams, provide extended descriptions:

```html
<figure>
  <img src="flowchart.png"
       alt="Troubleshooting flowchart for connection errors"
       aria-describedby="flowchart-description">
  <figcaption id="flowchart-description">
    The flowchart begins with "Connection failed" and branches based on
    error type: timeout errors lead to checking network connectivity,
    authentication errors lead to verifying credentials...
  </figcaption>
</figure>
```

### Content Order

Screen readers process content in DOM order. Ensure logical reading order:

- Main content before sidebars
- Headings before their content
- Instructions before actions

Visual layout can differ from reading order, but reading order should make sense.

### Avoid Screen Reader Traps

**Do not:**

- Use images of text (screen readers cannot read them)
- Rely on placeholder text for instructions
- Create content that only makes sense visually
- Use ASCII art for important information

## Color and Contrast

Not all users perceive color the same way.

### Color Contrast Requirements

WCAG requires minimum contrast ratios:

- **Normal text**: 4.5:1 contrast ratio
- **Large text** (18pt+): 3:1 contrast ratio
- **UI components**: 3:1 contrast ratio

Check contrast with tools like:

- WebAIM Contrast Checker
- Chrome DevTools accessibility panel
- Automated accessibility testing tools

### Do Not Rely on Color Alone

Color should not be the only way to convey information.

**Problematic:**
> Required fields are marked in red.

**Accessible:**
> Required fields are marked with an asterisk (*) and red border.

Users who cannot distinguish colors need alternative indicators.

### Syntax Highlighting

Code syntax highlighting should not rely solely on color:

- Ensure sufficient contrast for all syntax colors
- Consider users who cannot distinguish colors
- Test code blocks with color blindness simulators

## Plain Language

Plain language is an accessibility requirement for cognitive accessibility.

### Readability Guidelines

- Use simple sentence structures
- Define technical terms when first used
- Break complex information into smaller chunks
- Use active voice
- Avoid jargon when simpler terms work

### Reading Level

Write for the broadest possible audience:

- Target 8th-grade reading level for general content
- Technical content may require higher levels for accuracy
- Use readability tools to assess complexity

### Consistent Terminology

Use the same term for the same concept throughout:

**Inconsistent:**
> Click the **Submit** button. After you press **Send**, the form is processed.

**Consistent:**
> Click the **Submit** button. After you click **Submit**, the form is processed.

Inconsistent terminology confuses all users, especially those with cognitive disabilities.

## Interactive Elements

Documentation with interactive elements needs accessibility consideration.

### Keyboard Navigation

All interactive elements must be keyboard accessible:

- Tab moves between interactive elements
- Enter or Space activates buttons and links
- Escape closes dialogs and dropdowns
- Arrow keys navigate within components

Test by navigating with keyboard only.

### Focus Indicators

Visible focus indicators show keyboard users where they are:

```css
:focus {
  outline: 2px solid #1E3A8A;
  outline-offset: 2px;
}
```

Never remove focus indicators without providing alternatives.

### Skip Links

For documentation sites, provide skip links:

```html
<a href="#main-content" class="skip-link">Skip to main content</a>
```

This lets keyboard users skip navigation to reach content directly.

## Multimedia Accessibility

Video and audio content need accessibility accommodations.

### Video

- **Captions**: Synchronized text for dialogue and important sounds
- **Audio descriptions**: Narration of important visual information
- **Transcript**: Complete text alternative

### Audio

- **Transcript**: Complete text version of audio content
- **No auto-play**: Let users control when audio plays

### Animated Content

- Allow users to pause, stop, or hide animations
- Avoid content that flashes more than 3 times per second
- Provide static alternatives when possible

## Testing for Accessibility

### Automated Testing

Tools catch many accessibility issues:

- **WAVE**: Browser extension for accessibility evaluation
- **axe**: Accessibility testing engine
- **Lighthouse**: Chrome DevTools accessibility audit
- **Pa11y**: Command-line accessibility testing

Automated tools catch about 30-40% of accessibility issues.

### Manual Testing

Manual testing catches what automation misses:

- **Keyboard testing**: Navigate using only keyboard
- **Screen reader testing**: Use NVDA, JAWS, or VoiceOver
- **Zoom testing**: Test at 200% zoom
- **Color testing**: Use color blindness simulators

### User Testing

The most valuable accessibility testing involves users with disabilities:

- Recruit users who rely on assistive technologies
- Observe how they interact with documentation
- Gather feedback on barriers and friction points

## Accessibility Checklist

Use this checklist for documentation accessibility:

**Structure**

- [ ] Single H1 per page
- [ ] Heading hierarchy without skipped levels
- [ ] Proper list markup
- [ ] Accessible tables with headers

**Content**

- [ ] Alt text for all informative images
- [ ] Descriptive link text
- [ ] Plain language appropriate to audience
- [ ] Consistent terminology

**Visual**

- [ ] Sufficient color contrast
- [ ] Information not conveyed by color alone
- [ ] Readable font sizes
- [ ] Content reflows at zoom

**Interactive**

- [ ] Keyboard accessible
- [ ] Visible focus indicators
- [ ] Skip navigation option

**Multimedia**

- [ ] Captions for video
- [ ] Transcripts for audio
- [ ] User control over playback

## Summary

Accessible documentation serves all users and meets legal requirements. Key practices include:

- Proper document structure with semantic headings and lists
- Alt text for all informative images
- Sufficient color contrast without relying on color alone
- Plain language and consistent terminology
- Keyboard accessibility for interactive elements
- Captions and transcripts for multimedia

Accessibility is not an add-on—it is foundational to quality documentation. Build it in from the start.

---

**Next**: [Grammar Essentials](grammar-essentials.md) covers grammar rules most important for technical writing.
