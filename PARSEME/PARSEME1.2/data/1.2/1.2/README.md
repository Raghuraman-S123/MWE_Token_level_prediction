README
------
This resource contains the annotated corpora and evaluation scripts for the [PARSEME Shared Task on Verbal Multi-Word Expressions Identification - edition 1.2 (2020)](http://multiword.sourceforge.net/PHITE.php?sitesig=CONF&page=CONF_02_MWE-LEX_2020___lb__COLING__rb__&subpage=CONF_40_Shared_Task).

This resource contains corpora in multiple languages.
Corpora were annotated by human annotators with occurrences of verbal multiword 
expressions (VMWEs) according to common [annotation guidelines](http://parsemefr.lif.univ-mrs.fr/parseme-st-guidelines/1.2/).

This archival version was generated from our [gitlab repository](https://gitlab.com/parseme/sharedtask-data/) - [commit a8e210c3](https://gitlab.com/parseme/sharedtask-data/commit/a8e210c33891fbd89fb2ce6bc441b5fce8a95836)

Corpora
-------
Annotations can be found for multiple language directories,
such as `FR` for French, `DE` for German, `PL` for Polish, etc.
Inside each language directory, you may find these files:

  * `README.md`: A description of the available data for the given language.
  * `train.cupt`: Training data in cupt format.
  * `dev.cupt`: Development data in cupt format.
  * `test.blind.cupt`: Blind test data in cupt format (released to participants on April 30, 2018)
  * `test.cupt`: Gold test data in cupt format (released to participants after the shared task evaluation phase, on May 11, 2018)
  * `{train,test,dev}-stats.md`: Number of sentences, tokens and annotated VMWEs in each part of the corpus.

Note: For some languages, some fields may contain data that does not use the 
[Universal Dependencies](http://universaldependencies.org/) tagsets.


Format
-------
The [cupt format](http://multiword.sourceforge.net/cupt-format) is an extension 
of the [CoNLL-U](http://universaldependencies.org/format.html) format containing 
the original 10 columns from CoNLL-U + 1 additional column `PARSEME:MWE` 
containing VMWE annotations. Depending on the language, different types of 
information are available in the first 10 columns (check the language-specific 
`README.md` files).

The `PARSEME:MWE` column encodes information about VMWEs present in a sentence. 
It is very similar to the fourth column of the 2017 [parsemetsv format](https://typo.uni-konstanz.de/parseme/index.php/2-general/184-parseme-shared-task-format-of-the-final-annotation):

  * It contains a star `*` if the word in the current line is not part of a VMWE, 
    or if the current line describes a multiword tokens (e.g. _2-3 don't_).
  * It contains an underscore `_` if this information is underspecified (e.g. in 
    the blind test corpus).
  * It contains a list of semicolon-separated _VMWE codes_ if the current word 
    is part of one or more VMWEs. VMWE codes are only assigned to the 
    lexicalized components of a VMWE (see [Lexicalized components and open slots](http://parsemefr.lif.univ-mrs.fr/parseme-st-guidelines/1.1/?page=lexicalized) 
    in the annotation guidelines).
    * If the current line contains the **first** lexicalized component of the 
      VMWE in the sentence, the VMWE code consists of a _VMWE identifier_ 
      followed by a colon `:` and a _VMWE category label_, for example: `1:VID`
        * VMWE identifiers are integers starting from 1 for each new sentence, 
          and increased by 1 for each new VMWE.
        * VMWE category labels are strings corresponding to the category of the 
          VMWE (see [VMWE categories](http://parsemefr.lif.univ-mrs.fr/parseme-st-guidelines/1.1/?page=categ) 
          in the annotation guidelines). The following VMWE category labels are 
          allowed in shared task 1.1:
            * `LVC.full`: light-verb constructions in which the verb only adds 
              meaning expressed as morphological features, for example: 
              _to **give** a **lecture**_ (previously LVC).
            * `LVC.cause`: light-verb constructions in which the verb adds a 
              causative meaning to the noun, for example: 
              _to **grant rights**_ (new)
            * `VID`: verbal idioms, for example: 
            _to **go bananas**_ (previously ID).
            * `IRV`: inherently reflexive verbs, for example: 
              _to **help oneself** to the cookies_ (previously IReflV).
            * `VPC.full`: fully non-compositional verb-particle constructions in 
              which the particle totally changes the meaning of the verb, for 
              example: _to **do in**_ (previously VPC).
            * `VPC.semi`: semi-compositional verb-particle constructions, in 
              which the particle adds a partly predictable but non-spatial 
              meaning to the verb, for example: _to **eat up**_ (new).
            * `MVC`: multi-verb constructions, for example: 
              _to **make do**_ (new).
            * `IAV`: inherently adpositional verbs, for example: 
              _to **come across**_ (new).
    * If the current line contains a lexicalized component of the VMWE which is 
      **not the first** one in the sentence, the VMWE code contains the VMWE 
      identifier only, as described above, and no VMWE category label.


Scripts
----------

The `bin` directory contains useful scripts to evaluate and verify the system predictions.

  * `bin/evaluate.py`: script that assesses system predictions according to gold annotations by calculating the [evaluation metrics](http://multiword.sourceforge.net/PHITE.php?sitesig=CONF&page=CONF_04_LAW-MWE-CxG_2018___lb__COLING__rb__&subpage=CONF_50_Evaluation_metrics)
  * `bin/validate_cupt.py`: script for checking if the prediction file is in the proper CUPT format.
  * `bin/average_of_evaluations.py`: script used to calculate cross-lingual macro-averages for general and phenomenon-specific metrics.
  * `bin/tsvlib_usage_example.py`: example script for those who want to use `tsvlib.py` to develop software manipulating CUPT files.

Trial data
----------

The `trial` directory contains trial data. All files have toy sizes (true files are much larger) and all but the last are provided in [CUPT format](http://multiword.sourceforge.net/cupt-format).
Note that, while these trial files are in English, English is not part of the shared task edition 1.2.

  * `EN-trial.train.cupt`: Example of a training corpus in English with manually annotated VMWEs
  * `EN-trial.test.blind.cupt`: Example of a blind version of the test data; systems should take such a file on input and provide automatic predictions of VMWEs in column 11
  * `EN-trial.test.pred.cupt`: Sample system predictions of VMWEs in English
  * `EN-trial.test.cupt`: Example of a gold version of the test data; system predictions will be compared to this gold version
  * `EN-trial.raw.conllu`: Example of a raw parsed corpus for extracting unknown VMWEs, in [CoNLL-U format](https://universaldependencies.org/format.html)


