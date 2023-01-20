---
title: "Editing mundane texts across the digital divide"
subtitle: "the case of Arabic periodicals from the late nineteenth-century Eastern Mediterranean"
project: "Digital Humanities in Practice"
author: Till Grallert
date: 2023-02-01
ORCID: orcid.org/0000-0002-5739-8094
DOI: doi.org/10.5281/zenodo.999976
licence: http://creativecommons.org/licenses/by-nd/4.0/
bibliography: 
	- /Users/Shared/BachUni/publications/github/p0fb41f86/assets/bibliography/bootstrapped-scholarly-editions.csl.json
    - assets/bibliography/2023_dh-in-practice.csl.json
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

# abstract

The essay introduces the project [[*Open Arabic Periodical Editions*]{custom-style="EmphasisCustom"} (OpenArabicPE)](https://openarabicpe.github.io) as a case study of minimal computing to address the specific challenges and affordances of digital humanities in the Eastern Mediterranean. I will outline the socio-technical challenges for digital approaches to the cultural heritage of societies outside the Global North. I pose that a digital episteme and infrastructures deeply rooted in 20th-century, english-speaking, American neoliberal capitalism cause a neo-orientalist silencing of the material heritage of predominantly Arabic-speaking Islamicate societies. This places the onus of digitising the textual heritage on individual scholars and citizens and requires mitigation strategies on every level of the digital workflow. The enormity of the problem is illustrated by the following example: Less than 1/20, or 145, of all c.3300 Arabic periodical titles published globally before 1930 are  digitised. Almost all of them solely as facsimiles and most incomplete. 145 periodicals hidden through geo-fencing, behind paywalls, in proprietary data silos, and served through non-Arabic interfaces for a community of more than 400 million Arabic speakers. 

Influenced by [[*minimal computing*]{custom-style="EmphasisCustom"}](http://go-dh.github.io/mincomp/) and [[*pirate care*]{custom-style="EmphasisCustom"}](https://pirate.care) and based on the guiding principles of *accessibility*, *simplicity*, *sustainability* and *credibility*, OpenArabicPE originated in 2015 from an attempt to address the core problem of corpus building: the lack of functional Arabic OCR without which one would have to resort to human transcribers. Yet, we could produce reliable ground truth for improving and---with the advent of machine-learning based approaches---training OCR algorithms by combining existing transcriptions from shadow libraries, such as [*al-Maktaba al-Shāmila*](http://shamela.ws/), with openly available digital facsimiles for the purpose of validating the former.

The essay will critically reflect on OpenArabicPE and introduce the workflows to produce standard-compliant, machine-actionable, scholarly digital editions of Arabic periodicals by creatively repurposing open and free-to-use tools and platforms, which allow us to currently host full-text TEI XML editions of some 630 issues from six journals and more than 7 million words without any funding and resources beyond our own labour time and laptop computers.


"Open Arabic Periodical Editions (OpenArabicPE)"[^fn1]  was born in 2015 out of need and with a simple idea: Repurpose available data, tools and infrastructures in order to provide public and free access to reliable digital scholarly editions of early Arabic periodicals with the affordances in order to address the need for access to and information about such periodicals resulting from the multi-layered digital divides embodied in networked socio-technical infrastructures, computational tools, and digital artefacts themselves.

I had just finished my PhD on the history of the street in late Ottoman Damascus and moved to Beirut for a new post-doctoral research project on the genealogy of food riots across the predominantly Arabic-speaking Eastern Mediterranean. 
The main source for both projects were periodicals---tens of thousands of newspaper and magazine articles published across the region. But despite their quotidian nature, their pivotal role for central cultural phenomena of the time as the regions first mass medium, and ubiquitous references in scholarly literature, surprisingly little of substance is known about this medium in terms of individual publication histories, distribution channels, and audiences or the number and whereabouts of surviving copies. This is particularly true for locations beyond the centers of the press in Beirut and Cairo.[^cf1]

In spring 2015, I was part of the first Digital Humanities Institute -- Beirut, organised by David Wrisley and Randa el Khatib, where I taught a course on TEI XML with a focus on local, Arabic-speaking material. I also met Alex Gil, who introduced me to the idea of [*minimal computing*]{custom-style="EmphasisCustom"}

## Knowledge about artefacts

The first need, therefore, was (and still is) a need for improving our knowledge about periodicals as the embodiment of socio-economic relations, intellectual traditions, and political frameworks, their manifestation in a limited number of material artefacts, the transmission of individual artefacts into private and public collections, and finally their occasional digital remediation. I would need to know which paper was published and potentially covered the series of food riots across cities of the Syrian hinterland, such as Hama and Homs in summer 1910 [C.f. @Grallert+2019]. I would then need to know if copies survived the turmoil that since wreaked havoc upon the region and its cultural heritage over the last century, where to find surviving copies, and how to access them. 

As the number of potential data points in this set numbers into the thousands and as library catalogues had moved into the networked digital realm ages ago, or so I thought, all metadata should be machine actionable, conform to established standards in the field, and link to some sort of externally controlled authority files for disambiguating and enriching information. 

At this point we have to acknowledge the multi-layered digital divide, a chicken-egg problem that is difficult to tease appart.


Despite cotidian impressions to the contrary, many library catalogues have not been digitised or published online. This is particularly true for institutions outside the Global North and collections of material from the Global South. The website of the Lebanese National Library, for instance, still advertises its catalogue as forthcoming. Manually compiled union catalogues are a Herculean task and have largely fallen out of fashion with the advent of COPACs. Given their publication dates and the neccessary time for information collection, they should probably be read as historical sources rather than finding aids [E.g. @ElHadi+1965; @Hopwood+1970; @Aman+1979; @DeJong+1979; @Iḥdādan+1984; @Khūrī+1985; @Höpp+1994; @Atabaki+1995]. Likewise, library catalogues are layered historical documents that accumulate traces of their socio-technic affordances with each remediation. Looking at one of the many entries for [ʿAbdallāh Nadīm al-Idrīsī]{custom-style="persName"}'s weekly journal [al-Ustādh]{custom-style="Transcription"}, published in Cairo from 1892 to 1893, in Wordcat, we most likely will not encounter a record newly created from the material artefact by an expert cataloguer with domain knowledge in Arabic periodicals and the ability to read Arabic script. Even with the necessary domain knowledge she will most likely have had to contend with technological systems ill-suited, if not unable, to deal with the metadata in its original script, calendars or naming conventions.

Arabic is both one of the main human languages with more than 420 million speakers and a writing system for many historic and contemporary Asian and African languages, such as Persian, Urdu, Pashtu, Ottoman, Uzbek or Uighur [@Mumin.Versteegh+2014+TheArabicScript]. The script is written from right to left, letters have up to four shapes depending on their position within a string, and most letters connect in the writing direction within a word. Multiple letter share the same basic shape ([rasm]{custom-style="Transcription"}) and diacritical dots ([iʿjām]{custom-style="Transcription"}) below and above the [rasm]{custom-style="Transcription"} allow to decrease semantic ambiguity. Depending on writing style and typefonts, letters will form ligatures. They will not necessarily sit on a single base line and base lines can be tilted ([@fig:arabic]). There are only few exceptions to the script-specific writing rules across languages.[^fn2] Importantly for us, the diacritics are not strictly necessary for readers as is evidenced by recent efforts at circumventing surveillance and censorship of authoritarian Arab regimes by using (an approximation of) the [rasm]{custom-style="Transcription"} on social media. Furthermore, their use is subject to changing cultural preferences. Some regional practices all but omit them from specific letters, particularly at the end of a word.

![Example of basic Arabic typesetting from [@oclc_4770057679-i_13-div_8.d1e1249]: "America and the Arab scholars". The red arrow indicates the reading direction. Words are underlined in [*red*]{custom-style="EmphasisCustom"}. Ligatures of multiple letters are underlined in [*green*]{custom-style="EmphasisCustom"}.](/Users/Shared/BachUni/publications/github/p0fb41f86/assets/figures/arabic-script_annotated.png){#fig:arabic}

Type-written card-catalogues, hot-metal printing presses, electronic computers (understood as an interdependent combination of hardware and software) form a global hegemonic technology stack bound up in historically contingent cultural traditions of the Global North. Mechanically and, later, electronically recording information in scripts other than Latin was never considered sufficiently important or profitable to be supported out-of-the-box.
Computational systems  not only derive from their type-setting ancestors and enforce Latin script grammar upon other writing systems, they also inherited the concept of national languages and do not consequently distinguish between scripts and languages [@Fiormonte.etal+2015+ThePoliticsof]. The character-encoding standard Unicode enabled vendor-independent exchange and interoperability of texts in Arabic script but it continues to adhere to the script grammar of Latin. Unicodes organising principle of code points is a confusing combination of scripts and languages that results in multiple code points for the same glyph.
Anybody entering Arabic texts into a computer has to select one specific interpretation, one and only one Unicode representation of a textual string they want to encode. They have to either normalise historical or geographic orthographic variance or pick visually-matching but technically "wrong" glyphs.  The resulting large variety of encodings for the same string of Arabic letters depends largely on the language of operating systems and keyboard settings on the input device.
Egyptian cultural preferences, for instance, would virtually always omit the two dots underneath a final [yāʾ]{custom-style="Transcription"} (U+064A: ي). To mirror such cultural preferences, one can either select the Arabic [alif maqṣūra]{custom-style="Transcription"} (U+0649: ى) or the Persian [ye]{custom-style="Transcription"} (U+06CC: ی).[^fn3] Unfortunately, search algorithms built into modern operating systems are not aware of these variances and any application software relying on them will return skewed results without additional efforts at regularisation or a reduction to the [rasm]{custom-style="Transcription"} [@Milo.Martinez+2019+ANewStrategy].

The necessary human-machine interfaces for interacting with digital information present another layer of inaccessibility for those wanting to engage with Arabic text as encoding and rendering information are two different steps. 

- HTML `@lang` tag as example
- XML editors
	- I added support for the `@lang` tag in the TEI scripts for oXygen

Beyond the fundamental impossibility to adequately record written Arabic in digital form, cultural heritage and practices of societies from the Global South require constant efforts of translation and transcription, themselves intrinsically entangled with the socio-technical traditions of the Global North. The aforementioned journal is a simple, yet powerful example. [al-Ustādh]{custom-style="Transcription"} is, of course, a transliteration of the Arabic title
 الاستاذ
into Latin script, as is the rendering of the publisher's name 
عبد الله النديم الإدريسي
 as [ʿAbdallah al-Nadīm al-Idrīsī]{custom-style="persName"}. These transcriptions follow the widely adopted system of the International Journal of Middle East Studies. Catalogers in German-speaking countries would follow a system with 1:1 character transliterations devised by the Deutsche Morgenländische Gesellschaft and record the title as [al-Ustāḏ]{custom-style="Transcription"}. Many such  systems require diacritics not necessarily available on technical systems and not commonly recognised by the OCR-algorithms used for retro digitisation of card catalogues.

Discovery systems across the board are unsuited for this plurality of scripts and the large variety of transcriptions. All come with idiosyncrasies of their own, such as internally removing some or all diacritics from search queries but keeping the determined Arabic article 
ال
 as part of the word. Worse, these choices are rarely documented and communicated to their users. Be it ignorance or lack of interest in providing potentially expensive services to communities outside the Global North and their cultural heritage, users are commonly left to their own tools and have to try each and every version of a string they can thin of.

[@fig:jaraid-status] shows the distribution of all Arabic periodical titles published across the Middle East and North Africa between 1789 and 1929 based on [Project Jarāʾid](https://projectjaraid.githu.io/), a scholarly crowd-sourcing effort we are running since 2012 to gather publication and holdings data. Based on this data set, only 504 or 15,59% of the 3232 titles could be located in collections and only 148 or 4,58% have been at least partially digitised [@Mestyan.etal+2020+JaraidAchronology; @Mestyan.Grallert+2012+ProjectJaraid; @Mestyan.Grallert+2020+JaraIdChronology].

![Geographic distribution of Arabic periodical titles published across the Middle East and North Africa between 1789--1929. The size of the pie charts corresponds to the total number of titles published at a location. Slices show the percentage of known holdings and digitised collections.](/Users/Shared/BachUni/publications/github/p0fb41f86/assets/figures/map-jaraid_sf_mena_en-status_scatterpie.png){#fig:jaraid-status}

The very limited extent of digitisation is at least partially explained by the knowledge gap and interrelated survival and collection biases. Here, we are interested in the meaning of [*digitised*]{custom-style="EmphasisCustom"}. The vast majority of those 148 periodicals is solely available as digital facsimiles due to the challenges Arabic script, as outlined above, poses to traditional, segmentation-based approaches to computational text recognition. Accuracy rates for leading Arabic [OCR]{custom-style="Abbreviation"} solutions are well below 75% on the character level [@Alghamdi.Teahan+2017+ExperimentalEvaluationArabic; @Alkhateeb.etal+2017+ArabicOpticalCharacter; cf. @Märgner+2012a; @Habash+2010+IntroductionToArabic], which causes the Internet Archive to state that the "language [is] not currently OCRable" [item description for @KurdAli+1923+GharaibAlGharba]. [OCR]{custom-style="Abbreviation"} technologies for non-Latin scripts and ligatures such as Arabic have seen vast improvements with the widespread application of machine-learning approaches---from [Kraken](http://kraken.re/), to [Transkribus](https://readcoop.eu/transkribus/) and [Tesseract](https://github.com/tesseract-ocr/tesseract)---which generally have shown to reliably produce high levels of accuracy independent of input language and script [@Kiessling+2017]. They still suffer, however, from insufficient recognition of layouts and reading orders and the lack of models trained for this specific genre of texts. [^cf2]  Most of the material currently available online has been digitised over the course of the last twenty years and would require renewed effort and substantial funding to apply the latest [OCR]{custom-style="Abbreviation"} technologies.[^cf3] 

[*Digitised*]{custom-style="EmphasisCustom"} should also not be conflated with [*openly accessible*]{custom-style="EmphasisCustom"} on the internet. Many are kept in data silos with no application programming interfaces ([API]{custom-style="Abbreviation"}s) or the option to manually download more than individual page images. They are protected from their readers by layers of paywalls, geofencing, and forced personal registration. [al-Muqtabas]{custom-style="Transcription"}, for example, is commonly deemed in the public domain by vendors in the United States. Copies from the [University of Minnesota](https://catalog.hathitrust.org/Record/100658549) and [Princeton University](https://catalog.hathitrust.org/Record/008882293)  are openly available online through HathiTrust---for scholars at member institutions and the general public in the US as determined by a user's [IP]{custom-style="Abbreviation"} address. Everyone else will see blank pages or needs access to [VPN]{custom-style="Abbreviation"} services. Automated downloads frequently violate terms of use even if the vendor designates the material as being in the public domain. In one instance, such attempts by an academic resulted in (temporary) blanket block of an her home institution's entire [IP]{custom-style="Abbreviation"} range.

In consequence, we witness a neo-colonial absence of the Global South from the digital cultural record [@Risam+2019; c.f. @Gooding+2018, 149-157; @Thylstrup+2018, 79-100]. The shocking differences are probably best illustrated by the comparison between the number of digitised Arabic periodicals and digitised newspapers from the German state of Hesse ([@tbl:digitisation]) [@HessischeRegionalzeitungen2019].

|             | Arabic periodicals (1798--1929) | [WWI as mirrored by Hessian regional papers](https://hwk1.hebis.de) |
|-------------|---------------------------------|---------------------------------------------------------------------|
| community   | c. 420 million Arabic speakers  | c. 6.2 million inhabitants                                          |
| periodicals | 3269 newspapers and journals    | 125 newspapers                                                      |
| digitised   | 145 periodicals                 | 125 newspapers with more than 1.5 million pages                     |
| type        | mostly facsimiles               | facsimiles, full text                                               |
| access      | paywalls, geo-fencing           | open access                                                         |
| interface   | mostly foreign languages only   | local and foreign languages                                         |

Table: Comparison of [*digitised*]{custom-style="EmphasisCustom"} periodicals between the Global South and the Global North {#tbl:digitisation}

## Access to artefacts




The idea behind OpenArabicPE is simple: combine available digital remediations, human-transcribed text from immensely popular shadow libraries and digital facsimiles of the material artefact from institutional scanning efforts, and package them into an open, standard-compliant, and well-established format for digital editions.




We designed and applied workflows to automatically transform EPub (which is largely a zipped folder of HTML) files from [[al-Maktaba al-shāmila]{custom-style="Transcription"}][shamela] into XML following the [Text Encoding Initiative ([TEI]{custom-style="Abbreviation"})][tei]'s guidelines [@teiconsortium2020TEIP5Guidelines]. Part of this step was to extract as much structural mark-up as possible from the HTML source. We modelled each issue as a single TEI XML file in order to keep the original organisation of texts in this compound medium as they were published. Remediations of the material into other organisational structures for editing or reading purposes are left to future developments and user input. The individual periodical issue also happened to be the only reliable structural information provided by [[al-Maktaba al-shāmila]{custom-style="Transcription"}][shamela]. Individual files provided structural information in various forms, from structural (e.g. `<span class="title">`) to stylistic tags (`<span class="red">`) but only very little proved reliable enough for automatic conversion.
For the journal [al-Muqtabas]{custom-style="Transcription"}, for example, [al-Maktaba al-shāmila]{custom-style="Transcription"} somewhat consistently recorded all first-level articles and sections but no news items and articles within sections and no sections within longer articles. Thus, structural information for items in the "News and ideas" section ([akhbār wa afkār]{custom-style="Transcription"}), such as  [@oclc_4770057679-i_61-div_21.d1e2838], were not recorded [@fig:muqtabas-6-2-shamela]. The same is true for explicitly authorship information in bylines. We tried to catch both phenomena in multiple iterations of our conversion processes based on the length of paragraphs (`<p>`) and their position within the surrounding text string: Short paragraphs in predefined sections were assumed to signify the beginning of constituent articles. Short paragraphs at the end of articles were presumably bylines. This approach depends on reliable and consistent transcription of paragraphs and we learned that this had not been the case for all journals available from [al-Maktaba al-shāmila]{custom-style="Transcription"}. Consistency and reliability also differed between issues of the same journal, probably indicating different human transcribers and editors.

![[@oclc_4770057679-i_61-div_21.d1e2838] on [[al-Maktaba al-shāmila]{custom-style="Transcription"}](http://shamela.ws/browse.php/book-26523#page-4046)](https://openarabicpe.github.io/slides/assets/shamela_muqtabas-annotated.png){#fig:muqtabas-6-2-shamela}

![Facsimile of [@oclc_4770057679-i_61-div_21.d1e2838] from [EAP]()](http://images.eap.bl.uk/EAP119/EAP119_1_4_5/133.jp2/full/800,/0/gray.jpg){#fig:muqtabas-6-2-133-eap}

Adding and validating structural information required to identify the corresponding digital facsimile or material artefact, which means identifying the page the digital text was transcribed from. Arabic journals and magazines were, as far as I have seen, organised into annual, numbered volumes and numbered issues corresponding to the their respective publication schedule (monthly, fortnightly, weekly etc.). Unlike newspapers, journals restarted their issue count with every volume. [al-Maktaba al-shāmila]{custom-style="Transcription"}, on the other hand, abolishes volumes as organising principle and counts (available) issues in a consecutive sequence (see the sidebar in [@fig:muqtabas-6-2-shamela]).  
Locating the corresponding issue therefore required knowledge about every periodical's actual publication schedule. This could usually only be established by accessing physical copies or digital facsimiles because journals frequently diverted from their official publication schedule by publishing fewer issues per volume.[^cf4] [al-Maktaba al-shāmila]{custom-style="Transcription"} provides human-readable dating information at the beginning of each issue but this proved largely fictional both in regards to a journal's official publication schedule and individual issues' actual publication dates. 
Our process for generating the necessary bibliographic metadata for linking digital texts to facsimiles was a hybrid one: automatic iteration based on known publication dates and validation against the original.

Ultimately, locating page breaks in the text stream in order to link them to digital facsimiles proved to be the most labour-intensive task. Recording the original position of page breaks had apparently not been a priority for the anonymous transcribers. While some periodicals faithfully followed the original, others did not and introduced their own page breaks. [@fig:muqtabas-6-2-shamela] and [@fig:muqtabas-6-2-133-eap] demonstrate this mismatch. While [al-Maktaba al-shāmila]{custom-style="Transcription"} recorded the page number as 45 ([@fig:muqtabas-6-2-shamela]), digital facsimiles from EAP show the article was published on page 133 ([@fig:muqtabas-6-2-133-eap]). Consequently, every one of the c.8000 page breaks in the journals [[al-Muqtabas]{custom-style="Transcription"}][muqtabas_git] and [[al-Ḥaqāʾiq]{custom-style="Transcription"}][haqaiq_git] needed to be manually marked up by volunteers.[^fn4] My gratitude goes to Dimitar Dragnev, Talha Güzel, Dilan Hatun, Hans Magne Jaatun, Xaver Kretzschmar, Daniel Lloyd, Klara Mayer, Tobias Sick, Manzi Tanna-Händel and Layla Youssef, who contributed their time to this task.

On the technical level, linking is trivial, particularly with the increasing adoption of [IIIF]{custom-style="Abbreviation"} infrastructures in [GLAM]{custom-style="Abbreviation"} institutions. Links to externally hosted facsimiles, on the other hand, are the most volatile component of our data layer and we already encountered three major instances of link rot. Two were caused by vendors moving servers and changing protocols: The British Library moved the Endangered Archives Programme to [IIIF]{custom-style="Abbreviation"} in 2017 and [Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya]{custom-style="Transcription"} moved to a new domain in 2019.  HathiTrust, on the other hand, removed the facsimiles of Princeton's copy of [[al-Haqāʾiq]{custom-style="Transcription"} 1 (1910)](http://hdl.handle.net/2027/njp.32101036074001) from the public domain without any explanation in 2016. After multiple inquiries, HathiTrust reinstated public access six years later. Such link rot inevitably requires a lot of manual labour to figure out the patterns in new [URL]{custom-style="Abbreviation"}s (if any) and to write the necessary scripts to update all [TEI]{custom-style="Abbreviation"} files.  



The corpus comprises six fully searchable editions: [Muḥammad Kurd ʿAlī]{custom-style="persName"}'s journal [al-Muqtabas]{custom-style="Transcription"} (Cairo and Damascus, 1906--18, not to be confused with his newspaper of the same name), [ʿAbd al-Qādir al-Iskandarānī]{custom-style="persName"}'s  [al-Ḥaqāʾiq]{custom-style="Transcription"} (Damascus, 1910--12), [Anastās Mārī al-Karmalī]{custom-style="persName"}'s [Lughat al-ʿArab]{custom-style="Transcription"} (Baghdad, 1911--14),  [Muḥammad Rashīd Riḍā]{custom-style="persName"}'s [al-Manār]{custom-style="Transcription"} (Cairo, 1898--1940), [Anṭūn al-Jumayyil]{custom-style="persName"}'s [al-Zuhūr]{custom-style="Transcription"} (Cairo, 1910--13), and [ʿAbdallāh Nadīm al-Idrīsī]{custom-style="persName"}'s weekly journal [al-Ustādh]{custom-style="Transcription"} (Cairo, 1892--1893).[^cf5]

| Periodical                      | Place             | Dates[^tb1]   | DOI                                                                | Volumes   | Issues   | Words    | Size (MB)[^tb3] |
| ------------------------------- | ----------------- | ------------- | ------------------------------------------------------------------ | --------- | -------- | -------: | ---------:      |
| [al-Ḥaqāʾiq][haqaiq_git]        | Damascus          | 1910--13      | [10.5281/zenodo.1232016](https://doi.org/10.5281/zenodo.1232016)   | 3         | 35       | 298090   | 15              |
| [al-Manār][manar_git]           | Cairo             | 1898--1918    |                                                                    | 20        | 387      | c.3000000       | NA              |
| [al-Muqtabas][muqtabas_git]     | Cairo, Damascus   | 1906--18      | [10.5281/zenodo.597319](https://doi.org/10.5281/zenodo.597319)     | 9         | 96       | 1981081  | 107.6           |
| [al-Ustādh][ustadh_git]         | Cairo             | 1892--93      | [10.5281/zenodo.3581028](https://doi.org/10.5281/zenodo.3581028)   | 1         | 42       | 221447   | 13.1            |
| [al-Zuhūr][zuhur_git]           | Cairo             | 1910--13      | [10.5281/zenodo.3580606](https://doi.org/10.5281/zenodo.3580606)   | 4         | 39       | 292333   | 25.6            |
| [Lughat al-ʿArab][lughat_git]   | Baghdad           | 1911--14      | [10.5281/zenodo.3514384](https://doi.org/10.5281/zenodo.3514384)   | 3         | 34       | 373832   | 35              |
| **total**                       |                   |               |                                                                    | 41        | 645      | c.6166783  |                 |

Table: [OpenArabicPE]{custom-style="Abbreviation"}'s corpus of periodical editions {#tbl:corpus}

[^tb1]: The current cut-off date is 1918.
[^tb3]: Size includes [TEI]{custom-style="Abbreviation"} files and bibliographic metadata ([BibTeX]{custom-style="Abbreviation"}, [MODS]{custom-style="Abbreviation"}).

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
[eap]: http://eap.bl.uk/
[eapb]: https://www.gale.com/intl/c/early-arabic-printed-books-literature-grammar-language-catalogues-and-periodicals 
[github]: https://www.github.com
[gh-pages]: https://pages.github.com/
[gpa]: https://www.eastview.com/resources/gpa/
[hathitrust]: http://catalog.hathitrust.org/
[histme]: https://github.com/Hist-ME
[internetarchive]: https://archive.org/
[menadoc]: http://menadoc.bibliothek.uni-halle.de/
[minimal]: http://go-dh.github.io/mincomp/about/
[mit-license]: https://opensource.org/licenses/MIT
[manar_git]: https://www.github.com/openarabicpe/journal_al-manar
[muqtabas_git]: https://github.com/OpenArabicPE/journal_al-muqtabas
[haqaiq_git]: https://github.com/OpenArabicPE/journal_al-haqaiq
[lughat_git]: https://github.com/OpenArabicPE/journal_lughat-al-arab
[ustadh_git]: https://github.com/OpenArabicPE/journal_al-ustadh
[zuhur_git]: https://www.github.com/openarabicpe/journal_al-zuhur
[openarabicpe_schema]: https://github.com/OpenArabicPE/OpenArabicPE_ODD
[openarabicpe_blog]: https://openarabicpe.github.io
[openarabicpe_zotero]: https://www.zotero.org/groups/OpenArabicPE
[orcid]: https://orcid.org/
[rawgit-old]: https://github.com/rgrove/rawgit
[saaid]: http://saaid.net/
[sakhrit]: http://archive.sakhrit.co
[shamela]: http://www.shamela.ws/
[tei]: https://www.tei-c.org
[tei_publisher]: https://teipublisher.com/ 
[translatio]: https://www.translatio.uni-bonn.de/online-zeitschriften/arabische-online-zeitschriften 
[wikisource]: https://wikisource.org/ 
[zenodo]: https://www.zenodo.org
[zotero]: https://www.zotero.org

# Contributor bio

[^fn1]: Available online at <https://openarabicpe.github.io> and <https://github.com/openarabicpe>. See also @Grallert2022DHQ.

[^cf1]: For a detailed overview of the state of Arab Periodical Studies see my [@Grallert+2020].

[^fn2]: For an introduction to the particularities of Arabic script see [@Nemeth+2017, 14-22].

[^fn3]: On the background of Unicode and its application to Arabic see [@Nemeth+2017, 400-406]. Nemeth also provides the most concise overview of the work of Thomas Milo, the most profound critic of digital approaches to Arabic script and the founder of DecoType [-@Nemeth+2017,410-434].

[^cf2]: The "Open Islamicate Texts Initiative Arabic-script OCR Catalyst Project" ([OpenITI ACOP]{custom-style="Abbreviation"}) will train models for the most frequent fonts and types [@InitiativeOpenITI+2019+TheOpenIslamicate] and their technology will eventually find its way into HathiTrust [@2020+HathiTrustResearchCenter].

[^cf3]: On the environmental cost of machine learning see  @Alkaoud.Syed+2020+OnTheImportance [124]; @Strubell.etal+2019+EnergyAndPolicy; @Baillot.etal+2021+DigitalHumanitiesAnd.

[^cf4]: E.g. [al-Muqtabas]{custom-style="Transcription"} [4 (5/6)](https://openarabicpe.github.io/journal_al-muqtabas/tei/oclc_4770057679-i_41.TEIP5.xml) and [8 (11/12)](https://openarabicpe.github.io/journal_al-muqtabas/tei/oclc_4770057679-i_94.TEIP5.xml).

[^fn4]: In other instances, such as the journals [*Lughat al-ʿArab*][lughat_git] and [*al-Ustādh*][ustadh_git], *al-Maktaba al-shāmila* did provide page breaks that correspond to a printed edition.

[^cf5]: @OpenArabicPE:journal_al-haqaiq; @OpenArabicPE:journal_al-manar; @OpenArabicPE:journal_al-muqtabas; @OpenArabicPE:journal_al-ustadh; @OpenArabicPE:journal_al-zuhur; @OpenArabicPE:journal_lughat-al-arab.  Since [Riḍā]{custom-style="persName"}'s [Tafsīr]{custom-style="Transcription"}, which accounts for about one fifth of [al-Manār]{custom-style="Transcription"}'s content, was not included [al-Maktaba al-Shāmila]{custom-style="Transcription"}'s transcription, it is also missing from the digital edition. See @Zemmin+2016 [232].