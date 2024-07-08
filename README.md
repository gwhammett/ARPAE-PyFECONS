This Github contains a folder for each base case, and one for the benchmark cases. Each folder contains the code in a .ipynb file, the template text for each cost category in the 'Originals' folder, and other files required for the latex document to compile. To generate a report:

[?? gwh: need to start by forking your own copy of this github repo.  Note that overleaf only works with a main branch, so don't bother trying to create other branches.]
1. Download the code notebook .ipynb file or save a copy into google colab (search google colab, then file/upload notebook/ Github/ search for this repo using the url and select a code from the MFE, IFE etc.) currently running from google colab is recommended. If you decide to run the code locally, git handling code and file locations may be different, depending on your OS and environment.
2. Create an Overleaf.com document that is synced with your github fork of this repo.  To avoid possible errors, make sure that in the Overleaf "Menu" (upper left corner) the Settings section says the "Main document" MFE/Costing_ARPA-E_MFE_Modified.tex.
3. Here there are folders for each costing case. Select one, inside there are 'Originals', 'Modified', 'Costing_ARPA-E_x_Modified', 'Costing_ARPA-E_x_Originals' and others. To compile a report with template folders, run 'Costing_ARPA-E_x_Originals'. To edit text, edit files in 'Originals'. Edits made to files in the 'Modified' folder will be overwritten when the code is run.  If you edit files in 'Originals', you will need to go to Overleaf Menu, Sync, Github, and 'push' from overleaf back to the github repo to save them.
4. Become a Github collaborator and generate a PAT (ensure it has 'repo' access).
5. Input PAT into first cell of code.
6. Enter inputs in the code MFE/MFE/PyCosting_ARPA_E_MFE.ipynb on colab, and run all cells. This will overwrite 'originals' templates, and push the results back to your github repo.
7. Go to your overleaf document, and in  Menu, Sync, Github, do a'pull' from github into overleaf.  
8. Compile the 'Costing_ARPA-E_x_Modified'.tex file for the corresponding case.
9. A report should have compiled with the placeholder variables replaced.

10. To edit the text, edit the 'originals' .tex files corresponding to the cost category you would like to edit, in the case folder you are working on.
11. Go to 'Github' on the left tab, and 'push'.
12. Restart code (in colab go 'Runtime/Disconnect and delete runtime' then 'run all'), and repeat steps 3-6.
