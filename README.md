#	Checkout documentation

## Quick start

1.	Install the latest version of Material for MkDocs with ```pip```:
	``` sh
	pip install mkdocs-material
	```
2.	Download code from ```master``` branch.
3.	Using the Terminal ```cd``` to the directory where the ```mkdocs.yml``` is located.
4.	Start the MkDocs built-in dev-server:
``` sh
mkdocs serve
```
5.	In a browser access http://127.0.0.1:8000 to preview the changes in realtime when modifying the other files.

## Deploy changes to Github Page

1.	Using the Terminal ```cd``` to the directory where the ```mkdocs.yml``` is located.
2.	Execute the command ```mkdocs gh-deploy```.
	*	This command will generate the html files of the website and commit them to the ```gh-pages```branch.
	*	**Make sure you commit the changes of the MD files to the** ```master``` **branch.**

## Additional Information

For more information about MkDocs visit the following links:

1.	MkDocs: https://www.mkdocs.org/
2.	Material for MkDocs: https://squidfunk.github.io/mkdocs-material/
3.	MkDocs Material Components - Cheat Sheet: https://yakworks.github.io/mkdocs-material-components/cheat-sheet/