# Quarto Extension: Callout Exercise

This extension adds three new callouts to quarto:

- `{.callout-exercise}`: A general exercise callout.
- `{.callout-answer}`: A callout for exercise solutions.
- `{.callout-hint}`: A callout for exercise hints.

## Installation

Add this extension to your project by running:

```bash
quarto add cambiotraining/crit-quarto-ext/callout-exercise
```

## Usage

To use the extension, make sure to add the following to `_quarto.yml`:

```yaml
filters: 
  - callout-exercise
```

These can then be used as regular callouts in your markdown files.
For example:

```md
::: {.callout-exercise}
## An optional exercise title

Your question goes here.

::: {.callout-hint}
This is a hint to help with the exercise.
:::

::: {.callout-answer}
This is the answer to the exercise.
:::
:::


## Customisation

### Numbering exercises

By default the exercises are numbered within each chapter.
You can change this by adding the following to `_quarto.yml`:

```yaml
exercises:
  number: false
```

### Hiding answers

By default the answers are rendered in the output file as collapsed callout boxes.

However, you may want to hide the answers completely.
This is useful if you want to have them in the source markdown file, but not make them available to the reader.

This behaviour can be changed globally by adding the following to `_quarto.yml`:

```yaml
exercises:
  hide-answers: true # by default it's false
```

Alternatively, you can hide individual answers by adding the `hide` attribute to the answer callout:

```md
::: {.callout-answer hide=true}
This answer is hidden.
:::
```

Settings on the individual answers will always override the global settings.
For example, if you've set `hide-answers: true` globally, you can still show individual answers by setting `hide=false` on the callout.

### Styling

You can style the callouts using CSS, for example to add icons and colors, as shown below.

```css
/* Exercise callout */
.callout-exercise > .callout-header::before {
  font-family: "Font Awesome 5 Free";
  content: "\f303"; /* icon: fa-pencil */
  margin-right: 10px;
}
div.callout-exercise.callout {
  border-left-color: #007bff;
}
div.callout-exercise.callout-style-default > .callout-header {
  background-color: #f9f9f8;
}

/* Answer callout */
.callout-answer > .callout-header::before {
  font-family: "Font Awesome 5 Free";
  content: "\f002 "; /* icon: fa-search */
  margin-right: 10px;
}
div.callout-answer.callout {
  border-left-color: #28a745;
}
div.callout-answer.callout-style-default > .callout-header {
  background-color: #eaf3f3;
}

/* Hint callout */
.callout-hint > .callout-header::before {
  font-family: "Font Awesome 5 Free";
  content: "\f12e "; /* icon: fa-puzzle-piece */
  margin-right: 10px;
}
div.callout-hint.callout {
  border-left-color: #6c757d;
}
div.callout-hint.callout-style-default > .callout-header {
  background-color: #f9f9f8;
}
```
