---
title: "Transformations - Undo and Redo"
teaching: 5
exercises: 0
questions:
- "How do the Undo and Redo features work?"
objectives:
- "Explain how to use Undo and Redo to retrace ones' steps"
keypoints:
- "You can use Undo and Redo to retrace ones' steps"
- "You can save and apply a set of steps to a new set of data using the 'Extract' and 'Apply' features"
---

## Undo and Redo
OpenRefine lets you undo, and redo, any number of steps you have taken in cleaning the data. This means you can always try out transformations and 'undo' if you need to. The way OpenRefine records the steps you have taken even allows you to take the steps you've carried out on one data set, and apply it to another data set by a simple copy and paste operation.

The ```Undo``` and ```Redo``` options are accessed via the lefthand panel.

The Undo/Redo panel lists all the steps you've taken so far. To undo steps, simply click on the last step you want to preserve in the list and this will automatically undo all the changes made since that step.

The remaining steps will continue to show in the list but greyed out, and you can reapply them by simply clicking on the last step you want to apply.

However, if you 'undo' a set of steps and then start doing new transformations, the greyed out steps will disappear and you will no longer have the option to 'redo' these steps.

If you wish to save a set of steps to be re-applied later, or to a different project, you can click the ```Extract``` button. This gives you the option to select the steps you want to save, and to copy the transformations included in the selected steps in a format called 'JSON'

To apply a set of steps you have copied or saved in this 'JSON' format use the ```Apply``` button and paste in the JSON. In this way you can share transformations between projects and each other.

Undo/Redo data is stored with the Project and is saved automatically as you work, so next time you open the project, you can access your full history of steps you have carried out and undo/redo in exactly the same way.
