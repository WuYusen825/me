# Notes for Claude

## Building Chinese LaTeX (ctexart) PDFs in the cloud container
- The container ships without TeX. If `xelatex` is missing, install once:
  `apt-get update && apt-get install -y --no-install-recommends texlive-xetex texlive-lang-chinese texlive-latex-extra texlive-fonts-recommended fonts-noto-cjk`
- Compile with `xelatex` twice. Set CJK fonts explicitly: `\setCJKmainfont{Noto Serif CJK SC}` (the default ctex fontset finds no fonts here).
- Do not name a tcolorbox/environment `rule` — it clobbers `\rule`. Use `rulebox` etc.
- Wide 8-column tables: set `\tabcolsep` to ~3.5pt to avoid overfull boxes on A4.
