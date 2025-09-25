# Quarto Extension: Citation CFF Parser

This Quarto extension adds a shortcode to parse and display an author list taken from a `CITATION.cff` file.

## Installation

Add this extension to your project by running:

```bash
quarto add cambiotraining/crit-quarto-ext/citation-cff-parser
```

## Usage

You can use the shortcode `{{< citation <path to CITATION.cff> >}}` in your Quarto documents:

```markdown
{{< citation CITATION.cff >}}
```

TODO: add example output