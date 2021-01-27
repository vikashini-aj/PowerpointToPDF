# Powerpoint PresentationToPDF converts a Microsoft Powerpoint presentation to a PDF file containing one page for each animation step (i.e. each mouse-click).
To do this, it temporarily marks the original slides as "hidden", then creates one new slide for the end-state of each animation step. Both the old and new slides are tagged to identify which are which, and whether or not any of the original slides were already hidden. The result is "printed" to the "Microsoft Print to PDF" pseudo-printer, which is installed as part of Windows 10. The user then supplies a filename to a dialogue generated by the printer driver. Finally, the generated slides are deleted, the original slides unhidden and tags removed, restoring the presentation to its original state.

Optionally, slide numbers (in format *\<old slide number\>**-**\<animation step\>*) can be added to the result.

It is also possible to suppress the "restore" function and edit the generated slides. This is to allow the user to manually fix any parts of the conversion that the automatic process hasn't converted properly (I'm not aware of any, but I'm sure there are some!)

When the macro is run on a presentation that has already been converted, but not restored, it will warn the user and restore the presentation to normal.

INSTRUCTIONS

From within Powerpoint, create a new blank presentation and delete the default slide. Save this as an empty Powerpoint Macro-Enabled Presentation, e.g. "*Macros.pptm*". Press *alt-F11* to load the VBA macro editor. Go to the *Project Explorer* pane. (If you can't see this, click *View*, *Project Explorer*). Right-click on *Module1* and remove it.

Now click *File*, *Import File* and import *PresentationToPDF.bas* and each of the *.cls* files in turn. Once this has been done, click *File*, *Close and Return to Microsoft Powerpoint*. Once back in Powerpoint, save the new presentation, which will now include the uploaded VBA macro code.

To convert a real presentation, open both it and *Macros.pptm*. From within the real presentation select *View*, *Macros* and (at the bottom of the dialogue) select *Macros.pptm* from the drop-down below *Macro in:*. Then, from within the body of the dialog, select *PrintToPDF* and press *Run*. The code will then run - simply respond to the prompts displayed.

TECHNICAL NOTE: To perform the conversion, the macro deletes from the generated slide any shapes that should not be visible at the current animation step. Shapes containing animated paragraphs are left in place, but those paragraphs within them that should not be visible are camouflaged rather than deleted, i.e. the font colour is changed to match the shape colour. This ensures other, visible paragraphs do not move or increase in size within a shape.
