# Ryst-TeX Project

<br>

Welcome to the Ryst-TeX project, a template repository, 
use it to build projects with the need of a Rust compute module, with 
with a Python Interface, with the intention to build a research paper.

# TeX

For better reproducibility, run within a container.

```bash
docker run --rm -v "$PWD:/work" -w /work/tex \
  texlive/texlive:latest \
  latexmk -pdf drivers/paper.tex
```

Commonly needed

```bash
sudo tlmgr install \
  standalone \
  pgf \
  amsmath amscls amsfonts \
  microtype lmodern \
  enumitem booktabs titlesec authblk \
  hyperref \
  biblatex biber \
  xcolor
```

- **pgf** is what provides tikz : TikZ is the front-end, PGF is the engine
- **biblatex** + **biber** are needed for \addbibresource{...} and \printbibliography.

### On Apple

```bash
echo 'export PATH="/Library/TeX/texbin:$PATH"' >> ~/.zshrc
exec zsh
tlmgr --version
```

