# MD-TOC

A command line tool to automatically create a table of content (TOC) for markdown files with file extension `.md`. 

<!-- MD-TOC START LEVEL 99 -->

# Table of Contents

  - [Usage](#usage)
    - [Prepare Markdown File](#prepare-markdown-file)
    - [Run Script](#run-script)
  - [Examples](#examples)
  - [Author](#author)

<!-- MD-TOC END -->



### Prepare Markdown File

The _MD-TOC_ script will browse through the markdown file and search for (not printed) tokens. These tokens marks beginning and end of an existing table of content. 
If tokens are found, _MD-TOC_ will start parsing after the end token. So a title before the TOC will not be included to teh new TOC.
The tokens will be added automatically by the script when the TOC is placed at the beginning of the file. 
Alternatively, the start and end tokens can be placed in the file manually. Level specifies the number of heading levels to be included to the TOC:

```bash
<!-- MD-TOC START LEVEL 3 -->

Between the tokens everything will be overwritten.

<!-- MD-TOC END -->
```

### Run Script

Copy `md_toc.py` to main path of local directory:
```bash
wget https://raw.githubusercontent.com/RalfTischer/md-toc/main/md_toc.py
```

Start _MD-TOC_ from command line. 
```bash
python ./md_toc.py -f README.md
```

Options:
* `-f` or `--files`: list of files, optional
* `-p` or `--paths`: list of paths, optional
* `-s` or `--sub`: if set, browse all paths sub-directories, optional
* `-l` or `--level`: maximum level of headings to be included to TOC, optional, default=99

When finished, delete the local copy of _MD-TOC_:
```bash
rm md_toc.py
```

## Examples

Create TOC for `README.md` and `describe.py` to level 3:
```bash
python ./md_toc.py -f README.md describe.py --level 3
```

Create TOC for all .md files in current directory with all levels:
```bash
python ./md_toc.py -p "."
```

Create TOC for all .md files in `path/` directory including all subdirectories with all levels:
```bash
python ./md_toc.py -p "path/" -s
```
## Author

Ralf Tischer, 2024
