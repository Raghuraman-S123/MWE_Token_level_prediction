README
------
This directory contains the trial data for the [PARSEME shared task on automatic identification of verbal multiword expressions - edition 1.2](http://multiword.sourceforge.net/sharedtask2020).

Files
-------

All the files have toy sizes (true files will be larger) and all but the last are provided in the [cupt format](http://multiword.sourceforge.net/cupt-format). Note that, while these trial files are in English, English is not part of the shared task edition 1.2. 

  * `EN-trial.train.cupt`: Example of a training corpus in English with manually annotated VMWEs
  * `EN-trial.test.blind.cupt`: Example of a blind version of the test data; systems should take such a file on input and provide automatic predictions of VMWEs in column 11
  * `EN-trial.test.pred.cupt`: Sample system predictions of VMWEs in English 
  * `EN-trial.test.cupt`: Example of a gold version of the test data; system predictions will be compared to this gold version
  * `EN-trial.raw.conllu`: Example of a raw parsed corpus for extracting unknown VMWEs

