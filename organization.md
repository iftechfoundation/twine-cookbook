# Organization

## Layout
Each root folder is named after the recipe and its contributor(s). Inside this folder is one with the name of each story format supported. Inside each of these is a minimum of three files: the markdown file, the compiled HTML, and its twee notation.

File names use underscores whenever possible for spaces to differentiate between the examples of the recipe for other story formats within the same root folder.

## Structure
Recipe names are included in the Summary.md (table of contents) with quotations followed by the contributor's requested name in parentheses. Story format names are listed matching those in the folder including the version designed for in parentheses and point to their markdown files.

<pre>
* "Example" (Contributor)
	* [Harlowe (v2.0)](example_contributor/harlowe/harlowe_example.md)
	* [SugarCube (v2.18)](example_contributor/sugarcube/sugarcube_example.md)
	* [Snowman (v1.3)](example_contributor/snowman/snowman_example.md)
</pre>

## Root Folder Example
<pre>
chickendance_contributors
|	harlowe
|	|		harlowe_chickendance.md
|	|		harlowe_chickendance_example.html
|	|		harlowe_chickendance_twee.txt
|	sugarcube
|	|		sugarcube_chickendance.md
|	|		sugarcube_chickendance_example.html
|	|		sugarcube_chickendance_twee.txt
</pre>


