# Streamline PDF viewing in the CLI

`pdfviewer` is a simple shell script that uses `mutool` under the hood to quickly convert PDF files to text or HTML files, so they can be read in the CLI, or any other preferred application.

## Features

- Convert PDF files to text or HTML files and save to cache folder
- Hear PDF using `RHVoice` TTS
- Search cache folder using `fzf`
- Wrap lines, if they don't fit the whole screen

## Requirements

```
mutool
```

### Optional Requirements

```
rhvoice
lynx
fzf
```

## Installation

```
git clone https://github.com/anstrinn/pdfviewer
chmod +x pdfviewer-sh/src/pdfviewer
sudo cp pdfviewer-sh/src/pdfviewer /usr/local/bin/
```

## Usage

```
Streamline PDF viewing in the CLI

Usage:
  pdfviewer [OPTION] [FILE]

Options:
  -w             Wrap text, if text format is used
  -p [ARG]       Use alternative PAGER
  -v [PROFILE]   Use RHVoice as TTS

Commands:
  fzf [FILE]    Fuzzy find already converted files
  html [FILE]   Convert to html
```

The first time you use `pdfviewer` the cache folder will be created at `$HOME/.cache/pdfviewer` by default, where all processed files will live, allowing easier access skipping the convert process.

### Examples

```
pdfviewer -w -p bat pdfile.pdf    # Expand lines and use bat as the viewer
pdfviewer fzf                     # Use fzf to search the cache folder and view files
pdfviewer html pdfile.pdf         # To create a HTML file
```

## Notes

This script has been only tested in a Linux Machine.

## License

This repository is licensed under the MIT License, a very permissive license that allows you to use, modify, copy, distribute and more.
