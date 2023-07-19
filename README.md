<h1>Pandoc Notes</h1>

- [Installation](#installation)
- [CSS](#css)
- [Avenues For Exciting Upgrades](#avenues-for-exciting-upgrades)
- [Commands](#commands)
  - [Markdown to PDF:](#markdown-to-pdf)
    - [Via HTML (Allows CSS)](#via-html-allows-css)
    - [Directly (Allows Latex)](#directly-allows-latex)
  - [Markdown to Word:](#markdown-to-word)


## Installation
- TO DO
> I currently have it installed on every machine I need. I remember distinctly that there were some difficulties in getting it going because of the dependencies (I think because I was trying to include the ability to render markdown diagrams. I've since moved on to using .drawio.png images instead of this) so this section needs to be filled out if I ever want to share the repo.

## CSS
If you're creating a PDF via HTML (or just an HTML file) from Markdown, you can specify CSS to be applied to your document. This can be extremely handy. I've included any CSS I use on the reg' here. 

## Avenues For Exciting Upgrades
https://tex.stackexchange.com/questions/595615/how-can-i-reformat-a-table-using-markdown-pandoc-pdf

This conversation gives some good insight into ways that you can include a header in your markdown docs that patches Markdown itself in the rendering process!

## Commands
The easiest way I've found to run these commands is to use an absolute path that writes the output to your desktop, and absolute path to a global generic CSS file, and a relative path to the Markdown you're converting.

This will one day be upgradeable to use cloud-hosted CSS! Gotta work on that in my spare time.

### Markdown to PDF:
Two different methods here. I haven't yet found a way to apply CSS *and* include Latex, which is frustrating. 

#### Via HTML (Allows CSS)
> Likely each of the links here will need to be updated.
```bash
pandoc --standalone -f gfm -t html -o "/mnt/c/Users/lavers/OneDrive - Queensland University of Technology/Desktop/output_file.pdf" -c ./markdown/qut.css --highlight-style=kate ./file_to_convert.md
```

#### Directly (Allows Latex)
```bash
pandoc -s --variable "geometry=margin=1.2in"  -o "/mnt/c/Users/lavers/OneDrive - Queensland University of Technology/Desktop/output_file.pdf" ./file_to_convert.md
```

### Markdown to Word:
```bash
pandoc -o "/mnt/c/Users/lavers/OneDrive - Queensland University of Technology/Desktop/output_file.pdf" -f markdown -t docx ./file_to_convert.md
```