# resumeToLatex

A small python program to create multiple-language LaTeX documents (like resumes) from a single XML file.

## Prerequisites
* python3
* lxml (`pip install lxml`)

## Usage

* Create a (or modify the attached) `template_LANG.tex` file. Where `LANG` is the two-letter language code (e.g. `en` for English, `de` for German, ...). Use the [Cheetah3 template engine syntax](http://cheetahtemplate.org/users_guide/intro.html#give-me-an-example).
    * To get a printable ampersand `&`, use `&amp;`
* Edit your personal data in `resume_data.xml`
    * If you want a data field to have a different value in a certain language, use the `lang="en"` attribute to specify which language is meant.
* Execute resumetolatex: `python .\resumetolatex lang1 lang2 ...`. This will generate a file `filledTemplate_LANG.tex` for each language
* Compile the file(s) with your favorite LaTeX compiler.

**Full chain** (example)
```bash
python .\resumetolatex de en; latexmk -pdf -silent "filledTemplate_de.tex"; latexmk -pdf -silent "filledTemplate_en.tex"; latexmk -c; rm filledTemplate_de.tex; rm filledTemplate_en.tex;
```

## Usage as GitHub webhook
This repository also includes a `hook.php` file.
By renaming and editing the corresponding `config.php.example` file, you can setup a [GitHub webhook](https://developer.github.com/webhooks/) to automatically re-make your resume when the `master` branch changes.
