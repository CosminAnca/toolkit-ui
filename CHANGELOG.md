# Toolkit UI v1.0.0

## 1. Project Structure
- `toolkit-core` added as a project dependency to run tests and share config files.

## 2. Features
- [colors] `ui-` prefixed colors have moved to a `grey-` prefix for greater flexibility.
- [divider] `c-divider` for prominent horizontal (and vertical) rules for use between elements.
- [tile] `c-tile--full` for Tiles that utilise a full size image and overlapping title.

## 3. Deprecations
- [legacy-typography] Config switch now fully deprecated.

## 4. Refactor
- [dropdown] No longer utilises a checkbox hack, improving semantic structure and accessibility. Now implements a stateful `.is-open` class.
- [panel] Panel fits to content by default, with full viewport height achieved with the `c-panel--full` modifier.

## 5. Bug Fixes
- [accordion] Fixed arrow icon alignment in IE9.
- [buttons] Added relative border to buttons so that the border width scales with font-size.
- [buttons] Added `:focus` styles for accessibility.
- [forms] Fix for `.c-form-checkbox` margin which broke on multi-line captions.
- [forms] Fix to add border-radius and prevent text from overflowing beneath the icon on `c-form-select`.
- [panel] Inset shadow fix from all sides to top and bottom only.
- [tile] Fix for `.c-tile--collapsable` with nested links breaking on mobile.
- [tile] Fix for `.c-tile__media` height rounding down incorrectly causing a 1px gap.
- [tile] Fix for `.c-tile--square` height 100% + 5px causing tiles such as 555px x 560px.
- [shine] Fix for `.c-shine` when using with full width elements.
- [select] Added `:focus` styles for accessibility.
- [select] Fixed spacing of text.

===

# Toolkit UI v0.5.0

## 1. Bug Fixes
- [bezel] Added `max-width: 100%` to prevent overflow issues on IE.
- [forms] Removed tick on selected radio button.
- [forms] Refactored checkbox structure to allow for keyboard focus. Instead of `c-form-checkbox__faux`, we now utilise `c-form-checkbox__caption`.
- [select] Keyboard accessibility support.

## 2. Enhancements
- [select] Different styles for hover, focus and active states.

## ⚠️ Update Notes

To make our checkboxes and radio buttons keyboard accessible, a significant refactor was required.

`c-form-checkbox__caption` now **replaces** `c-form-checkbox__faux` for generating the indicator, wrapping the text of the input.

**If you are using checkboxes and/or radio buttons in your project, you will need to implement the following example structures:**

Checkbox:

```html
<label for="f-terms_1" class="c-form-checkbox">
  <input type="checkbox" class="c-form-checkbox__input" name="f-terms" id="f-terms_1" value="1" />
  <span class="c-form-checkbox__caption">I agree to the terms &amp; conditions</span>
</label>
```

Radio:

```html
<li class="c-form-list__item  c-form-pair">
  <span class="c-form-pair__label">
    <label class="c-form-label  u-margin-right">
      Which side?
    </label>
  </span>
  <span class="c-form-pair__input">
   <label for="f-side_1" class="c-form-checkbox  c-form-checkbox--radio  u-margin-bottom-small">
     <input type="radio" name="f-side" id="f-side_1" value="good" class="c-form-checkbox__input" />
     <span class="c-form-checkbox__caption">Good</span>
   </label>
   <label for="f-side_2" class="c-form-checkbox  c-form-checkbox--radio">
     <input type="radio" name="f-side" id="f-side_2" value="evil" class="c-form-checkbox__input" />
     <span class="c-form-checkbox__caption">Evil</span>
   </label>
  </span>
</li>
```

===

# Toolkit UI v0.4.2

## 1. Bug Fixes
- [tiles] Only title now underlines on hover.
- [tiles] Specificity reduced with hover style allowing easier customisation

===

# Toolkit UI v0.4.1

## 1. Enhancements
- [select] Reduced horizontal padding from 60px to 40px.

## 1. Bug Fixes
- [select] Border styles are now applied to the label element, this resolves a rendering issue were multiple select buttons  lost their borders.
- [select] Webkit vendor prefixes applied so buttons look and function correctly in older versions of Safari (including iOS8).

===

# Toolkit UI v0.4.0

## 1. Enhancements
- [buttons] Secondary (invert) hover color changed to align with branding.
- [panels] Panels now utilise a white background by default.
- [tiles] Sky Cinema gradient implemented to `c-tile`, replacing Sky Movies.
- [typography] New responsive Typographic scale (and added to components where used).

## 2. Deprecations
- [legacy-typography] We removed the previous typographic variables in favour of a responsive approach. To deprecate gracefully, a toggle variable has been provided in settings/config.
- [panels] Following branding, grey panels are no longer used.

===

# Toolkit UI v0.3.9

## 1. Feature
- [Tooltip] Adds the `c-tooltip` component. Easily apply tooltip bubbles to any trigger.

===


# Toolkit UI v0.3.8

## 1. Feature
- [Accordion] Integrate `c-accordion`, a simple accordion container which can be animated and controlled by a range of different frameworks.

===

# Toolkit UI v0.3.7

## 1. Bug Fixes
- [spinner] Changed the `.c-spinner` transition from targeting all properties to target opacity and visibility as these are the properties that need to be transitioned when the `.is-complete` class is added.

===

# Toolkit UI v0.3.6

## 1. Bug Fixes
- [tile] Corrected `c-tile__media` overflow from `none` to `hidden`.

===

# Toolkit UI v0.3.5

## 1. Bug Fixes
- [select] Hover states moved to `.c-select__btn` rather than the hidden input (`.c-select__input`) to ensure better browser support.
- [select] Focus style uses shaded border rather than matching the hover state to avoid confusion over the actual state.

===

# Toolkit UI v0.3.4

## 1. Enhancements
- [tile] Removed outer border and refactor of variables.
- [hero] Match glass border thickness to `c-tile`.

===

# Toolkit UI v0.3.3

## 1. Bezel
- [bezel] Added the `.c-bezel` component, which provides a glass "bezel" inner border to the container of a media element.

===

# Toolkit UI v0.3.2

## 1. Bug Fixes
- [tile] Changed tile brand modifiers class to `.c-tile__body` rather than `.c-tile__caption` so that it applies to all tiles rather than just the split media tiles
- [select] Fixes gap in bg and border on hover state caused by duplicate `border-radius` properties.

===

# Toolkit UI v0.3.1

## 1. Enhancements
- [select] Added `.is-selected` state to `.c-select__input` to change icon to cross

===

# Toolkit UI v0.3.0

## 1. Enhancements
- [tile] Added `.c-tile--collapsable` modifier to replecate previous default of removing height and `.c-tile__media` on mobile
- [tile] Refactored tile to improve performance
- [tile] Added radial gradient for content tiles and linear for media tiles by default
- [shine] Added `pointer-events: none;` to `.c-shine` to prevent it influencing hover states
- [select] Added hover state
- [defence] Moved defence to `toolkit-ui` from `toolkit-core

## 2. Bug Fixes
- [tile] Branded Tile hover text and background tweaks to be more consistent between focus / active
- [tile] Prevented multiple gradients being applied to single tiles
- [forms] Fixed unwanted outline on inputs on firefox when element in focus
- [forms] Fixed select drop down showing default arrow on firefox and IE
- [forms] Fixed input spacing on IE
- [select] Fixed select not showing tick icon correctly on firefox
- [hero] Fixed IE9 video support
- [typography] Corrected `.c-text-body` selector

## 3. Deprecations
This release contains the following potentially breaking deprecations:

- [tile] Default removal of height constraint and `.c-tile__media` on mobile has been replaced with the `.c-tile--collapsable` modifier
- [form] Removed `.c-form-inline` due to accessibilty concerns and support issues
- [sass-deprecate] We removed the sass-deprecate library in favour of changelogs and improved release notes
