# Digital Systems and Microprocessors

> This is a repository to share and compile notes for the ELEC1202
module.

## Regulations

For each lecture there should be a folder containing a markdown
document, and any additional content (images, slides etc.).

It is important that you edit the notes already present, rather than
just uploading your notes.

Please use `git` correctly, forking the repository before making a 
pull request to get your content added.

## How to Edit

To edit any of the documents fork the repository then edit the markdown or image documents on your desktop, or in GitHub's online editor. When you are done editing create a pull request. One of the admins will then either accept the pull request to merge it with `master` or write in the comments of the pull request with suggested further edits.

## Pandoc

All of the notes in this repository are written in Pandoc Markdown[^pandoc], which although very similar to GitHub flavoured markdown is still slightly different, so if you are familiar with other markdown styles its worth reading the README, as it is very well documented. 

All of the documents are converted to LaTeX PDFs and are placed in the same directory as the `.md` document they are made from. These are the file that you can study from, the markdown files are the ones that are edited.

Before submitting your pull request it would be great if you could update or create any PDF documents related to what you have worked on. Generally this is the format for conversion:

    pandoc fromFile.md -o toFile.pdf --latex-engine="xelatex"

However this is quite advanced as it requires the installation of LaTeX, and if you can't do this please say in your pull request and an admin will do it for you.

[^pandoc]: <http://pandoc.org/README.html#pandocs-markdown>

>If you have any questions don't hesitate to email the administrator, Harry Beadle, username hb11g15.
