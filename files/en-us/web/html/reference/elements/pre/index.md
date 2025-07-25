---
title: "<pre>: The Preformatted Text element"
slug: Web/HTML/Reference/Elements/pre
page-type: html-element
browser-compat: html.elements.pre
sidebar: htmlsidebar
---

The **`<pre>`** [HTML](/en-US/docs/Web/HTML) element represents preformatted text which is to be presented exactly as written in the HTML file. The text is typically rendered using a non-proportional, or [monospaced](https://en.wikipedia.org/wiki/Monospaced_font) font.

Whitespace inside this element is displayed as written, with one exception. If one or more leading newline characters are included immediately following the opening `<pre>` tag, the _first_ newline character is stripped.

`<pre>` elements' text content is parsed as HTML, so if you want to ensure that your text content stays as plain text, some syntax characters, such as `<`, may need to be escaped using their respective {{glossary("character reference", "character references")}}. See [escaping ambiguous characters](#escaping_ambiguous_characters) for more information.

`<pre>` elements commonly contain {{HTMLElement("code")}}, {{HTMLElement("samp")}}, and {{HTMLElement("kbd")}} elements, to represent computer code, computer output, and user input, respectively.

By default, `<pre>` is a [block-level](/en-US/docs/Glossary/Block-level_content) element, i.e., its default {{cssxref("display")}} value is `block`.

{{InteractiveExample("HTML Demo: &lt;pre&gt;", "tabbed-standard")}}

```html interactive-example
<pre>
             S
             A
            LUT
             M
            O N
            D  E
            DONT
          JE SUIS
          LA  LAN
          G U E  É
         L O Q U E N
        TE      QUESA
       B  O  U  C  H  E
      O        P A R I S
     T I R E   ET   TIRERA
    T O U             JOURS
   AUX                  A  L
 LEM                      ANDS   - Apollinaire
</pre>
```

```css interactive-example
pre {
  font-size: 0.7rem;
  margin: 0;
}
```

## Attributes

This element only includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

- `width` {{deprecated_inline}} {{Non-standard_Inline}}
  - : Contains the _preferred_ count of characters that a line should have. Though technically still implemented, this attribute has no visual effect; to achieve such an effect, use CSS {{Cssxref("width")}} instead.
- `wrap` {{non-standard_inline}} {{Deprecated_Inline}}
  - : Is a _hint_ indicating how the overflow must happen. In modern browser this hint is ignored and no visual effect results in its present; to achieve such an effect, use CSS {{Cssxref("white-space")}} instead.

## Accessibility

It is important to provide an alternate description for any images or diagrams created using preformatted text. The alternate description should clearly and concisely describe the image or diagram's content.

People experiencing low vision conditions and browsing with the aid of assistive technology such as a screen reader may not understand what the preformatted text characters are representing when they are read out in sequence.

A combination of the {{HTMLElement("figure")}} and {{HTMLElement("figcaption")}} elements, supplemented by the [ARIA](/en-US/docs/Web/Accessibility/ARIA) `role` and [`aria-label`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-label) attributes on the `pre` element allow the preformatted {{Glossary("ASCII")}} art to be announced as an image with alternative text, and the `figcaption` serving as the image's caption.

### Example

```html
<figure>
  <pre role="img" aria-label="ASCII COW">
      ___________________________
  &lt; I'm an expert in my field. &gt;
      ---------------------------
          \   ^__^
           \  (oo)\_______
              (__)\       )\/\
                  ||----w |
                  ||     ||
  </pre>
  <figcaption id="cow-caption">
    A cow saying, "I'm an expert in my field." The cow is illustrated using
    preformatted text characters.
  </figcaption>
</figure>
```

- [MDN Understanding WCAG, Guideline 1.1 explanations](/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.1_—_providing_text_alternatives_for_non-text_content)
- [H86: Providing text alternatives for ASCII art, emoticons, and leetspeak | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H86.html)

## Examples

### Basic example

#### HTML

```html
<p>Using CSS to change the font color is easy.</p>
<pre><code>
body {
  color: red;
}
</code></pre>
```

#### Result

{{EmbedLiveSample("Basic_example")}}

### Escaping ambiguous characters

Suppose you want to demonstrate HTML code in a `<pre>` element. The character sequences that define valid HTML tags (starting with `<` and ending with `>`) will not be displayed. To display the tag characters as text, you need to escape (at least) the `<` character using its character reference, so that the sequences no longer define valid tags.

In reality, the HTML parser treats most characters as plain text unless in specific contexts. For example, `< code` is fine, but `<code` would be misparsed; `&am;` is fine, but `&amp;` is not. However, it's a good practice to escape all ambiguous characters to avoid any confusion, especially if you are programmatically generating HTML and injecting the `<pre>` content. In this case, here's a good rule of thumb for how to escape characters:

1. First, write the content out, as you would like it to appear in the HTML document.
2. Replace any ampersands (`&`) with `&amp;`. Do this step first, so that new `&` characters generated in the next step don't get escaped.
3. Replace any `<` characters with `&lt;`.

This should result in the content being displayed as you intended. The replacement of other HTML syntax characters is optional (like `>` to `&gt;`, `"` to `&quot;`, and `'` to `&apos;`), but will do no harm.

#### HTML

```html
<pre><code>
let i = 5;

if (i &lt; 10 &amp;&amp; i &gt; 0)
  return &quot;Single Digit Number&quot;
</code></pre>
```

#### Result

{{EmbedLiveSample("Escaping_reserved_characters")}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories"
          >Content categories</a
        >
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >Flow content</a
        >, palpable content.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >Phrasing content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>None, both the starting and ending tag are mandatory.</td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>
        Any element that accepts
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >flow content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <code
          ><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/generic_role"
            >generic</a
          ></code
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLPreElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- CSS: {{Cssxref('white-space')}}, {{Cssxref('word-break')}}
- {{glossary("Character reference")}}
- Related element: {{HTMLElement("code")}}, {{HTMLElement("samp")}}, {{HTMLElement("kbd")}}
