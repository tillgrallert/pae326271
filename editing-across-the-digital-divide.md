---
title: 2023_dh-in-practice  
author:
---

---
title: "Editing mundane texts across the digital divide"
subtitle: "the case of Arabic periodicals from the late nineteenth-century Eastern Mediterranean"
project: "Digital Humanities in Practice"
author: Till Grallert
date: 2023-02-01
ORCID: orcid.org/0000-0002-5739-8094
DOI: doi.org/10.5281/zenodo.999976
licence: http://creativecommons.org/licenses/by-nd/4.0/
bibliography: assets/bibliography/2023_dh-in-practice.csl.json
suppress-bibliography: true
reference-section-title: "Bibliography"
abstract:
lang: en-US
tags:
    - pae326271
---


# abstract

The essay introduces the project [[*Open Arabic Periodical Editions*]{custom-style="EmphasisCustom"} (OpenArabicPE)](https://openarabicpe.github.io) as a case study of minimal computing to address the specific challenges and affordances of digital humanities in the Eastern Mediterranean. I will outline the socio-technical challenges for digital approaches to the cultural heritage of societies outside the Global North. I pose that a digital episteme and infrastructures deeply rooted in 20th-century, english-speaking, American neoliberal capitalism cause a neo-orientalist silencing of the material heritage of predominantly Arabic-speaking Islamicate societies. This places the onus of digitising the textual heritage on individual scholars and citizens and requires mitigation strategies on every level of the digital workflow. The enormity of the problem is illustrated by the following example: Less than 1/20, or 145, of all c.3300 Arabic periodical titles published globally before 1930 are  digitised. Almost all of them solely as facsimiles and most incomplete. 145 periodicals hidden through geo-fencing, behind paywalls, in proprietary data silos, and served through non-Arabic interfaces for a community of more than 400 million Arabic speakers. 

Influenced by [[*minimal computing*]{custom-style="EmphasisCustom"}](http://go-dh.github.io/mincomp/) and [[*pirate care*]{custom-style="EmphasisCustom"}](https://pirate.care) and based on the guiding principles of *accessibility*, *simplicity*, *sustainability* and *credibility*, OpenArabicPE originated in 2015 from an attempt to address the core problem of corpus building: the lack of functional Arabic OCR without which one would have to resort to human transcribers. Yet, we could produce reliable ground truth for improving and---with the advent of machine-learning based approaches---training OCR algorithms by combining existing transcriptions from shadow libraries, such as [*al-Maktaba al-Shāmila*](http://shamela.ws/), with openly available digital facsimiles for the purpose of validating the former.

The essay will critically reflect on OpenArabicPE and introduce the workflows to produce standard-compliant, machine-actionable, scholarly digital editions of Arabic periodicals by creatively repurposing open and free-to-use tools and platforms, which allow us to currently host full-text TEI XML editions of some 630 issues from six journals and more than 7 million words without any funding and resources beyond our own labour time and laptop computers.


"Open Arabic Periodical Editions (OpenArabicPE)"[^fn1]  was born in 2015 out of a need and with a simple idea. I had just finished my PhD on the history of the street in late Ottoman Damascus and moved to Beirut for a new post-doctoral research project on the genealogy of food riots across the predominantly Arabic-speaking Eastern Mediterranean. 
The main source for both projects were periodicals---tens of thousands of newspaper and magazine articles published across the region. But despite their quotidian nature, their pivotal role for central cultural phenomena of the time as the regions first mass medium, and ubiquitous references in scholarly literature, surprisingly little of substance is known about this medium in terms of individual publication histories, distribution channels, and audiences or the number and whereabouts of surviving copies. This is particularly true for locations beyond the centers of the press in Beirut and Cairo.[^cf1]

The first need, therefore, was (and still is) a need for improving our knowledge about periodicals as the embodiment of socio-economic relations, intellectual traditions, and political frameworks, their manifestation in a limited number of material artefacts, the transmission of individual artefacts into private and public collections, and finally their occasional digital remediation. I would need to know which paper was published and potentially covered the series of food riots across cities of the Syrian hinterland, such as Hama and Homs in summer 1910 [C.f. @Grallert+2019]. I would then need to know if copies survived the turmoil that since wreaked havoc upon the region and its cultural heritage over the last century, where to find surviving copies, and how to access them. As the number of potential data points in this set numbers into the thousands and as library catalogues had moved into the networked digital realm ages ago, or so I thought, all metadata should be machine actionable, conform to established standards in the field, and link to some sort of externally controlled authority files for disambiguating and enriching information. 

At this point we have to acknowledge the multi-layered digital divide, a chicken-egg problem that is difficult to tease appart

Printed union catalogues are a Herculean task and have largely fallen out of fashion with the advent of COPACs. Given their publication dates and the neccessary time for information collection, they should probably be read as historical sources rather than finding aids [E.g. @ElHadi+1965; @Hopwood+1970; @Aman+1979; @DeJong+1979; @Iḥdādan+1984; @Khūrī+1985; @Höpp+1994; @Atabaki+1995]. Likewise, library catalogues are layered historical documents that accumulate traces of their socio-technic affordances with each remediation. Looking at one of the many entries for [ʿAbdallāh Nadīm al-Idrīsī]{custom-style="persName"}'s weekly journal [al-Ustādh]{custom-style="Transcription"}, published in Cairo from 1892 to 1893, in Wordcat, we most likely will not encounter a record newly created from the material artefact by an expert cataloguer with domain knowledge in Arabic periodicals and the ability to read Arabic script. Even with the necessary domain knowledge she will most likely have had to contend with technological systems ill-suited, if not unable, to deal with the metadata in its original script, calendars or naming conventions. 

Type-written card-catalogues, hot-metal printing presses, electronic computers (understood as an interdependent combination of hardware and software) all necessitate error-prone transcription, translation, and normalisation, which themselves are bound up in historically contingent cultural traditions. The aforementioned journal is a simple, yet powerful example. [al-Ustādh]{custom-style="Transcription"} is, of course, a Latin transliteration of the Arabic
 الاستاذ
, as is the rendering of the publisher's name 
عبد الله النديم الإدريسي
 as Muḥammad Kurd ʿAlī. These transcriptions follow the widely adopted system of the International Journal of Middle East Studies. The Deutsche Morgenländische Gesellschaft devised a different system with 1:1 character transliterations. Catalogers in German-speaking countries would therefore record the title as [al-Ustāḏ]{custom-style="Transcription"}. Both systems require diacritics not available on technical systems, while a common Francophone rendition would be [el Oustad]{custom-style="Transcription"}.

## The digital divide

## Open Arabic Periodical Editions







Those familiar with   


 material artefacts, the historical socio-economic relations and political frameworks they were produced in,   and to gather what is commonly referred to as verified and verifiable metadata. Metadata about periodicals, the people involved, and collections. 

Thus I followed the history guilds established traditions and just delved into local collections and read every issue from front to back. From the British Library in London to the Staatsbibliothek in Berlin, to the American University of Beirut's Jafet Library, this meant spending months hunched over dimly lit microfilm projectors trying to decipher badly abused copies.

- Need for knowledge about these artefacts
- Need for access to these artefacts: reading and computation
- Despite all advances in digitisation efforts and machine-learning approaches to OCR/HTR that finally manages to transcribe nineteenth-century Arabic with a reasonably low CER, the digital divide persists.

- David Wrisley's invitation to teach an introduction to TEI at DHIB 2015
- Meeting Alex Gil 
- Minimal computing

The corpus comprises six fully searchable editions: [Muḥammad Kurd ʿAlī]{custom-style="persName"}'s journal [al-Muqtabas]{custom-style="Transcription"} (Cairo and Damascus, 1906--18, not to be confused with his newspaper of the same name), [ʿAbd al-Qādir al-Iskandarānī]{custom-style="persName"}'s  [al-Ḥaqāʾiq]{custom-style="Transcription"} (Damascus, 1910--12), [Anastās Mārī al-Karmalī]{custom-style="persName"}'s [Lughat al-ʿArab]{custom-style="Transcription"} (Baghdad, 1911--14), {--and from Cairo--} [Muḥammad Rashīd Riḍā]{custom-style="persName"}'s [al-Manār]{custom-style="Transcription"} (Cairo, 1898--1940), [Anṭūn al-Jumayyil]{custom-style="persName"}'s [al-Zuhūr]{custom-style="Transcription"} (Cairo, 1910--{--19--}13), and [ʿAbdallāh Nadīm al-Idrīsī]{custom-style="persName"}'s weekly journal [al-Ustādh]{custom-style="Transcription"} (Cairo, 1892--1893).[^cf2]

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

# Contributor bio

[^fn1]: Available online at <https://openarabicpe.github.io> and <https://github.com/openarabicpe>. See also @Grallert2022DHQ.

[^cf1]: For a detailed overview of the state of Arab Periodical Studies see my [@Grallert+2020].

[^cf2]: @OpenArabicPE:journal_al-haqaiq; @OpenArabicPE:journal_al-manar; @OpenArabicPE:journal_al-muqtabas; @OpenArabicPE:journal_al-ustadh; @OpenArabicPE:journal_al-zuhur; @OpenArabicPE:journal_lughat-al-arab.  Since [Riḍā]{custom-style="persName"}'s [Tafsīr]{custom-style="Transcription"}, which accounts for about one fifth of [al-Manār]{custom-style="Transcription"}'s content, was not included [al-Maktaba al-Shāmila]{custom-style="Transcription"}'s transcription, it is also missing from the digital edition. See @Zemmin+2016 [232].