---
id: 2117h28zflwd4f4975796m4
title: Shortcuts
desc: ''
updated: 1704579784250
created: 1704569450121
---

## Shortcouts for dendron
- `Ctrl+Alt+L`: Open the dendron command palete

## Functionalities
- You can _paste the content of anote in a nother note_. You only have to **select the content**, then **open the dendron command palete** and **write the new note path**

- You can create **scratch notes** with the command `Dendron: Create Scratch Note` (you can also use the shortcut `Ctrl+Alt+L` and selectign the option)

- If you _change the name of a note_ (a parent note), you have to do a **Refactoring Hierarchy** with **Ctrl+Shift+P**. With this you ensure that the name of the note is changed in all the references.

- For _create a schema_ in the command palet you have to put **Create Schema From...**, but you have to ensure to be in the note that you want to create the schema (this have to be a parent note).
  - This creates a yml file.
    - id: Is the id or the real name of the note
    - title: Is the title of the note, this shows when you create this note

-  In a schema you can _create a template_ puting something similar like this (ensuring that the id of themplate exists):
  ```yml
  pattern: rust
  title: rust
  desc: rust file
  template:
    id: 'templates.rust'
    type: note
  ```
  - Also you can use _dynamic variables into the template_. For this you need to **create your file**, prefer to be called **templates.anything** and in this file you can use variables like `$1`, `$2`, `$CURRENT_YEAR` and more. Then, in your file, you open the **command palete** and select the **Inset Note** option, selecting your template.