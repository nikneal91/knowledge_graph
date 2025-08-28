type:: template
tags:: logseq
created:: [[Aug 28th, 2025]]

-
-
-
- ## ✅  **Common Template Variables in Logseq**
  collapsed:: true
  
  Here are the built-in variables you can use in templates:
	- | Variable | Expands To |
	  | ---- | ---- | ---- |
	  | `<% today %>` | Current date in **your journal format** |
	  | `<% now %>` | Current date **and time** |
	  | `<% time %>` | Current time |
	  | `<% yesterday %>` | Previous day's date |
	  | `<% tomorrow %>` | Next day's date |
	  | `<% current page %>` | Name of the current page |
-
- title:: <% current page %>
  type:: page
  status:: live
  priority:: A
  tags:: work, project
  created:: <% today %>
  created-time:: <% time %>
  template:: logseq/page
-
- TODO Task description
  
  priority:: B
  status:: backlog
  scheduled:: <% today %>
  deadline:: <% tomorrow %>
  refs:: [[Project Name]]
  template:: todo/task