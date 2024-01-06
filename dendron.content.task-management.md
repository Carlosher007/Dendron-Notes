---
id: bzxhsgk42dhuumjsgl7mpk0
title: Task Management
desc: ''
updated: 1704582230705
created: 1704580314974
---

This is a form to do tasks. It's a way to organize our notes and tasks.

## How to create a task note
- Go to the command pallet and select the **Create Note** option.
- Type the name of the note, for example: **test-task**. Remember that already exist a default name, so you can change it or not.

## Call the task

In this section we will see how to call the task note.

- [[task.2024.05.06]]

## The really tasks key

The key of the tasks is in configuring the dendron global file, do templates and treat the tasks as a squema, with its own domain , not as a secondary elements.

- Modify the dendron.yml
- Create a task.schema.yml
- With this done we can go to the **command palete** and write `Create task note` and select the option.
  - With this template we can do it subtasks, for example `task.2022.02.13.read-the-book` and it will be a subtask of the task `task.2022.02.13`