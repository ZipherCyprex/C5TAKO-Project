# Translate C5TAKO docs to English

English source files already live under `docs/en/` with the same folder structure as the Thai documentation. Do not overwrite an existing English page from the Thai source: translate only the page that changed.

## Prompt for an AI translator

Give one Thai source file and its matching English destination file to the AI. For example: `docs/features/wifi-scan.mdx` to `docs/en/features/wifi-scan.mdx`.

```text
Translate this Thai Mintlify MDX document into clear technical English.

Rules:
- Return only the complete translated MDX file.
- Preserve front matter keys, Markdown structure, MDX components, code blocks, tables, admonitions, and HTML/JSX exactly unless the text itself needs translation.
- Do not translate commands, device menu labels, paths, filenames, identifiers, URLs, image paths, or code.
- Keep internal documentation links under /en/ exactly as supplied.
- Translate headings, prose, link labels, table text, and user-facing button descriptions.
- Keep all safety and authorization warnings explicit.
- Do not add claims or remove details.
```

After translating a batch, run:

```powershell
mint.cmd validate
```

from the `docs` folder.
