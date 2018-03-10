# resumeToLatex

A small python program to create multiple-language LaTeX documents (like resumes) from a single XML file.

## Usage

* Create a (or modify the attached) `template_LANG.tex` file. Where `LANG` is the two-letter language code (e.g. `en` for English, `de` for German, ...). Use the [Cheetah3 template engine syntax](http://cheetahtemplate.org/users_guide/intro.html#give-me-an-example).
* Edit your personal data in `resume_data.xml`
    * If you want a data field to have a different value in a certain language, use the `lang="en"` attribute to specify which language is meant.
* Execute resumetolatex:
    * If you want to save the rendered template to a latex file: `python .\resumetolatex > filledTemplate.tex`
    * If you want to get a PDF directly, pipe it to a latex render engine: `??? TODO ???`
