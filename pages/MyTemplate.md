tags:: #templates #reuse 
alias:: template

-
- ## ✅  **Common Template Variables in Logseq**
  
  Here are the built-in variables you can use in templates:
  
  | Variable | Expands To |
  | ---- | ---- | ---- |
  | `<% today %>` | Current date in **your journal format** |
  | `<% now %>` | Current date **and time** |
  | `<% time %>` | Current time |
  | `<% yesterday %>` | Previous day's date |
  | `<% tomorrow %>` | Next day's date |
  | `<% current page %>` | Name of the current page |
-
-
- [Open in vscode](vscode://file:///C:/Users/nikhilsharma03/Code/code-with-quarkus)
  template:: vscode
-
- title:: <% current page %>
  type:: project
  status:: planning
  priority:: A
  tags:: work, project
  created:: <% today %>
  deadline:: <% tomorrow %>
  created-time:: <% time %>
  template:: project
-
- TODO Task description
  
  priority:: B
  status:: next-action
  scheduled:: <% today %>
  deadline:: <% today %>
  refs:: [[Project Name]]
  template:: task
-