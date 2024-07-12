A thesis template that approximates the style guidelines of the University of Leeds.

## How to produce a version of your thesis showing changes (for sending to your examiners to show you've done your corrections)

I used `\include` to split up my files while writing so using the `latexdiff` [program on the web](https://3142.nl/latex-diff/) was insufficient in this case. Fortunately I had a local installation of TeX Live, so I used that. This worked on my university computer (MS Windows 11) that I didn't have admin rights for, since TeX Live comes bundled with the perl stuff necessary. 

 1. Make a separate copy of the initial thesis before making any corrections, which we'll need later.
 2. Make all changes to the "new" version, and carry on until happy.
 3. From the *TeX Live command-line* program, produce a version of your old and new thesis versions from your copies without the  `\include` commands as one whole document using `latexpand`, which comes bundled with TeX Live. This didn't work using the command prompt, I needed the TeX Live command line.

`latexpand initial_thesis\main.tex > initial_thesis\old.tex`

`latexpand thesis\main.tex > thesis\new.tex`

 3. Now run `latexdiff` on these two docs to produce a document showing your changes, as desired. We're running locally here (don't mind the precious things) so no need to worry about Overleaf timeouts, or lack of pretty-ness, as this is just to show your examiners that you've made your corrections.
    
`latexdiff initial_thesis\old.tex thesis\new.tex > diff.tex`

4. Now compile `diff.tex` as desired (either locally (why not?) or upload to Overleaf etc.)
   
