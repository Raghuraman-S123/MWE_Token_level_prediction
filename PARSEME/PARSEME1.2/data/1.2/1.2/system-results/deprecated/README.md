PARSEME Shared Task 1.2 - system results (DEPRECATED)
========================================================================

This folder contains the raw results of the [PARSEME Shared Task
1.2](http://multiword.sourceforge.net/sharedtaskresults2020) including system
scores and system predictions.  These results were calculated based on the
obsolete definition of a *seen VMWE* are are therefore **deprecated** (see the
note on the webpage for more details).

### Folder structure

Each folder corresponds to a system. The `.closed` or `.open` extensions
indicate to which track the system was submitted. Each system folder contains
one folder per language covered by the system, with two files in it:
 * A `test.system.cupt` file, containing the system predictions for the
    given language in [cupt format](http://multiword.sourceforge.net/cupt-format/)
 * A `results.txt` file containing the scores for the system in that
    language, according to the shared task evaluation metrics

Each system folder also contains a `ave-results.txt` file with the 
macro-averaged results across all languages.

