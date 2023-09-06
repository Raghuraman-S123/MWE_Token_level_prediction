PARSEME Shared Task 1.2 - system results
========================================================================

This folder contains the raw results of the [PARSEME Shared Task
1.2](http://multiword.sourceforge.net/sharedtask2020/) including system scores
and system predictions.  Note that these results were corrected due to the
change of the definition of a *seen VMWE* (see the note on the PARSEME webpage
for more details).  The deprecated results can be found in the `deprecated`
folder.

### Folder structure

Each folder (with the exception of `deprecated`) corresponds to a system. The
`.closed` or `.open` extensions indicate to which track the system was
submitted. Each system folder contains one folder per language covered by the
system, with two files in it:
 * A `test.system.cupt` file, containing the system predictions for the
    given language in [cupt format](http://multiword.sourceforge.net/cupt-format/)
 * A `results.txt` file containing the scores for the system in that
    language, according to the shared task evaluation metrics

Each system folder also contains a `ave-results.txt` file with the 
macro-averaged results across all languages.

