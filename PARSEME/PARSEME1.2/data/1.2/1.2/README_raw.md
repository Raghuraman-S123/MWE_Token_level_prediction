README - raw data
-----------------

This resource contains the companion "raw" corpora for the [PARSEME Shared Task on Verbal Multi-Word Expressions Identification - edition 1.2 (2020)](http://multiword.sourceforge.net/sharedtask2020).

The corpora are in 14 languages, and were automatically tagged and parsed, mainly using UDPipe (see information for each language below). All the corpora are in [CoNLL-U](https://universaldependencies.org/format.html) format.
This archival version was generated from the [dedicated page of the PARSEME 1.2 shared task concerning raw corpora](https://gitlab.com/parseme/corpora/-/wikis/Raw-corpora-for-the-PARSEME-1.2-shared-task).


### How data was prepared and checked

For each language, we provide one or several `.tgz` files, each containing a list of `.xz` compressed files. The `.xz` files are named `raw-001.conllu.xz` to `raw-xxx.conllu.xz` where _xxx_ is the total number of files for the language.
Each conllu file should be a valid CoNLL-U file.
A subset of the first 1,000 sentences of most files has been validated with the UD validation script with the command:
```bash
validate.py --lang=ud --level=2 file
```


Level 2 validation ensures that, for each sentence:
 - there is a `# text` line, a `# sent_id` line
 - the POS and DEPREL are compliant with UD 2
 - the syntactic annotation is a well formed tree


## Information for each language

In this release, the `.xz` files were further archived into one or several `.tgz` files.

### German (DE)

The raw corpus corresponds to sentences 1,000,001 up to 11,000,00 from the [WMT 2014 News Crawl: articles from 2013](http://statmt.org/wmt14/translation-task.html#download) (Bojar et al. 2014).

* sentences: 10,000,000
* tokens: 184,864,965

[Bojar, Ondřej, Christian Buck, Christian Federmann, Barry Haddow, Philipp Koehn, Johannes Leveling, Christof Monz, Pavel Pecina, Matt Post, Herve Saint-Amand, Radu Soricut, Lucia Specia, Aleš Tamchyna. 2014. Findings of the 2014 Conference on Machine Translation. In Proceedings of the Ninth Workshop on Statistical Machine Translation, 12–58. Baltimore, MD: Association for Computational Linguistics.](http://statmt.org/wmt14/pdf/W14-3302.pdf)

### Greek (EL)

The raw data were drawn from the Greek section of the [CoNLL 2017 shared task corpus](http://hdl.handle.net/11234/1-1989), as well as the newswire and wikipedia subcorpora [Leipzig Corpus collection](https://wortschatz.uni-leipzig.de/en/download/) (Goldhahn et al., 2012). They were re-parsed with  UDPipe using the `greek-gdt-ud-2.5-191206` model.

* sentences: 1,044,268
* tokens: 25,559,954

[D. Goldhahn, T. Eckart & U. Quasthoff: Building Large Monolingual Dictionaries at the Leipzig Corpora Collection: From 100 to 200 Languages. In: Proceedings of the 8th International Language Resources and Evaluation (LREC'12), 2012](http://www.lrec-conf.org/proceedings/lrec2012/pdf/327_Paper.pdf)

### Basque (EU)

The raw corpus for Basque are sentences from the [Berria](https://www.berria.eus/) Basque newspaper, automatically annotated using [UDPipe](http://ufal.mff.cuni.cz/udpipe), based on the [Basque model](https://ufal.mff.cuni.cz/udpipe/models), within the HiTZ Basque center for language technology, Ixa NLP group, University of the Basque Country.

* sentences: 1,327,630
* tokens: 21,268,325

### French (FR)

The raw corpus for the PARSEME 1.2 shared task contains about two thirds of the French wikipedia (dumped on Dec 12, 2016).

More precisely, the corpus contains 34 million sentences (out of a total of 46.7 million sentences), minus 20,919 sentences (corresponding to 5,911 unique sentences), which have been removed because they were found in the VMWE-annotated corpus.
So the precise number of sentences is 33,979,081 sentences, and contains none of the sentences appearing in the VMWE annotated corpus.

The raw corpus is tokenized into a little less than 1 billion tokens (914 824 075 tokens), and parsed with [UDPIPE](http://ufal.mff.cuni.cz/udpipe), using the [french-gsd-ud-2.5-191206.udpipe model](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-3131).

Each file contains around 1 million sentences and 27 million tokens. NB: the text in the `# text` lines of the CONLLU files is NOT the original text but a bare space-separated concatenation of the tokens.

* sentences: 33,979,081
* tokens: 914,824,075

### Irish (GA)

The raw corpus for Irish, consisting of 1,379,824 dependency parsed trees in CoNLL-U format, is a compilation of various sources of raw text data, which have been automatically tokenised, POS-tagged, lemmatised, morphologically analysed and dependency parsed with the UDPipe tool, using the [irish-idt-ud-2.5-191206.udpipe model](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-3131). 
The tagset used was the same as that of the annotated corpus. The raw text was compiled from the following sources:

* Citizens Information: 10,297 sentences crawled from the Citizen’s Information Ireland website (https://www.citizensinformation.ie/ga/)
* EU Bookshop: 133,363 sentences from the EU bookshop, accessed from the Opus website (http://opus.nlpl.eu/EUbookshop.php)
* Paracrawl: 782,769 sentences from the Irish side of the Paracrawl data, accessed from the Opus website (http://opus.nlpl.eu/ParaCrawl.php)
* Tatoeba: 1,894 translated sentences from the Tatoeba corpus, accessed from the Opus website (http://opus.nlpl.eu/Tatoeba.php)
* Vicipéid: 302,838 sentences from the Irish Wikipedia text dump (https://dumps.wikimedia.org/gawiki/20200220/)

As the data was automatically compiled and processed, the quality cannot be assured. Text from EU bookshop, Paracrawl and Tatoeba was translated from the original source. The genre is a mixture of general, legal, and news. Some automatic cleaning was performed, but noisy text, including boilerplate text may still be included.

Text from the Citizen’s Information contains Irish Public Sector Data licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) licence.

Text from ParaCrawl is under the Creative Commons CC0 Licence (“no rights reserved”).

Text from the EU bookshop is available for free download from the Opus website for open-source data. No licence was specified with the data.

Text from Tatoeba corpus is available under the CC–BY 2.0 FR licence.

Vicipéid (Irish Wikipedia) data is licensed under the GNU Free Documentation License (GFDL) and the Creative Commons Attribution-Share-Alike 3.0 License.

* sentences: 1,379,824
* tokens: 34,211,598

### Hebrew (HE)

The Hebrew raw corpus was taken from [MILA knowledge Center for Processing Hebrew](https://yeda.cs.technion.ac.il/resources_corpora.html)

* sentences: 451,408
* tokens: 12,867,409

### Hindi (HI)

The raw corpus for Hindi is a part of the [HindiMonocorp](https://lindat.mff.cuni.cz/repository/xmlui/handle/11858/00-097C-0000-0023-6260-A) which has been scraped from the web. It has been automatically parsed using the model `model hindi-hdtb-ud-2.5-191206.udpipe`.

* sentences: 3,597,653
* tokens: 77,964,199

### Italian (IT)

The raw corpus for Italian consists of the entire [PAISÀ Corpus](https://www.corpusitaliano.it/) converted to CoNLL-U format, except for the sentences present in the annotated corpus and few faulty sentences (those containing invalid HEAD fields).

* sentences 12,280,673
* tokens: 281,418,631

### Polish (PL)

The raw corpus for Polish originates from the [CoNLL 2017 shared task raw corpus](http://hdl.handle.net/11234/1-1989) for Polish (see the [paper](https://www.aclweb.org/anthology/K17-3001.pdf#page=3)).

* sentences: 159,115,022
* tokens: 1,902,279,431
* genre: Wikipedia pages and various other web pages (from CommonCrawl)
* morpho-syntactic tagging: upgraded to a [UD-2.5](http://hdl.handle.net/11234/1-3105)-compatible version with [UDPipe](http://ufal.mff.cuni.cz/udpipe) using the [polish-pdb-ud-2.5-191206](https://lindat.mff.cuni.cz/repository/xmlui/bitstream/handle/11234/1-3131/polish-pdb-ud-2.5-191206.udpipe?sequence=76&isAllowed=y) model (same as for the automatically tagged parts of the manually annotated corpus)

### Brazilian Portuguese (PT)

The raw corpus for Brazilian Portuguese has two sources: 
  * files `raw-001.conllu.gz` through `raw-018.conllu.gz` correspond to the Wikipedia dump provided in the [raw corpora of the CoNLL 2017 shared task](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-1989). The files were re-parsed using UDPipe, as described below. 
  * file `raw-019.conllu.gz` corresponds to articles from the Folha de São Paulo newspaper provided by Oto Vale. The files were parsed using UDPipe, as described below.

* sentences: 26042884
* tokens: 306603890
* genre: Wikipedia pages and newspaper (Folha)
* morpho-syntactic tagging: upgraded to a [UD-2.5](http://hdl.handle.net/11234/1-3105)-compatible version with [UDPipe](http://ufal.mff.cuni.cz/udpipe) using the [portuguese-bosque-ud-2.5-191206.udpipe](https://lindat.mff.cuni.cz/repository/xmlui/bitstream/handle/11234/1-3131/portuguese-bosque-ud-2.5-191206.udpipe?sequence=75&isAllowed=y) model (same as for the automatically tagged parts of the manually annotated corpus)

### Romanian (RO)

The raw corpus for the PARSEME 1.2 shared task contains 447,464 sentences from online Romanian newspapers. All texts were shuffled so that the original articles cannot be recovered. The corpus is tokenized into 12,822,588 tokens and parsed with [UDPIPE](http://ufal.mff.cuni.cz/udpipe). The model used is [romanian-rrt-ud-2.5-191206`](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-3131). The corpus is split into 100 files of almost the same size. The corpus processing was performed by Elena Irimia.

* sentences: 477,313
* tokens: 12,680,325

### Swedish (SV)

The raw corpus for Swedish is a part of the [CoNLL 2017 shared task raw corpus](http://hdl.handle.net/11234/1-1989) for Swedish (see the [paper](https://www.aclweb.org/anthology/K17-3001.pdf#page=3)). It was parsed using UDPipe baseline system, trained on Swedish-Talbanken version 2.0 (model: swedish-ud-2.0-conll17-170315.udpipe).

* sentences: 163,633,807
* tokens: 2,474,800,065
* genre: Various web pages (from CommonCrawl)

### Turkish (TR)

The Turkish Raw corpus comes from the Turkish newspaper corpus introduced in [Sak et al. (2019)](https://www.cmpe.boun.edu.tr/~gungort/papers/Resources%20for%20Turkish%20Morphological%20Processing.pdf). The corpus has been annotated using UDPipe, relying on the model: [turkish-imst-ud-2.4-190531.udpipe](http://hdl.handle.net/11234/1-2998)

* sentences: 1,390,791
* tokens: 19,463,230

### Chinese (ZH)

The raw corpus was taken from the [CoNLL 2017 shared task raw corpus](http://hdl.handle.net/11234/1-1989) for Chinese. It contains 4 files:
 * `raw-001.conllu`
    * origin: `conll2017-crawl-000`
    * sentences: 348,935
    * tokens: 5,150,812
 * `raw-002.conllu`
    * origin: `conll2017-crawl-001`
    * sentences: 1,175,265
    * tokens: 18,450,549
 * `raw-003.conllu`
    * origin: `conll2017-crawl-002`
    * sentences: 1,144,700
    * tokens: 18,588,146
 * `raw-004.conllu`
    * origin: `conll2017-wiki-000`
    * sentences: 1,438,279
    * tokens: 25,046,404

* sentences: 4,107,179
* tokens: 67,235,911


