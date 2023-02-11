---
title: "Editing mundane texts across the digital divide"
subtitle: "The case of Arabic periodicals from the late nineteenth-century Eastern Mediterranean"
project: "Digital Humanities in Practice"
author: Till Grallert
date: 2023-02-01
status: draft
ORCID: orcid.org/0000-0002-5739-8094
DOI: 
licence: http://creativecommons.org/licenses/by-nd/4.0/
bibliography: 
	- /Users/Shared/BachUni/publications/github/p0fb41f86/assets/bibliography/bootstrapped-scholarly-editions.csl.json
    - /Users/Shared/BachUni/publications/github/pae326271/assets/bibliography/2023_dh-in-practice.csl.json
    - /Users/Shared/BachUni/research-projects/OpenArabicPE/assets/bibliography/openarabicpe.csl.json
suppress-bibliography: false
reference-section-title: "Bibliography"
abstract:
lang: en-US
tags:
    - pae326271
---

<!-- pre-process with pancritic -->
<!-- pancritic editing-across-the-digital-divide.md -t markdown --critic-mode accept -o editing-across-the-digital-divide_changes-accepted.md -->
<!-- beware that the wrapping brackets around pandoc citations must be removed from footnotes if they should not be wrapped in parentheses in the formatted output
    - Regex: \[([^\[]*?@.*?)\]
 -->

## Introduction

In 2015, I had just finished my PhD on the history of the street in late Ottoman Damascus (1875--1914) and moved to Beirut for a new post-doctoral research project on the genealogy of food riots across the predominantly Arabic-speaking Eastern Mediterranean from the nineteenth century to the present [@Grallert+2019]. 
The main source for both projects were periodicals---tens of thousands of newspaper and magazine articles published in Arabic and Ottoman Turkish across the region. But despite their quotidian nature, their pivotal role for central cultural phenomena of the time as the region's first mass medium, and ubiquitous references in scholarly literature, surprisingly little of substance is known about this medium in terms of individual publication histories, distribution channels, and audiences or the number and whereabouts of surviving copies. This is particularly true for periodicals published outside the centers of the press in Beirut and Cairo.[^cf1]

The sheer size of the corpus and the focus on social history suggests we muster help of computational tools and networked infrastructures. Working with textual material in Arabic---one of the six official working languages of the United Nations but also a severely under-resourced language in the digital realm---and in a region with  limited access to utilities  forces us to reckon with the nitty-gritty details of the multidimensional infrastructural underpinnings of modern scholarship.

This is not a theoretical essay on the politics of digitization as a continuation of much older politics of archives, preservation and reproduction of cultural heritage, and ultimately the politics of representation embodied in the question of who writes history and of whom [C.f. @Zaagsma2022DigitalHistoryPolitics; @Thylstrup+2018; @Risam+2019; @Fiormonte2021Taxation; @Grallert2022DHQ; @Grallert2021GG].  Instead, I focus on the practical consequences, the always concrete affordances these politics create for the digitization of a specific society's cultural  record.

The two projects featured in this essay, [Jarāʾid][jaraid], a union list of all Arabic periodical titles published globally until 1929, and Open Arabic Periodical Editions ([OpenArabicPE]{.Abbreviation custom-style="Abbreviation"})[^fn1], a framework for scholarly digital editions of such periodicals, were born out of two interconnected needs and with a simple idea: Creatively repurpose existing open data, tools, and infrastructures in order to provide sustainable public and free access to reliable knowledge about periodicals as well as high-quality digital editions and to do so not just in Latinized transcriptions as is established scholarly practice in the Global North but in their original script and languages.
Both projects can be considered fairly successful attempts at applying a minimal computing approach to address our severely limited resources: Jarāʾid currently holds information on 3550  periodical titles , including holding-information on 775 titles in 233 library collections and links to  233 at least partially digitized titles. [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"} provides a corpus of openly accessible digital scholarly editions of six journals published between 1892 and 1918 in Baghdad, Beirut, Cairo, and Damascus with a total of 41 volumes, 645 individual issues, and more than 6 million words.



The first part of this essay is concerned with creating the necessary knowledge about the history of the Arabic periodical press, its material artifacts, and existing digital remediations. It introduces catalogues as historical documents and the consequences of hegemonic  technological infrastructures of the Global North for creating and recording  knowledge about cultural artifacts and practices of societies in the Global South. Here, I use Arabic as a prime example how character encodings, rendering engines, and a complete lack of interest from market-dominating software vendors and platforms exercise epistemic violence [@Fiormonte2021Taxation]. Finally, I discuss our project to produce a crowd-sourced union list of all Arabic periodicals published until 1929.

The second part turns to making cultural artifacts accessible to human readers and computational methods. It briefly discusses existing digital artifacts as being limited by the state of OCR-technologies and fractured data silos, paywalls, and geofencing before I turn to our project Open Arabic Periodical Editions as a practical critique of infrastructures of exclusion.

## Creating knowledge about artifacts

The first need, therefore, was (and still is) a need for improving our knowledge about periodicals as the embodiment of socio-economic relations, intellectual traditions, and political frameworks, their manifestation in a limited number of material artifacts, the transmission of individual artifacts into private and public collections, and finally their occasional digital remediation. In order to investigate the extent of food riots across cities of the Syrian hinterland in summer 1910 [C.f. @Grallert+2019], one would need to know which papers, if at all, were published in Hama, Homs or Nablus and therefore potentially printed eye-witness accounts ([@fig:map-periodicals-1908-12] presents such information based on our cataloguing project introduced below). One would then need to establish if copies survived the turmoil that  wreaked havoc upon the region and its cultural  record over the last century, where to find surviving copies, and how to access them.

![Map of all new Arabic periodicals published in Greater Syria between 1908 and 1912 based on [@MestyanEtAl2020JaraidDataset]](/Users/Shared/BachUni/publications/github/pae326271/assets/images/map-periodicals_Bilād al-Shām_1908-1912_temp-dist.png){#fig:map-periodicals-1908-12}

At this point we have to acknowledge that digitization is political and inseparable from multi-layered digital divides---a chicken-egg problem of interwoven knowledge systems, representations, and socio-technical infrastructures that is difficult to tease apart.

Despite quotidian impressions to the contrary, many library catalogues have not been digitized or published online. This is particularly true for institutions outside the Global North and collections of material from the Global South. The website of the Lebanese National Library, for instance, still advertises its catalogue as forthcoming. Manually compiled union catalogues are a Herculean task and have largely fallen out of fashion with the advent of COPACs. Given their publication dates and the necessary time for information collection, they should probably be read as historical sources rather than finding aids [E.g. @ElHadi+1965; @Hopwood+1970; @Aman+1979; @DeJong+1979; @Iḥdādan+1984; @Khūrī+1985; @Höpp+1994; @Atabaki+1995]. Likewise, library catalogues are layered historical documents that accumulate traces of their socio-technic affordances with each remediation. Looking at one of the many entries for [ʿAbdallāh Nadīm al-Idrīsī]{.persName custom-style="persName"}'s weekly journal [al-Ustādh]{.Transcription custom-style="Transcription"}, published in Cairo from 1892 to 1893, in Worldcat, we most likely will not encounter a record newly created from the material artifact by an expert cataloguer with domain knowledge in Arabic periodicals and the ability to read Arabic script. Even  if she will most likely have had to contend with technological systems ill-suited, if not unable, to deal with the metadata in its original script, calendars or naming conventions.

### The representational power of monolingual infrastructures and Latin script

Arabic is  one of the main human languages with more than 420 million speakers  as well as a writing system for many historic and contemporary Asian and African languages, such as Persian, Urdu, Pashtu, Ottoman, Uzbek or Uighur [@Mumin.Versteegh+2014+TheArabicScript]. The script is written from right to left, most letters connect in the writing direction within a word, and letters have up to four  letterforms depending on their position within a string. Multiple letters share the same basic  letterform ([rasm]{.Transcription custom-style="Transcription"}).  Diacritical signs ([iʿjām]{.Transcription custom-style="Transcription"}), mostly dots below and above the [rasm]{.Transcription custom-style="Transcription"}, allow to decrease semantic ambiguity. Depending on writing style and typefonts, multiple letterforms  will form ligatures. Letterforms and ligatures will not necessarily sit on a single baseline and baselines can be tilted ([@fig:arabic]). There are only few exceptions to these script-specific writing rules across languages. Importantly for us, the diacritics are not strictly necessary for readers as is evidenced by recent efforts at circumventing surveillance and censorship of authoritarian Arab regimes by using (an approximation of) the [rasm]{.Transcription custom-style="Transcription"} on social media. Furthermore, their use is subject to changing cultural preferences. Some regional practices all but omit them from specific letters, particularly at the end of a word.[^fn2]

![Example of basic Arabic typesetting from [@oclc_4770057679-i_13-div_8.d1e1249]: "America and the Arab scholars". The red arrow indicates the reading direction. Words are underlined in [*red*]{.EmphasisCustom custom-style="EmphasisCustom"}. Ligatures of multiple letters are underlined in [*green*]{.EmphasisCustom custom-style="EmphasisCustom"}.](/Users/Shared/BachUni/publications/github/pae326271/assets/imagesarabic-script_annotated.png){#fig:arabic}

Type-written card-catalogues, hot-metal printing presses, electronic computers (understood as an interdependent combination of hardware and software) form a global hegemonic technology stack bound up in historically contingent cultural traditions of the Global North. Mechanically and, later, electronically recording information in scripts other than Latin---particularly complex scripts with a much larger number of graphemes and different writing directions---was never considered sufficiently important or profitable to be supported out-of-the-box [@Nemeth2018ArabicHotMetal; @Singh+2018+TheMachineIn].
Computational systems  not only derive from their type-setting ancestors and enforce Latin script grammar upon other writing systems, they also inherited the concept of national languages and do not consequently distinguish between scripts and languages. The character-encoding standard Unicode enabled vendor-independent exchange and interoperability of texts in Arabic script but it continues to adhere to the script grammar of Latin and the affordances of movable type-printing [c.f. @FiormonteEtAl2015PoliticsOfCode, 3-4].[^fn3] Unicode's organizing principle of code points is a confusing combination of scripts and languages that results in multiple code points for the same glyph.
Anybody entering Arabic texts into a computer has to select one specific interpretation, one and only one Unicode representation of a textual string they want to encode. They have to either normalize historical or geographic orthographic variance or pick visually-matching but technically "wrong" glyphs.  The resulting large variety of encodings for the same string of Arabic letterforms depends largely on the language of operating systems and keyboard settings on the input device [c.f. @VeisiEtAl2020KurdishLanguageProcessing].
Egyptian cultural preferences, for instance, would virtually always omit the two dots underneath a final [yāʾ]{.Transcription custom-style="Transcription"} (U+064A: [ي]{.Arabic custom-style="ArabicScript"}). To mirror such cultural preferences, one can either select the Arabic [alif maqṣūra]{.Transcription custom-style="Transcription"} (U+0649: [ى]{.Arabic custom-style="ArabicScript"}) or the Persian [ye]{.Transcription custom-style="Transcription"} (U+06CC: [ی]{.Arabic custom-style="ArabicScript"}) [c.f. @TaghiZadehEtAl2017NewHybridStemming]. Unfortunately, search algorithms built into modern operating systems are not aware of these variances and any application software relying on them will return skewed results without additional efforts at regularization or a reduction to the [rasm]{.Transcription custom-style="Transcription"} [@Milo.Martinez+2019+ANewStrategy].

The necessary human-machine interfaces for interacting with digital information present another layer of inaccessibility for those wanting to engage with Arabic text as encoding and rendering information are two different steps. 

Support for the correct rendering of Arabic with connected letters, from right-to-left, and right-aligned is growing but remains hit-and-miss depending on operating systems and software applications---even on the web. [HTML5]{.Abbreviation custom-style="Abbreviation"} is the current standard for structuring and presenting content on the World Wide Web. Developed since the  mid-2000s, [HTML5]{.Abbreviation custom-style="Abbreviation"} is maintained as a "living standard" by the [*Web Hypertext Application Technology Working Group*]{.EmphasisCustom custom-style="EmphasisCustom"} ([WHATWG]{.Abbreviation custom-style="Abbreviation"}), whose members are the leading vendors of web browsers: Apple, Google, Microsoft, and Mozilla. Most importantly for our discussion, [HTML5]{.Abbreviation custom-style="Abbreviation"} added the global `@lang` attribute, which mirrors the earlier `@xml:lang` attribute for explicitly specifying the language of a document or parts thereof through the use of [BCP]{.Abbreviation custom-style="Abbreviation"} 47 language tags, such as "ar" for Arabic or "en" for English [@BCP47]. Yet, despite having been originally developed in 2008 and being maintained by an industry consortium of leading browser vendors, no major modern web browser, however, uses the `@lang` attribute in their built-in [CSS]{.Abbreviation custom-style="Abbreviation"} for text-alignment or font selection. Even if a website declares its content as being written in Arabic, browsers such as Chrome, Firefox or Safari, do not correctly render the text as right-aligned ([@fig:arabic-fail-chrome]).  The necessary fix requires only a single line of code (`*[lang^="ar"] {direction:rtl;}`)---from everyone publishing text in right-to-left scripts on the Web. The problem is not purely aesthetic. Trailing punctuation marks, for instance, become leading punctuation marks without these adjustments (Final line on [@fig:arabic-fail-chrome]).

![The beginning of [@oclc_4770057679-i_13-div_8.d1e1249] as rendered in Chrome](/Users/Shared/BachUni/publications/github/pae326271/assets/images/html5-lang_ar-chrome.png){#fig:arabic-fail-chrome}

<!-- ![The beginning of [@oclc_4770057679-i_13-div_8.d1e1249] as rendered in Firefox](https://tillgrallert.github.io/slides/assets/dh/html5-lang_ar-firefox-2.png){#fig:arabic-fail-firefox} -->

This lack of support is not limited to viewing content. Software for editing digital editions marked up in [*Extensible Markup Language*]{.EmphasisCustom custom-style="EmphasisCustom"} ([XML]{.Abbreviation custom-style="Abbreviation"}) following the guidelines of the [*Text*]{.EmphasisCustom custom-style="EmphasisCustom"}
[*Encoding Initiative*]{.EmphasisCustom custom-style="EmphasisCustom"} ([TEI]{.Abbreviation custom-style="Abbreviation"}) [@TEIP5Guidelines400] represent the same attitude in their [CSS]{.Abbreviation custom-style="Abbreviation"} to render a more human-friendly view of the commonly verbose [XML]{.Abbreviation custom-style="Abbreviation"} files. The developers of the  popular oXygen [XML]{.Abbreviation custom-style="Abbreviation"} editor added the relevant [CSS]{.Abbreviation custom-style="Abbreviation"} for rendering [TEI/XML]{.Abbreviation custom-style="Abbreviation"} in their "author mode" in 2015 (v17, see [@fig:bidi-xml-oxygen-author]) and in response to our feature request. But this support for correctly rendering Arabic and some other [RTL]{.Abbreviation custom-style="Abbreviation"} languages is limited to [TEI/XML]{.Abbreviation custom-style="Abbreviation"}.

This leads to another major issue in the insufficient support for Arabic in the digital realm: the display of bi-directional text on a two-dimensional surface (as opposed to the logical character sequence, which is a one-dimensional string), particularly on the same line, which is necessary for editing Arabic content in most standard formats. If we assume writing directions differ only in one dimension, such as left-to-right and right-to-left, but all scripts otherwise follow the same direction in the second dimension, such as top-to-bottom, it is impossible to decide whether both scripts are of equal importance to the text or which one takes precedence over the other. [XML]{.Abbreviation custom-style="Abbreviation"} is fully unicode-compliant and supports tag and attribute names in any script as long as they can be encoded in unicode. Only the [XML]{.Abbreviation custom-style="Abbreviation"} declaration (`<?xml version="1.0" encoding="UTF-8"?>`) at the very beginning of the file needs to be written in Latin script. According to the unicode bidirectional (bidi) algorithm, this establishes left-to-right as the  [*base direction*]{.EmphasisCustom custom-style="EmphasisCustom"} and causes all computational tools to assume that they encounter a document with a left-to-right reading order (that at this point might or might not include bits and pieces in other writing systems) ([@fig:bidi-xml-oxygen]) [@W3CUnicodeBiDiBasics; @ICUDocumentationBiDi].




::: columns
:::: column

![Example of bidirectional [XML]{.Abbreviation custom-style="Abbreviation"}  of [@oclc_1034545644-i_15-div_1.d2e634]. The colored arrows indicate reading direction. The reading order is indicated by the numbers below the arrows](/Users/Shared/BachUni/publications/github/pae326271/assets/imagesxml_zuhur-v_2-i_4_annotated.png){#fig:bidi-xml-oxygen}

::::
:::: column

![Example of bidirectional [XML]{.Abbreviation custom-style="Abbreviation"}  of [@oclc_1034545644-i_15-div_1.d2e634] as displayed in an editor without support for right-to-left scripts](/Users/Shared/BachUni/publications/github/pae326271/assets/images/sublime_zuhur-bright.png){#fig:bidi-xml-sublime-text}

::::
:::

![Correctly rendered bidirectional [XML]{.Abbreviation custom-style="Abbreviation"} of [@oclc_1034545644-i_15-div_1.d2e634] in oXygen's author mode](/Users/Shared/BachUni/publications/github/pae326271/assets/images/oxygen_zuhur-author.png){#fig:bidi-xml-oxygen-author}

Beyond the fundamental impossibility to adequately record written Arabic in digital form, the cultural  record and practices of societies from the Global South require constant efforts of translation and transcription, themselves intrinsically entangled with the socio-technical traditions of the Global North [C.f. @DuganMontpellier2021MultipleScripts]. The aforementioned journal [al-Ustādh]{.Transcription custom-style="Transcription"} is a simple, yet powerful example. "[al-Ustādh]{.Transcription custom-style="Transcription"}" is, of course, a transliteration of the Arabic title
 [الاستاذ]{.Arabic custom-style="ArabicScript"}
into Latin script, as is the rendering of the publisher's name 
[عبد الله النديم الإدريسي]{.Arabic custom-style="ArabicScript"}
 as [ʿAbdallah al-Nadīm al-Idrīsī]{.persName custom-style="persName"}. These transcriptions follow the widely adopted system of the [*International Journal of Middle East Studies*]{.EmphasisCustom custom-style="EmphasisCustom"} ([IJMES]{.Abbreviation custom-style="Abbreviation"}). Catalogers in German-speaking countries would follow a system with 1:1 character transliterations devised by the [*Deutsche Morgenländische Gesellschaft*]{.EmphasisCustom custom-style="EmphasisCustom"} ([DMG]{.Abbreviation custom-style="Abbreviation"}) and record the title as [al-Ustāḏ]{.Transcription custom-style="Transcription"}. In addition to the output language, transcription schemes differ between input languages in the same script. The British Library's [*Endangered Archives Programme*]{.EmphasisCustom custom-style="EmphasisCustom"} ([EAP]{.Abbreviation custom-style="Abbreviation"}), for instance, misread the Ottoman Turkish title
[يكي تصوير افكر]{.Arabic custom-style="ArabicScript"}
 as 
[تصوير افكر]{.Arabic custom-style="ArabicScript"}
, assumed it was Arabic (because Ottoman was written in Arabic script until 1924) and "correctly" transcribed it as [Taṣwīr Afkār]{.Transcription custom-style="Transcription"} while the correct transcription of the Ottoman would have been [Yeni]{.Transcription custom-style="Transcription"} [Taṣvīr-i Efkār]{.Transcription custom-style="Transcription"} [@EAP119/1/18_website]. 
Finally, such transcription schemes require diacritics not necessarily available on technical systems and not commonly recognized by the OCR-algorithms used for retro digitization of card catalogues.

Discovery systems across the board are unsuited for this plurality of scripts and the large variety of transcriptions. All come with idiosyncrasies of their own, such as internally removing or normalizing some or all diacritics from search queries. Worse, these choices are rarely documented and communicated to their users. Through ignorance or lack of interest in providing potentially costly services to communities outside the Global North and their cultural  record, users are commonly left to their own tools and have to try each and every version of a string they can think of (see [@fig:zdb-ar; @fig:zdb-dmg; @fig:zdb-dmg-defective]).

::: columns
:::: column

![Searching the union catalogue for periodicals in German-speaking countries for the journal [al-Janna]{.Transcription custom-style="Transcription"} in Arabic script](/Users/Shared/BachUni/publications/github/pae326271/assets/imageszdb_janna-ar.png){#fig:zdb-ar}

::::
:::: column

![Searching the union catalogue for periodicals in German-speaking countries for the journal [al-Janna]{.Transcription custom-style="Transcription"} in [DMG]{.Abbreviation custom-style="Abbreviation"} transcription ([al-Ǧanna]{.Transcription custom-style="Transcription"})](/Users/Shared/BachUni/publications/github/pae326271/assets/imageszdb_janna-ar-Latn.png){#fig:zdb-dmg}

::::
:::: column

![Searching the union catalogue for periodicals in German-speaking countries for the journal [al-Janna]{.Transcription custom-style="Transcription"} in in [DMG]{.Abbreviation custom-style="Abbreviation"} transcription without diacritics or definite article ([Ganna]{.Transcription custom-style="Transcription"})](/Users/Shared/BachUni/publications/github/pae326271/assets/imageszdb_janna-ar-Latn-no-al.png){#fig:zdb-dmg-defective}

::::
:::

## Creating a crowd-sourced union list

The project ["Jarāʾid: A Chronology of Arabic Periodicals (1800-1929)"][jaraid] has seen many iterations since its inception by Adam Mestyan in the early 2010s [@Mestyan.etal+2020+JaraidAchronology; @Mestyan.Grallert+2012+ProjectJaraid; @Mestyan.Grallert+2020+JaraIdChronology]. At its core, Jarāʾid is a volunteer effort of scholars working with periodicals  to openly share their collective knowledge about the publication history of Arabic periodical titles and their surviving copies, including digitised artefacts. I have been involved in the project as one of its main contributors and  lead on data modelling and some iterations of the website since 2012. Starting from a modest table of a few hundred titles in a Word document, Jarāʾid has grown into a catalogue of more than 3200 Arabic periodicals from all around the globe, recording [*inter alia*]{.EmphasisCustom custom-style="EmphasisCustom"} known titles, editors, publishers, place of publication, dates of first issue, additional publication languages in case of multilingual publications. Rooted in the  scholarly practices described above, information was originally gathered in Latinized transcriptions as found in sources and library catalogues and then normalized into the [IJMES]{.Abbreviation custom-style="Abbreviation"} system. In recent years, we have computationally re-transcribed these Latin transcriptions into Arabic script based on heuristic approach of rules and look-up tables. Jarāʾid therefore represents not just the only comprehensive union list of this material but the only one that can be searched and browsed in the original script. 
Finally, I have integrated holding information from [HathiTrust][hathi], the [Zeitschriften Datenbank ([ZDB]{.Abbreviation custom-style="Abbreviation"})][zdb], a database of periodical holdings in German-speaking countries, and the library of the American University of Beirut based on public [API]{.Abbreviation custom-style="Abbreviation"}s (former two) and personal collaborations (the latter) [@Grallert2022IntegratingLibraryData].

Jarāʾid is a very modest effort but it has become indispensable to the field despite our failure to attract any funding beyond an initial 500 Euros. Even though the project predates the approach of [[*minimal computing*]{.EmphasisCustom custom-style="EmphasisCustom"}][minimal] as introduced by [@Gil+2016; see also @RisamGil2022Introduction] it resonates with the questions and approaches outlined therein: focus on the things we can do and build the infrastructures we need "without the help we can't get" [@Gil+2016, 29]. Our technical decisions, from data formats to software stacks, result from balancing our scholarly need as a community with the limited knowledge, tools, and infrastructures at our disposal. [TEI/XML]{.Abbreviation custom-style="Abbreviation"} is certainly not what one would expect for bibliographic metadata but [XML]{.Abbreviation custom-style="Abbreviation"} and related technologies was the only data serialization format we had experiences with. In addition, the pilot for what later became [[FIHRIST]{.Abbreviation custom-style="Abbreviation"}][fihrist] had just adapted [TEI/XML]{.Abbreviation custom-style="Abbreviation"} to be a viable format for catalogues of Arabic manuscripts [C.f. @Soualah+2012; @OrtoljaBairdEtAl2019DigitalHumanitiesMemory, 3]. [TEI/XML]{.Abbreviation custom-style="Abbreviation"} also allowed us to treat bibliographic data as historical source and annotate it with information on the origin of information, certainty of stated facts, dates, and links to external authority files in a semantically rich catalogue without a relational database. The resulting data---mainly [TEI/XML]{.Abbreviation custom-style="Abbreviation"} files and their derivates---are hosted on [GitHub][github]. Releases are archived in the publicly-funded research data repository [Zenodo][zenodo]. Jarāʾid thus satisfies our goals of [*accessibility*]{.EmphasisCustom custom-style="EmphasisCustom"}, [*sustainability*]{.EmphasisCustom custom-style="EmphasisCustom"}, and [*credibility*]{.EmphasisCustom custom-style="EmphasisCustom"}.


![Geographic distribution of Arabic periodical titles published across South West Asia and North Africa (SWANA) between 1789--1929. The size of the pie charts corresponds to the total number of titles published at a location. Slices show the percentage of known holdings and digitized collections](/Users/Shared/BachUni/publications/github/pae326271/assets/imagesmap-data-set-periodicals_1789-1929-scatterpie-mena-label_en.png){#fig:map-periodicals-status}

![Map linking places of publication with known collections](/Users/Shared/BachUni/publications/github/pae326271/assets/imagesmap-data-set-periodical-holdings-global-north-na_mapped.png){#fig:map-periodicals-holdings}

## Access to artefacts

[@fig:map-periodicals-status] shows the distribution of all Arabic periodical titles published across South West Asia and North Africa ([SWANA]{.Abbreviation custom-style="Abbreviation"}) between 1789 and 1929 based on the [Jarāʾid][jaraid] dataset. It also provides information on the ratio of titles with known holdings and digital remediations. [@fig:map-periodicals-holdings] shows the 775 or 21,83% of all 3550 titles in the dataset that could be located in collections. Almost one third of them, 233 or 6.56% of all titles, have digital remediations. While the digitization quote of  titles in collections is surprisingly high, it must be kept in mind that we cannot resolve information on the extent of digitization. Even if only a single issue  was digitized, the periodical title will be included in this count. The Jarāʾid dataset also provides an astonishing insight in the uncoordinated nature of scanning efforts. 66 periodicals or 28,33% have been digitized by multiple institutions and 21 of this subset by three and more. Considering the limited resources and relatively high cost of digitization, it would surely make sense if future efforts where directed towards those titles not yet digitized at all.



The very limited extent of digitization is at least partially explained by the knowledge gap and interrelated survival and collection biases. Here, we are interested in the meaning of [*digitized*]{.EmphasisCustom custom-style="EmphasisCustom"}. The vast majority of those 233 periodicals is solely available as digital facsimiles due to the challenges Arabic script poses to traditional, segmentation-based approaches to computational text recognition. Accuracy rates for leading Arabic [OCR]{.Abbreviation custom-style="Abbreviation"} solutions are well below 75% on the character level [@Alghamdi.Teahan+2017+ExperimentalEvaluationArabic; @Alkhateeb.etal+2017+ArabicOpticalCharacter; cf. @Märgner+2012a; @Habash+2010+IntroductionToArabic], which causes the Internet Archive to state that the "language [is] not currently OCRable" [item description for @KurdAli+1923+GharaibAlGharba]. Commercial vendors frequently make opaque claims of highly accurate text recognition technologies but none share their code or data for evaluation. Their search-centric interfaces return high numbers of false positives. With the extent of false negatives---strings not found even though they are present in the original---impossible to determine, such data layers are nigh impossible to use beyond anecdotal evidence [@Grallert2022DHQ, §13; @Grallert2021GG, 64-65]. 

[OCR]{.Abbreviation custom-style="Abbreviation"} technologies for non-Latin scripts and ligatures such as Arabic have seen vast improvements with the widespread application of machine-learning approaches---from [Kraken][kraken], to [Transkribus][transkribus] and [Tesseract][tesseract]---which generally have shown to reliably produce high levels of accuracy independent of input language and script [@Kiessling+2017].[^cf2] They still suffer, however, from insufficient recognition of layouts and reading orders and the lack of models trained for this specific genre of texts. [^cf3] Most of the material currently available online has been digitized over the course of the last twenty years and would require renewed effort and substantial funding to apply the latest [OCR]{.Abbreviation custom-style="Abbreviation"} technologies.[^cf4] 

[*Digitized*]{.EmphasisCustom custom-style="EmphasisCustom"} should also not be conflated with [*openly accessible*]{.EmphasisCustom custom-style="EmphasisCustom"} on the internet. As Tim Sherratt [-@Sherratt+2019] called on us to query for the meaning of access, one has to ask "access to what and for whom?". Many digitized Arabic periodicals are kept in data silos with no application programming interfaces ([API]{.Abbreviation custom-style="Abbreviation"}s) or the option to manually download more than individual page images. They are protected from their readers by layers of paywalls, geofencing, and forced personal registration. [al-Muqtabas]{.Transcription custom-style="Transcription"}, for example, is commonly deemed in the public domain by vendors in the United States. Copies from the [University of Minnesota](https://catalog.hathitrust.org/Record/100658549) and [Princeton University](https://catalog.hathitrust.org/Record/008882293)  are openly available online through HathiTrust---for scholars at member institutions and the general public in the US as determined by a user's [IP]{.Abbreviation custom-style="Abbreviation"} address. Everyone else will see blank pages or needs access to [VPN]{.Abbreviation custom-style="Abbreviation"} services. Automated downloads frequently violate terms of use even if the vendor designates the material as being in the public domain. In one instance, such attempts  resulted in (temporary) blanket block of our home institution's entire [IP]{.Abbreviation custom-style="Abbreviation"} range.

In consequence, we witness a neo-colonial absence of the Global South from the digital cultural record [@Risam+2019; c.f. @Gooding+2018, 149-157; @Thylstrup+2018, 79-100]. The shocking differences are probably best illustrated by the comparison of the number of digitized Arabic periodicals with digitized newspapers from the German state of Hesse ([@tbl:digitisation]) [@HessischeRegionalzeitungen2019].

|             | Arabic periodicals (1798--1918) | [WWI as mirrored by Hessian regional papers](https://hwk1.hebis.de) |
|-------------|---------------------------------|---------------------------------------------------------------------|
| community   | c. 420 million Arabic speakers  | c. 6.2 million inhabitants                                          |
| periodicals | 2054 newspapers and journals    | 125 newspapers                                                      |
| digitized   | 156 periodicals                 | 125 newspapers with more than 1.5 million pages                     |
| type        | mostly facsimiles               | facsimiles and full text                                               |
| access      | paywalls, geo-fencing           | open access                                                         |
| interface   | mostly foreign languages only   | local and foreign languages                                         |

Table: Comparison of [*digitized*]{.EmphasisCustom custom-style="EmphasisCustom"} periodicals between the Global South and the Global North {#tbl:digitisation}

### Open Arabic Periodical Editions, 2015--

Open Arabic Periodical Editions ([OpenArabicPE]{.Abbreviation custom-style="Abbreviation"}, 2015--) is a project to design and implement workflows for sustainable,  scholarly digital editions with the affordances of the Global South. Based on the guiding principles of [*accessibility*]{.EmphasisCustom custom-style="EmphasisCustom"}, [*simplicity*]{.EmphasisCustom custom-style="EmphasisCustom"}, [*sustainability*]{.EmphasisCustom custom-style="EmphasisCustom"}, and [*credibility*]{.EmphasisCustom custom-style="EmphasisCustom"}, [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"} unites openly available digital facsimiles from institutional scanning efforts with human-transcribed text from shadow libraries and models them in [TEI/XML]{.Abbreviation custom-style="Abbreviation"} as an open, standard-compliant, and well-established format for digital editions.  

[[al-Maktaba al-shāmila]{.Transcription custom-style="Transcription"}][shamela] (The Comprehensive Library, 2005--, henceforth [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}) is the largest of a number of extremely popular shadow libraries for Arabic texts [@Verkinderen+2020+AlMaktabaAlShamilaShort]. It is widely used but rarely cited by scholars [@Grallert2022DHQ, §30; c.f. @Miller+2018, 104] and has been repeatedly employed for building scholarly corpora with a focus on distant reading approaches to classical texts [@Belinkov+2016; @Alrabiah+2013; @GundelfingerVerkinderen2020Governors; @OpenITIDocumentation]. [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"} was the first project to emphasise the transformation of material from [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} into verified scholarly editions and remains the only one with a modern focus.

[OpenArabicPE]{.Abbreviation custom-style="Abbreviation"} aims at providing a means to verify transcriptions against facsimiles and thus the necessary ground truth for training text recognition algorithms, a reliable corpus for distant reading, and reliably citable digital remediations. Despite our extremely limited resources---no project funds, no staff beyond volunteering interns, and no equipment beyond our own computers---we have published a corpus of six periodical editions with a total of 41 volumes, 645 issues and more than six million words ([@tbl:corpus]). All files, including bibliographic metadata on the article level in a number of standard formats, are published on [GitHub][openarabicpe_git], which also hosts a static webview for human readers based on the [[TEI]{.Abbreviation custom-style="Abbreviation"} Boilerplate][tei_boilerplate]. Releases are archived in the [Zenodo][zenodo] research data repository.[^cf5] Our plan to provide stable access through Canonical Texts Services ([CTS]{.Abbreviation custom-style="Abbreviation"}) and integration into [CLARIN]{.Abbreviation custom-style="Abbreviation"}'s [*Virtual Language Observatory*]{.EmphasisCustom custom-style="EmphasisCustom"} was abandoned after an initial upload of all issues of [al-Muqtabas]{.Transcription custom-style="Transcription"} because of unsustainable maintenance costs and our editions' evolving character.[^cf6]

| Periodical                      | Place             | Publisher                    | Dates[^tb1]   | DOI                                                                | Volumes | Issues | Words     |
| ------------------------------- | ----------------- | -----------                  | ------------- | ------------------------------------------------------------------ | ----:   | ----:  | ------:   |
| [al-Ḥaqāʾiq][haqaiq_git]        | Damascus          | [ʿAbd al-Qādir al-Iskandarānī]{.persName custom-style="persName"} | 1910--13      | [10.5281/zenodo.1232016](https://doi.org/10.5281/zenodo.1232016)   | 3       | 35     | 298090    |
| [al-Manār][manar_git]  [^tb2]          | Cairo             | [Muḥammad Rashīd Riḍā]{.persName custom-style="persName"}         | 1898--1918    |                                                                    | 20      | 387    | c.3000000 |
| [al-Muqtabas][muqtabas_git]     | Cairo, Damascus   | [Muḥammad Kurd ʿAlī]{.persName custom-style="persName"}           | 1906--18      | [10.5281/zenodo.597319](https://doi.org/10.5281/zenodo.597319)     | 9       | 96     | 1981081   |
| [al-Ustādh][ustadh_git]         | Cairo             | [ʿAbdallāh Nadīm al-Idrīsī]{.persName custom-style="persName"}    | 1892--93      | [10.5281/zenodo.3581028](https://doi.org/10.5281/zenodo.3581028)   | 1       | 42     | 221447    |
| [al-Zuhūr][zuhur_git]           | Cairo             | [Anṭūn al-Jumayyil]{.persName custom-style="persName"}            | 1910--13      | [10.5281/zenodo.3580606](https://doi.org/10.5281/zenodo.3580606)   | 4       | 39     | 292333    |
| [Lughat al-ʿArab][lughat_git]   | Baghdad           | [Anastās Mārī al-Karmalī]{.persName custom-style="persName"}      | 1911--14      | [10.5281/zenodo.3514384](https://doi.org/10.5281/zenodo.3514384)   | 3       | 34     | 373832    |
| [**total**]{.StrongCustom custom-style="StrongCustom"}                       |                   |                              |               |                                                                    | 41      | 645    | c.6166783 |

Table: [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"}'s corpus of periodical editions {#tbl:corpus}

[^tb1]: The current cut-off date is 1918.
[^tb2]: Since [Riḍā]{.persName custom-style="persName"}'s [Tafsīr]{.Transcription custom-style="Transcription"}, which accounts for about one fifth of [al-Manār]{.Transcription custom-style="Transcription"}'s content, was not included [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}'s transcription, it is also missing from the digital edition. See @Zemmin+2016 [232].

We designed and applied workflows to automatically transform [EPub]{.Abbreviation custom-style="Abbreviation"} (which is largely a zipped folder of [HTML]{.Abbreviation custom-style="Abbreviation"}) files from  [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} into [TEI/XML]{.Abbreviation custom-style="Abbreviation"}. 
Part of this step was to extract as much structural mark-up as possible from the [HTML]{.Abbreviation custom-style="Abbreviation"} source. We modelled each issue as a single [TEI/XML]{.Abbreviation custom-style="Abbreviation"} file in order to keep the original organisation of texts in this compound medium as they were published. Remediations of the material into other organisational structures for editing or reading purposes are left to future developments and user input. The individual periodical issue also happened to be the only reliable structural information provided by [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}. Individual files provided structural information in various forms, from structural (e.g. `<span class="title">`) to stylistic tags (`<span class="red">`) but only very little proved reliable enough for automatic conversion.
For the journal [al-Muqtabas]{.Transcription custom-style="Transcription"}, for example, [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} somewhat consistently recorded all first-level articles and sections but no news items and articles within sections and no sections within longer articles. Thus, structural information for items in the "News and ideas" section ([akhbār wa afkār]{.Transcription custom-style="Transcription"}), such as  [@oclc_4770057679-i_61-div_21.d1e2838], were not recorded [@fig:muqtabas-6-2-shamela]. The same is true for explicitly authorship information in bylines. We tried to catch both phenomena in multiple iterations of our conversion processes based on the length of paragraphs (`<p>`) and their position within the surrounding text string: Short paragraphs in predefined sections were assumed to signify the beginning of constituent articles. Short paragraphs at the end of articles were presumably bylines. 

This approach depends on reliable and consistent transcription of paragraphs and we learned that this had not been the case for all journals available from [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}. Consistency and reliability also differed between issues of the same journal, probably indicating different human transcribers and editors. 
Algorithmic searches for uncharacteristically short pages with close reading of these pages   substantiated the hypothesis of human transcribers because most omissions can be plausibly explained by common human errors:  skipping a few words on a long line, jumping a small number of lines, or turning two pages at once. This also indicates that [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} had no quality control such as double-keying. Finally, we incidentally found  unmarked comments interspersed in the transcription itself, stating, for example, that someone could not read the following four lines in the copy in front of them [@oclc_644997575-i_11-div_4.d1e704, 422]. 
From these notes, common orthographic normalisation, and the omission of all words in Latin script, we can safely deduce that the transcribers were Arabic speakers. We are still looking for ways to adequately acknowledge their work beyond a generic reference in the metadata section of our [TEI/XML]{.Abbreviation custom-style="Abbreviation"} files.

![[@oclc_4770057679-i_61-div_21.d1e2838] on [[*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}](http://shamela.ws/browse.php/book-26523#page-4046)](https://openarabicpe.github.io/slides/assets/shamela_muqtabas-annotated.png){#fig:muqtabas-6-2-shamela}

![Facsimile of [@oclc_4770057679-i_61-div_21.d1e2838] from [[EAP]{.Abbreviation custom-style="Abbreviation"}][eap]](http://images.eap.bl.uk/EAP119/EAP119_1_4_5/133.jp2/full/800,/0/gray.jpg){#fig:muqtabas-6-2-133-eap}

Adding and validating structural information required to identify the corresponding digital facsimile or material artefact, which means identifying the page the digital text was transcribed from. Arabic journals and magazines wereorganised into annual, numbered volumes and numbered issues corresponding to the their respective publication schedule (monthly, fortnightly, weekly etc.). Unlike newspapers, journals restarted their issue count with every volume. [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}'s transcriptions, on the other hand, abolished volumes as organising principle and count (available) issues in a consecutive sequence (see the sidebar in [@fig:muqtabas-6-2-shamela]).  
Locating the corresponding issue therefore required knowledge about every periodical's actual publication schedule. This could usually only be established by accessing physical copies or digital facsimiles because journals frequently diverted from their official publication schedule by publishing fewer issues per volume.[^cf7]

[*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} human-readable dating information at the beginning of each issue proved largely fictional both in regards to a journal's official publication schedule and individual issues' actual publication dates. 
Our process for generating the necessary bibliographic metadata for linking digital texts to facsimiles was a hybrid one: automatic iteration based on known publication dates and validation against the original.

Digital facsimiles are available from a growing number of vendors. [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"} was largely inspired by the British Library's [*Endangered Archives Programme*]{.EmphasisCustom custom-style="EmphasisCustom"} ([[EAP]{.Abbreviation custom-style="Abbreviation"}][eap]) publishing the scans of Arabic periodical collections in the al-Aqṣā Mosque's library in Jerusalem ([[EAP119]{.Abbreviation custom-style="Abbreviation"}][eap119]) in the early 2010s [^cf8] but has since added links to facsimiles from [HathiTrust][hathi], [Translatio][translatio], and [[Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya]{.Transcription custom-style="Transcription"}][alsharekh], the largest Arabic platform for facsimiles of historical periodicals. With regard to the latter, one must note that proclaimed facsimiles cannot be taken as such [*prima facie*]{.EmphasisCustom custom-style="EmphasisCustom"}. As it turned out, they had rendered the text of an entire volume of [al-Muqtabas]{.Transcription custom-style="Transcription"} from [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} in a original-looking layout and served them as "fakesimiles" [@Grallert2022DHQ, §14]. This further emphasises the need for and value of vetted text and image layers in digital [*scholarly*]{.EmphasisCustom custom-style="EmphasisCustom"} editions, such as the ones produced by [OpenArabicPE]{.Abbreviation custom-style="Abbreviation"}. 




Ultimately, locating page breaks in the text stream in order to link them to digital facsimiles proved to be the most labour-intensive task. Recording the original position of page breaks had apparently not been a priority for [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"}'s anonymous transcribers. While some periodicals faithfully followed the original, others did not and introduced their own page breaks. [@fig:muqtabas-6-2-shamela] and [@fig:muqtabas-6-2-133-eap] demonstrate this mismatch. While [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} recorded the page number as 45 ([@fig:muqtabas-6-2-shamela]), digital facsimiles from EAP show the article was published on page 133 ([@fig:muqtabas-6-2-133-eap]). Consequently, every one of the c.8000 page breaks in the journals [[al-Muqtabas]{.Transcription custom-style="Transcription"}][muqtabas_git] and [[al-Ḥaqāʾiq]{.Transcription custom-style="Transcription"}][haqaiq_git] needed to be manually marked up by volunteers.[^cf9] My gratitude goes to Dimitar Dragnev, Talha Güzel, Dilan Hatun, Hans Magne Jaatun, Xaver Kretzschmar, Daniel Lloyd, Klara Mayer, Tobias Sick, Manzi Tanna-Händel and Layla Youssef, who contributed their time to this task.

On the technical level, linking is trivial, particularly since the increasing adoption of [IIIF]{.Abbreviation custom-style="Abbreviation"} infrastructures in [GLAM]{.Abbreviation custom-style="Abbreviation"} institutions. Links to externally hosted facsimiles, on the other hand, are the most volatile component of our data layer and we already encountered three major instances of link rot. Two were caused by vendors moving servers and changing protocols: The British Library moved  [EAP]{.Abbreviation custom-style="Abbreviation"} to [IIIF]{.Abbreviation custom-style="Abbreviation"} in 2017 and [Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya]{.Transcription custom-style="Transcription"} moved to a new domain in 2019.  HathiTrust, on the other hand, removed the facsimiles of Princeton's copy of [[al-Haqāʾiq]{.Transcription custom-style="Transcription"} 1 (1910)](http://hdl.handle.net/2027/njp.32101036074001) from the public domain without any explanation in 2016. HathiTrust reinstated public access six years later after multiple inquiries. Such link rot inevitably requires a lot of manual labour to figure out the patterns in new [URL]{.Abbreviation custom-style="Abbreviation"}s (if any) and to write the necessary scripts to update all [TEI]{.Abbreviation custom-style="Abbreviation"} files.  



## Conclusion

[aanp]: https://lebanesestudies.ncsu.edu/YourStory/newspapers.php 
[almeshkat]: http://almeshkat.net/ 
[alsharekh]: http://archive.alsharekh.org/
[alwaraq]: http://www.alwaraq.net/
[bibalex]: http://ima.bibalex.org/IMA/presentation/home/list.jsf
[cc-by-sa-4]: http://creativecommons.org/licenses/by-sa/4.0/
[ceteicean]: https://github.com/TEIC/CETEIcean
[dhib]: https://dhibeirut.wordpress.com/
[dhsi]: https://dhsi.org/
[doi]: https://doi.org
[eap]: https://eap.bl.uk/
[eap119]: https://eap.bl.uk/project/EAP119
[eapb]: https://www.gale.com/intl/c/early-arabic-printed-books-literature-grammar-language-catalogues-and-periodicals 
[fihrist]: https://www.fihrist.org.uk/
[github]: https://www.github.com
[gh-pages]: https://pages.github.com/
[gpa]: https://www.eastview.com/resources/gpa/
[hathi]: http://catalog.hathitrust.org/
[histme]: https://github.com/Hist-ME
[internetarchive]: https://archive.org/
[jaraid]: https://projectjaraid.github.io/ 
[menadoc]: http://menadoc.bibliothek.uni-halle.de/
[minimal]: http://go-dh.github.io/mincomp/
[mit-license]: https://opensource.org/licenses/MIT
[manar_git]: https://www.github.com/openarabicpe/journal_al-manar
[muqtabas_cts]: http://cts.informatik.uni-leipzig.de/muqtabas/cts/
[muqtabas_git]: https://github.com/OpenArabicPE/journal_al-muqtabas
[haqaiq_git]: https://github.com/OpenArabicPE/journal_al-haqaiq
[lughat_git]: https://github.com/OpenArabicPE/journal_lughat-al-arab
[ustadh_git]: https://github.com/OpenArabicPE/journal_al-ustadh
[zuhur_git]: https://www.github.com/openarabicpe/journal_al-zuhur
[kraken]: http://kraken.re/
[openarabicpe_git]: https://github.com/OpenArabicPE/
[openarabicpe_schema]: https://github.com/OpenArabicPE/OpenArabicPE_ODD
[openarabicpe_blog]: https://openarabicpe.github.io
[openarabicpe_zotero]: https://www.zotero.org/groups/OpenArabicPE
[orcid]: https://orcid.org/
[rawgit-old]: https://github.com/rgrove/rawgit
[saaid]: http://saaid.net/
[sakhrit]: http://archive.sakhrit.co
[shamela]: http://www.shamela.ws/
[tei]: https://www.tei-c.org
[tei_boilerplate]: http://dcl.slis.indiana.edu/teibp/
[tei_publisher]: https://teipublisher.com/ 
[tesseract]: https://github.com/tesseract-ocr/tesseract
[transkribus]: https://readcoop.eu/transkribus/
[translatio]: https://www.translatio.uni-bonn.de/online-zeitschriften/arabische-online-zeitschriften 
[wikisource]: https://wikisource.org/ 
[zdb]: https://zdb-katalog.de/
[zenodo]: https://www.zenodo.org
[zotero]: https://www.zotero.org

# Contributor bio

[^cf1]: For a detailed overview of the state of Arab Periodical Studies see [@Grallert2021GG].

[^fn1]: Available online at <https://openarabicpe.github.io> and <https://github.com/openarabicpe>. See also @Grallert2022DHQ.

[^fn2]: For an introduction to the particularities of Arabic script see @Nemeth+2017 [14-22]; @GruendlerArabicScript; @Milo2011ArabicTypography.

[^fn3]: On the background of Unicode and its application to Arabic see @Nemeth+2017 [400-406]; @MiloCommentsArabicBlock. Nemeth provides the most concise overview of the work of Thomas Milo, the most profound critic of digital approaches to Arabic script and the founder of DecoType [-@Nemeth+2017,410-434].

[^cf2]: Some projects working on languages that have seen script reforms in the twentieth century, such as Turkish, directly transcribe Arabic into Latin script with [HTR]{.Abbreviation custom-style="Abbreviation"} [@KirmizialtinWrisley2022AutomatedTranscription].

[^cf3]: The "Open Islamicate Texts Initiative Arabic-script OCR Catalyst Project" ([OpenITI ACOP]{.Abbreviation custom-style="Abbreviation"}) will train models for the most frequent fonts and types [@InitiativeOpenITI+2019+TheOpenIslamicate] and their technology will eventually find its way into HathiTrust [@2020+HathiTrustResearchCenter].

[^cf4]: On the environmental cost of machine learning see  @Alkaoud.Syed+2020+OnTheImportance [124]; @Strubell.etal+2019+EnergyAndPolicy; @Baillot.etal+2021+DigitalHumanitiesAnd.

[^cf5]: For a detailed project description see @Grallert2022DHQ.

[^cf6]: [@Grallert+2017a]. The endpoint  at <http://cts.informatik.uni-leipzig.de/muqtabas/cts/> is still functional as of January 2023.

[^cf7]: E.g. [al-Muqtabas]{.Transcription custom-style="Transcription"} [4 (5/6)](https://openarabicpe.github.io/journal_al-muqtabas/tei/oclc_4770057679-i_41.TEIP5.xml) and [8 (11/12)](https://openarabicpe.github.io/journal_al-muqtabas/tei/oclc_4770057679-i_94.TEIP5.xml).

[^cf8]: Technical information on the project is scarce and contradictory despite two publications by the project leaders; [@Qasem+2015; @Matusiak+2009]

[^cf9]: In other instances, such as the journals [[Lughat al-ʿArab]{.Transcription custom-style="Transcription"}][lughat_git] and [[al-Ustādh]{.Transcription custom-style="Transcription"}][ustadh_git], [*Shamela*]{.EmphasisCustom custom-style="EmphasisCustom"} did provide page breaks that correspond to a printed edition.