# README

This is the README file from the PARSEME verbal multiword expressions (VMWEs) corpus for German, edition 1.2.

The raw corpus is not released in the present directory, but can be downloaded from a [dedicated page](https://gitlab.com/parseme/corpora/-/wikis/Raw-corpora-for-the-PARSEME-1.2-shared-task)

## Corpora

VMWEs have been annotated in the following corpora:

- `WMT.cupt`:
   - sentences 1–7500 from the 2014 edition of the annual Workshop on Statistical Machine Translation, the [WMT 2014 News Crawl: articles from 2013](http://statmt.org/wmt14/translation-task.html#download) (Bojar et al. 2014) 
   - sentence IDs: `newscrawl-1` to `newscrawl-7500`
   - text genre: news
- `UD.cupt`:
   - sentences `train-s1501` to `train-s3000` from v2.5 of the [German part](https://github.com/UniversalDependencies/UD_German-GSD) of the [Universal Dependencies (UD) corpus](http://universaldependencies.org).
   - sentence IDs: `train-s1501` to `train-s3000`
   - text genre: news, reviews, wikis

The raw data is drawn from the same WMT corpus as above, using sentences 1,000,001 up to 11,000,000.

## Provided annotations

The VMWE-annotated data are in the [.cupt](http://multiword.sourceforge.net/cupt-format) format and the raw corpus in the [.conllu](https://universaldependencies.org/format.html) format. Here is detailed information about some columns:

* LEMMA (column 3): Available. Automatically annotated (UDPipe).
* UPOS (column 4): Available. Automatically annotated for `WMT.cupt` and the raw data (UDPipe), manually annotated for `UD.cupt`.
* XPOS (column 5): Available. Automatically annotated for `WMT.cupt` and the raw data (UDPipe), automatically annotated for `UD.cupt` (TreeTagger).
* FEATS (column 6): Available. Automatically annotated (UDPipe).
* HEAD and DEPREL (columns 7 and 8): Available. Automatically annotated for `WMT.cupt` and the raw data (UDPipe), manually annotated for `UD.cupt`. The inventory is [Universal Dependency Relations](http://universaldependencies.org/u/dep).
* MISC (column 10): No-space information available. Automatically annotated.
* PARSEME:MWE (column 11): Manually annotated for `WMT.cupt` and `UD.cupt`. The following [VMWE categories](http://parsemefr.lif.univ-mrs.fr/parseme-st-guidelines/1.1/?page=030_Categories_of_VMWEs) are annotated: IRV, LVC.cause, LVC.full, VID, VPC.full, VPC.semi.

Automated annotation in both the annotated and the raw corpus was performed using [UDPipe with model german-gsd-ud-2.5-191206.udpipe](https://ufal.mff.cuni.cz/udpipe/models#universal_dependencies_25_models).

## Tokenization

- `WMT.cupt` & raw data: the sentence tokenization was performed using the WMT script for German.

- `UD.cupt` & raw data: the word tokenization is that of German UD treebanks with some preposition-determiner contractions being analysed , e.g., *zum* --> *zu dem*, *im* --> *in dem* etc.

- `WMT.cupt`: the word tokenization does not analyse preposition-determiner contractions.

## Statistics
* Annotated corpus:
  * Sentences: 8,996
  * Tokens: 173,562
  * Annotated [VMWEs](http://parsemefr.lif.univ-mrs.fr/parseme-st-guidelines/1.2/?page=030_Categories_of_VMWEs):
	* IRV: 322
    * LVC.cause: 33
    * LVC.full: 311
    * VID: 1434
	* VPC.full: 1744
	* VPC.semi: 194
* Raw corpus:
  * Size (uncompressed): 13 GB
  * Sentences: 10,000,000
  * Tokens: 184,864,965
  * Tokens/sentences: 18.49

## Annotation authors

Building on the VMWE annotations made by Fabienne Cap and Glorianna Jagfeld in v1.0, and the VMWE annotations added and refined by Timm Lichte and Rafael Ehren in v1.1, further corrections have been conducted by Timm Lichte and Rafel Ehren in v1.2.

## License

All VMWEs annotations are distributed under the terms of the [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.
The lemmas, POS-tags, morphological features and dependency tags (contained in the CoNLL-U files) are distributed under the [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0) license, i.e. the same license as the [German Universal Dependencies data](http://universaldependencies.org/#de), on which [UDPipe](https://ufal.mff.cuni.cz/udpipe) was trained. All sentences are distributed under the [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0) license.


## Contact

- timm.lichte@uni-tuebingen.de
- rafael.ehren@hhu.de

## References

Bojar, Ondřej, Christian Buck, Christian Federmann, Barry Haddow, Philipp Koehn, Johannes Leveling, Christof Monz, Pavel Pecina, Matt Post, Herve Saint-Amand, Radu Soricut, Lucia Specia, Aleš Tamchyna. 2014. Findings of the 2014 Conference on Machine Translation. In Proceedings of the Ninth Workshop on Statistical Machine Translation, 12–58. Baltimore, MD: Association for Computational Linguistics. http://statmt.org/wmt14/pdf/W14-3302.pdf


