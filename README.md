# Markdown Resume Generator

Thank you very much to [there4](https://github.com/there4/markdown-resume) for developing this beautiful template. I am keeping much of their readme the same for ease of reference on my end, but I encourage anyone who is looking at making a resume in markdown to check out [this project](https://github.com/there4/markdown-resume). 

Right now I am using their design template, but I am looking to change the CSS to suite my aesthetic taste soon. 

Turn a simple Markdown document into an elegant resume with both a perfect
pdf printable format, and a responsive css3 html5 file. You can view a sample
at the [blog post for the project][blog].

[![Build Status](https://travis-ci.org/there4/markdown-resume.png?branch=master)](https://travis-ci.org/there4/markdown-resume)

## Features

* Three styles to choose from: modern, blockish, unstyled (Fork and add more!)
* PDF generation via [wkhtmltopdf][wkhtmltopdf]
* Responsive design for multiple device viewport sizes
* Simple Markdown formatting
* Single file deployment (no external stylesheets)
* You can now version control and branch your resume.

## Quickstart

  There is no installation or need to run composer. Just run the phar file:

    ./bin/md2resume html examples/source/sample.md examples/output/
    ./bin/md2resume pdf examples/source/sample.md examples/output/

## Help
```
Markdown Resume Generator version 2.0.8 by Craig Davis

Usage:
  [options] command [arguments]

Options:
  --help           -h Display this help message.
  --quiet          -q Do not output any message.
  --verbose        -v|vv|vvv Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug
  --version        -V Display this application version.
  --ansi              Force ANSI output.
  --no-ansi           Disable ANSI output.
  --no-interaction -n Do not ask any interactive question.

Available commands:
  help         Displays help for a command
  html         Generate an HTML resume from a markdown file
  list         Lists commands
  pdf          Generate a PDF from a markdown file
  selfupdate   Updates md2resume.phar to the latest version.
  stats        Generate a word frequency analysis of your resume
  templates    List available templates
  version      Show current version information

```
## Examples

Choose a template with the -t option.

    ./bin/md2resume html --template blockish examples/source/sample.md examples/output/

If you want to edit your markdown resume in your editor while watching it
update in your browser, run this command:

    watch ./bin/md2resume html --refresh yes --template modern examples/source/sample.md examples/output/

This makes the build script run periodically, and html document will refresh
every two seconds via a meta tag. Open the `./examples/ouput/sample.html` file
in your browser, and then just save your markdown document when you want to see
a fresh preview.

## Authoring Your Resume

Markdown is limited to basic html markup. Follow the `examples/source/sample.md`
file  as a guideline. This file includes various headers and several nested
elements. This allows us to construct a semantic HTML document for the resume,
and then use CSS rules to display a nicely formatted resume. Note that because
we have very few ways to nest or identify elements that many of the css rules
are based on descendant and adjacent selectors.

__PLEASE NOTE__: The templates are compiled into the phar archive in the `./bin`
folder. If you intend to edit the templates or add new ones, you'll need to run
this application in the dev mode. See below for more information about doing
this.

## Feature Development

The application is deployed as a compiled phar file. In order to add new
commands, you'll need to first install the dependencies:

* `composer install`

After that, you can run the `md2resume_dev.php` file from the command line.
Check out the pake tooling for more information about the build. Pake will be
installed to `./vendor/bin/pake`. So for instance a complete phar file build
looks like `./vendor/bin/pake build`.

## Acknowledgments

The initial inspiration is from the [Sample Resume Template][srt].
However, no HTML from that project has been used in this. General layout has
been reused, and media queries have been added. It's a nice template, and if you
are a more comfortable with html than markdown, you should use it.


## Useful Links

- [srt]: http://sampleresumetemplate.net/ "A great starting point"
- [blog]: http://there4development.com/blog/2012/12/31/markdown-resume-builder/
- [pake]: https://github.com/indeyets/pake/wiki/Installing-Pake
- [wkhtmltopdf]: https://github.com/pdfkit/pdfkit/wiki/Installing-WKHTMLTOPDF
- [console]: http://symfony.com/doc/current/components/console/introduction.html
