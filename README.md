# highlight-within-textarea

Small library for highlighting bits of text within a textarea.

## Introduction

It's not actually possible to style text in a textarea, because any markup within a textarea is treated as literal text. This plugin aims to fake it, allowing you to highlight pieces of text inside a textarea.

A native textarea element is used and familiar behavior (auto-correct, scrolling, resizing, etc.) works as expected.

## Usage

To start, call `highlightWithinTextarea()`, passing in a textarea and a config object.

```javascript
const highlighter = new HighlightWithinTextarea(myTextarea, {
    highlight: whatever // string, regexp, array, function, or custom object
});
```

The `highlight` property accepts several different types of values to describe what will be highlighted.

## Styling

**The vanilla version has a [demo page](https://therealgoodlivin.github.io/highlight-within-textarea/)** and is the same configuration jQuery version.

**The jQuery version has a [demo page](https://lonekorean.github.io/highlight-within-textarea/)** with some sample styling (view source to see the CSS). 

There are some guidelines for getting your styles in the right places. Here are the classes you'll want to use.

### .hwt-container

Use for visibility, positioning, and background.
- `display`
- `position`
- `top`
- `left`
- `margin`
- `background`

### .hwt-content

Use for sizing and text formatting.
- `width`
- `height`
- `padding`
- `border`
- `color`
- `font`

### .hwt-content mark

Use for highlighted text. Generally, stuff that doesn't change size is fine.
- `background-color`
- `border-radius`
- `box-shadow`

Changes to `color` won't be visible, since text in the textarea covers colored text in the highlights.

## Updating

Highlighting will automatically be updated as the user edits the contents of the textarea. But sometimes other scripts may directly change the contents of the textarea. In these cases, you can manually trigger a highlighting update.

```javascript
highlighter.handleInput()
```

## Destroying

You can remove the plugin from a textarea with this. This will remove all events triggers that have been applied to the textarea.
```javascript
highlighter.destroy()
```
