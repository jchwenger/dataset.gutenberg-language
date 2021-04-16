# Dataset: Gutenberg

Downloading & cleaning [Gutenberg](https://www.gutenberg.org/) (filtered by language).

### Download

Two ways possible, using and building on a python utility from [flauBERT](https://github.com/getalp/Flaubert):

```bash
python download.py -indir download_directory
```

Or [this script](https://www.exratione.com/2014/11/how-to-politely-download-all-english-language-text-format-files-from-project-gutenberg/). The latter creates directories `zipfiles/` and `files/` as well as the file links-zipfile.txt that contains the links to the sources.

```bash
./download.sh lang_code
```

The `lang_code` can be 'fr', 'en', etc.

### Clean

A script also from [flauBERT](https://github.com/getalp/Flaubert) using tools
from [kiasar](https://github.com/kiasar/gutenberg_cleaner/blob/master/_cleaning_options/strip_headers.py), using [NLTK](https://www.nltk.org/) to clean up licenses & endings.


```bash
python clean.py -indir download_directory -outdir clean_dir
```

---

```bash
$ python download.py --help
usage: download.py [-h] -indir INDIR [-lang LANG] [-update_url UPDATE_URL]

optional arguments:
  -h, --help            show this help message and exit
  -indir INDIR          Path to directory to save downloaded files
  -lang LANG            Language to download
  -update_url UPDATE_URL
                        Choose to update book URLs if necessary (1/0)

```

```bash
$ python clean.py --help
usage: clean.py [-h] -indir INDIR -outdir OUTDIR [-json JSON]

optional arguments:
  -h, --help      show this help message and exit
  -indir INDIR    Path to directory to save downloaded files
  -outdir OUTDIR  Path to directory to save clean files
  -json JSON      Save file to json format or not (1/0)
```
