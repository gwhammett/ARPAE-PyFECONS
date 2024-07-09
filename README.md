The code in this Github repo aims to provide a standard costing tool for fusion power plants based on IAEA 2001 and GenIV 2007 cost accounts, entailing Magnetic Fusion Energy, Magneto Inertial Fusion and Inertial Fusion Energy.  

This repo is a modified version of https://github.com/Woodruff-Scientific-Ltd/ARPAE-PyFECONS, which is an open source public release to document the general approach and data used in some fusion reactor costing projects by Woodruff Scientific Ltd funded by ARPA-E. Caution: the upstream (original) repo was released as-is with no plans for support, and there are known limitations and various levels of approximations in it that persist in this present forked version. You should not use this code for any serious work without understanding all of it and improving at least some of it for your applications. (Commercial versions of this software have a number of fixes and more detailed analysis relative to this open-source version.) Search https://github.com/gwhammett/ARPAE-PyFECONS/blob/main/MFE/PyCosting_ARPA_E_MFE.ipynb for "??" to find some of the known places that need further work. (I have only made changes to the MFE directory so far.)

This Github repo contains a folder for each base case, and one for the benchmark cases. Each folder contains the main python costing code in a .ipynb file, the template text for each cost category in the 'Originals' folder, and other files required for the latex document to compile. To generate a report:

1. Fork your own copy of this github repo.  (Note that overleaf only works with a main branch, so don't bother trying to create other branches.)
2. Go to the main python notebook in one of the subdirectories (I have focussed on the MFE version), [MFE/PyCosting_ARPA_E_MFE.ipynb](MFE/PyCosting_ARPA_E_MFE.ipynb), and click on the "Open in Colab" link at the beginning to open it in https://colab.research.google.com.

(Alternatively, you can download the code notebook .ipynb file or save a copy into google colab (search google colab, then file/upload notebook/ Github/ search for this repo using the url and select a code from the MFE, IFE etc.) currently running from google colab is recommended. If you decide to run the code locally, git handling code and file locations may be different, depending on your OS and environment.
3. Create an Overleaf.com document that is synced with your github fork of this repo.  To avoid possible errors, make sure that in the Overleaf "Menu" (upper left corner) the Settings section says the "Main document" MFE/Costing_ARPA-E_MFE_Modified.tex.
4. Here there are folders for each costing case. Select one, inside there are 'Originals', 'Modified', 'Costing_ARPA-E_x_Modified', 'Costing_ARPA-E_x_Originals' and others. To compile a report with template folders, run 'Costing_ARPA-E_x_Originals'. To edit text, edit files in 'Originals'. Edits made to files in the 'Modified' folder will be overwritten when the code is run.  If you edit files in 'Originals' in Overleaf, afterwards you will need to go to Overleaf Menu, Sync, Github, and 'Push Overleaf changes to github' to save them.  You will then need to rerun the MFE/MFE/PyCosting_ARPA_E_MFE.ipynb in colab to generate new files in Modified.
5. Become a Github collaborator and generate a PAT (ensure it has 'repo' access).
6. Input PAT into first cell of code.
7. Enter inputs in the code MFE/MFE/PyCosting_ARPA_E_MFE.ipynb on colab, and run all cells. This will overwrite all of the files in the 'Modified' subdirectory, by substituting values for variables in the 'Original' template *.tex files.  It will then push the results (the new versions in the 'Modified' subdirectory) back to your github repo.
8. If you edited the code MFE/MFE/PyCosting_ARPA_E_MFE.ipynb in colab, then to save the new version of the code, and the updated version of the output cells from running it, then in colab do "File -> Save a copy in GitHub".
9. Go to your overleaf document, and in Menu, Sync, Github, do a 'Pull GitHub changes into Overleaf'.
10. Process the 'Costing_ARPA-E_x_Modified'.tex file for the corresponding case to generate an updated pdf report.
11. A report should have compiled with the placeholder variables replaced.

12. To edit the text, edit the 'originals' .tex files corresponding to the cost category you would like to edit, in the case folder you are working on.
13. Go to 'Github' on the left tab, and 'push'.
14. Restart code (in colab go 'Runtime/Disconnect and delete runtime' then 'run all'), and repeat steps 3-6.
