## Writing markdown
Markdown is an excelent and lightweight markup language. With it you can make documentation like this, adding math notation, code blocks of different types of language, add image and even more.

To learn how to write markdown go [here](https://guides.github.com/features/mastering-markdown/#examples)

## Markdown package for Atom
Atom have nice Package to work with markdown:

In Atom go to settings [ 'ctrl + , ' ] > Install and then search for the following packages:
  * [Markdown-preview](https://atom.io/packages/markdown-preview)

    this package allow you to live preview your markdown text using the command ["ctrl + shift + m"]
  * [Markdown-pdf](https://atom.io/packages/markdown-pdf)

    By selecting your markdown code and using the command ['Ctrl + shift + c'], this package convert a **single** file in a .PDF file.



## Create a documentation book like this:

1. The official tutorial can be found [here](https://github.com/GitbookIO/gitbook-cli):

2. Install Gitbook
```
npm install -g gitbook-cli
```
3. Prepare environment for gitbook
```
gitbook init
```

4. Create PDF file
```
gitbook pdf .\ .\book.pdf
```
