- Goal: simple website to see courses summaries
- Features: 
	- one .md = one page
	- internal links between .md pages
	- rendering .md
	- site search function
	- breadcrumbs
	- backlinks list (where is this files mentioned)
	- forwardlinks list (what this site mentions)
	- link from hosts single monolith folder to structured website
		- groundwork for folders structure

# the page file
- .md file
- parse from content the following data:
	- internal links: denoted in[[]]
	- external links ex[[]]
	- embedded media med[[]]

# steps top->bottom
1. show home page with all links accessible and a navigation feature
2. parse md files to html
3. get source folder