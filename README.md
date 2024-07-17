**The code in this Github repo aims to provide a standard costing tool for fusion power plants based on IAEA 2001 and GenIV 2007 cost accounts, entailing Magnetic Fusion Energy, Magneto Inertial Fusion and Inertial Fusion Energy.**  

### Background:

This repo is a modified version of https://github.com/Woodruff-Scientific-Ltd/ARPAE-PyFECONS, which is an open source public release to document the general approach and data used in some fusion reactor costing projects by Woodruff Scientific Ltd funded by ARPA-E.  For a video talk describing the code, see:
https://www.linkedin.com/posts/activity-7193175795689738241-4jxT/ 

GWH: I've made changes only to files in the MFE folder.  These were minor changes to fix some latex errors that prevented making the final pdf report, minor changes to the python code to make it easier for a user to be able to set up their own cases and do runs with out affecting the main github repo, and a few other minor changes.
Caution: the upstream (original) repo was released as-is with no plans for support, and there are known limitations and various levels of approximations in it that persist in this present forked version. You should not use this code for any serious work without understanding it and going through all of the code to set up the proper inputs for your case.  (Commercial versions of this software have a number of fixes and more detailed analysis relative to this open-source version.) Search https://github.com/gwhammett/ARPAE-PyFECONS/blob/main/MFE/PyCosting_ARPA_E_MFE.ipynb for "??" to find some of the known places that could use further work.

### How to run this code:

This Github repo contains a folder for each base case (IFE, MFE, MIF), and one for the benchmark cases. Each folder contains the main python costing code in a .ipynb file, the template text for each cost category in the 'Originals' folder, and other files required for the latex document to compile. To generate a report:

1. Initial setup only:  Fork (or clone) your own copy of this github repo.  (Don't bother trying to create a branch, overleaf only works with a main branch.)
2. Overleaf setup and usage:
    1. Initial setup only: Create an Overleaf.com document that is synced with your github fork of this repo.  (This can sometimes take a couple of minutes.)  To avoid possible confusion, make sure that in the Overleaf "Menu" (upper left corner), the Settings section says the "Main document" is the desired one (for me, MFE/Costing_ARPA-E_MFE_Modified.tex).
    2. In Overleaf, there are folders for each costing case. Select one  Inside there are 'Originals', 'Modified', 'Costing_ARPA-E_x_Modified.tex', 'Costing_ARPA-E_x_Originals.tex' and others. To compile a report from a past run of the code, compile 'Costing_ARPA-E_x_Modified.tex', which uses info in the Modified folder.
    3. To see the template form of the report (before specific values are inserted for variables) compile 'Costing_ARPA-E_x_Originals.tex', which uses info in the Originals folder.
3. Initial setup only:  Create a GitHub PAT for your github repo and put it in a file Colab-private/ARPAE-PyFECONS-PAT.txt in your google drive.  (A PAT is a Personal Access Token, essentially a long password.  Keep this PAT confidential, as it gives write access to your GitHub repo.  This will be used by the python costing code run in colab to write results back to github, where it will be read by overleaf.com to make the final pdf report.)
4. Go to the main python notebook in the github subdirectory you are working on, like [MFE/PyCosting_ARPA_E_MFE.ipynb](MFE/PyCosting_ARPA_E_MFE.ipynb) <br> (I have focussed only on the MFE version so far), and click on the "Open in Colab" icon/link at the beginning to open it in https://colab.research.google.com. \
(Alternatively, you can upload the code notebook .ipynb file from github to colab.  In google colab, go to file -> upload notebook -> Github, search for your repo using the url, and select a code from an MFE, IFE, etc. directory).) Currently, running from google colab is recommended. If you decide to run the code locally, git handling code and file locations may be different, depending on your OS and environment.
5. Edit the first code cell of the .ipynb code to set some parameters which point to your github repo.
6. Enter other inputs in the \*.ipynb code if desired (such as the parameters in various places in the code that describe the reactor design being costed) or just use the default values.
7. In the colab menu, go to Runtime and select Run all cells. (Or if this is a repeat run, in colab do Runtime -> "Restart Ssession and run all".) This will do the costing calculations and overwrite all of the files in the 'Modified' subdirectory, by substituting values for variables in the 'Original' template *.tex files.  It will then push the results (the new versions in the 'Modified' subdirectory) back to your github repo.
8. If you edited the \*.ipynb code in colab, then to save this file, in colab do "File -> Save a copy in GitHub".
9. Go to your overleaf document, and in Menu, Sync, Github, do a 'Pull GitHub changes into Overleaf'.
10. Recompile the corresponding tex file (Costing_ARPA-E_x_Modified.tex in this example) to generate an updated pdf report.
11. To edit text in the final report,
    1. In Overleaf, edit the 'Originals' .tex files corresponding to the cost category you would like to edit, in the case folder you are working on. (Edits made to files in the 'Modified' folder would be overwritten when the code is run.)
    2. In the Overleaf Menu, Sync, Github, and 'Push Overleaf changes to github' to save them.
    3. Rerun the MFE/PyCosting_ARPA_E_MFE.ipynb code (in colab do 'Runtime/Restart session and run all')) to generate new files in the Modified folder in the github repo.  Then redo steps 9-10 above.
