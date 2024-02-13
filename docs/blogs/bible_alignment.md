---
title: "Bible Alignment"
description: "One data source often used in low resource languages is the Bible. Simply put, the Bible has been translated to thousands of languages, including languages which may be considered as extremely low resourced. Aside from the diverse set of languages, data is also abundant. Some translations of the Bible only contain New Testament, but that itself already contains ~7900 translation pairs. If it happens to include the Old Testament, then we can get up to ~31000 translation pairs in total."
---

# Bible Alignment

One data source often used in low resource languages is the Bible. Simply put, the Bible has been translated to thousands of languages, including languages which may be considered as extremely low resourced. Aside from the diverse set of languages, data is also abundant. Some translations of the Bible only contain New Testament, but that itself already contains ~7900 translation pairs. If it happens to include the Old Testament, then we can get up to ~31000 translation pairs in total.

Languages of Indonesia is no exception, so we immediately saw the opportunity to leverage this.

In this blog, I would like to document a few challenges that I found while aligning the Bible. To be specific, aligning here is the task of mapping one verse to another. For instance, we map the Indonesian translation of Genesis 1:1 to that of the Javanese translation. On paper, this _sounds_ easy to do. Indeed, the majority of Bible verses align very well. By that I mean Genesis 1:1 in Indonesian really does correspond to the Javanese version.

But upon closer inspection, there are variations in how the verses are presented.

## Variation 1: Cascading Verses

I would call this first type of variation as "cascading" verses. Note that there may be an official term for this, but calling them "cascading" verses is just the most intuitive one for me.

Take **Exodus 6** in [Javanese](https://alkitab.mobi/jawa/Kel/6/), for example.

| #          | Verse                                                                                                                                                                                                                                                                                                                      |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Exodus 6:1 | (5-24) Nanging pangandikane Pangeran Yehuwah marang Nabi Musa: “Ing samengko sira bakal sumurup, apa kang bakal Suntandukake marang Pringon; anggone bakal nglilani lunga bangsa iki sarana dipeksa ing asta kang rosa, iya marga saka dipeksa dening asta kang rosa dheweke bakal nundhung bangsa iku saka ing nagarane.” |
| Exodus 6:2 | (6-1) Sabanjure Gusti Allah ngandika marang Nabi Musa mangkene: “Ingsun iki Yehuwah.                                                                                                                                                                                                                                       |
| Exodus 6:3 | (6-2) Ingsun wus ngatingal marang Abraham, Iskak lan Yakub, dadi Allah kang Mahakuwasa, nanging asmaningSun Yehuwah durung Sunsumurupake.                                                                                                                                                                                  |
| Exodus 6:4 | (6-3) Karodene Ingsun ora mung damel prasetyan karo leluhurira iku, yen bakal Sunparingi tanah Kanaan, tanah panggonane neneka,                                                                                                                                                                                            |

Notice that in front of each verse, there is an additional verse identifier. It says that the verse in **Exodus 6:1** is, actually **Exodus 5:24**? Because of that "shift", every other verse after that follows and hence "cascades".

!!! note

    Interestingly, the additional verse identifier is removed in the [NIV version](https://alkitab.mobi/niv/Kel/6#v1).

Note that if this shift is inconsistent across languages, it would certainly cause issues: verses are therefore not parallel and hence not valid translation pairs. Otherwise, we can simply drop these additional verse identifiers.

What I noticed that for this case ([Exodus 1:6](https://alkitab.mobi/jawa/Kel/6/1/)) in particular, the "shift", if identified, is parallel across languages:

| Language   | Version              | Verse                                                                                                                                                                                                                                                                                                                      |
| ---------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Javanese   | Jawa                 | (5-24) Nanging pangandikane Pangeran Yehuwah marang Nabi Musa: “Ing samengko sira bakal sumurup, apa kang bakal Suntandukake marang Pringon; anggone bakal nglilani lunga bangsa iki sarana dipeksa ing asta kang rosa, iya marga saka dipeksa dening asta kang rosa dheweke bakal nundhung bangsa iku saka ing nagarane.” |
| Indonesian | Terjemahan Baru (TB) | (5-24) Tetapi TUHAN berfirman kepada Musa: "Sekarang engkau akan melihat, apa yang akan Kulakukan kepada Firaun; sebab dipaksa oleh tangan yang kuat ia akan membiarkan mereka pergi, ya dipaksa oleh tangan yang kuat ia akan mengusir mereka dari negerinya."                                                            |
| Sundanese  | Sunda                | PANGERAN ngandika ka Musa, "Tenjokeun ku maneh rek dikumahakeun eta raja teh ku Kami. Saenya-enyana, ku Kami rek dipaksa nepi ka manehna kapaksa ngaluarkeun umat Kami ti nagarana."                                                                                                                                       |
| Madurese   | Madura               | (5-24) Dhabuna PANGERAN ka Mosa, "Sateya ba’na bakal nangaleyana epabaramma’a rato jareya bi’ Sengko’. Rato jareya bi’ Sengko’ epaksa’a mabebas Tang bangsa. Saongguna, bi’ Sengko’ rato jareya epaksa’a ngojuk Tang bangsa jareya dhari nagara reya."                                                                     |
| Balinese   | Bali                 | Ida Sang Hyang Widi Wasa raris ngandika ring Dane Musa: “Ane jani kita lakar nepukin saluiring ane lakar laksanayang Ulun marep teken sang prabu. Ulun lakar maksa ia, apang ia maang kaulan Ulune makaad. Sasajaane Ulun lakar maksa ia apanga ia nundung kaulan Ulune uli guminnyane.”                                   |

## Variation 2: Combined Verses

I would call the second type of variation as "combined verses". At times we can sort of consider this as a derivation of variation #1. An example of this is **Revelations 13:1**, again, in [Javanese](https://alkitab.mobi/jawa/Why/13/).

| #                | Verse                                                                                                                                                                                                                                           |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Revelations 13:1 | (12-18) lan banjur manggon ana ing pinggir sagara. (13-1) Sabanjure aku weruh ana kewan njedhul saka sajroning sagara, sungune sapuluh lan endhase pitu; pucuking sungune ana makuthane sapuluh, lan ing endhase ana cirine jeneng panyenyamah. |
| Revelations 13:2 | Kewan kang dakdeleng iku rupane kaya macan tutul, sikile kaya sikil bruwang lan cangkeme kaya cangkem singa. Iku banjur diwenehi kasekten dening naga mau, lan dhampar tuwin panguwasane kang gedhe.                                            |
| Revelations 13:3 | Aku nuli ndeleng endhase kang siji iku kaya ana tatune kang mbebayani tumrap uripe, nanging tatune banjur waras. Temah wong sadonya padha kaeraman, banjur ngetut buri kewan iku.                                                               |

Notice that **Revelations 13:1** contains **both** **Revelations 12:18** and **13:1**. We might presume that verses will cascade, but in this case, they don't. Now, the questions are:

1. Do we assign the sub-verse **12:18** as "**Revelations 12:18**" explicitly? Or do we consider it part of **Revelations 13:1**?
2. How do other languages handle this?

I would opt to answer the second question first, since that'll be important to ultimately decide whether it is parallel, i.e., if is a valid translation pair. With a simple [verse comparison](https://alkitab.mobi/jawa/Why/13/1/), we find:

| Language   | Version              | Verse                                                                                                                                                                                                                                                                                                     |
| ---------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Javanese   | Jawa                 | (12-18) lan banjur manggon ana ing pinggir sagara. (13-1) Sabanjure aku weruh ana kewan njedhul saka sajroning sagara, sungune sapuluh lan endhase pitu; pucuking sungune ana makuthane sapuluh, lan ing endhase ana cirine jeneng panyenyamah.                                                           |
| Indonesian | Terjemahan Baru (TB) | (12-18) Dan ia tinggal berdiri di pantai laut. (13-1) Lalu aku melihat seekor binatang keluar dari dalam laut, bertanduk sepuluh dan berkepala tujuh; di atas tanduk-tanduknya terdapat sepuluh mahkota dan pada kepalanya tertulis nama-nama hujat.                                                      |
| Sundanese  | Sunda                | (12-18) Gen naga ngajanteng di sisi basisir. (13-1) Ti dinya kaula nenjo aya hiji sato hanjat ti laut, huluna tujuh tandukna sapuluh. Unggal tanduk make makuta, dina unggal huluna aya tulisan hiji ngaran anu ngahina ka Allah.                                                                         |
| Madurese   | Madura               | (12-18) Naga ganeka laju manjeng e paseser. (13-1) Kaula pas nengale badha keban raja kalowar dhari dhalem tase’. Keban ganeka atandhu’ sapolo ban acethak papetto’. E tandhu’na se sapolo ganeka badha jamang settong ebang, ban e saneyap cethagga badha tolesanna, aropa nyama panyeya’an ka Allah.    |
| Balinese   | Bali                 | (12-18) Nagane punika raris nyeleg ring sisin segarane. (13-1) Tumuli tiang ngatonang sato asiki medal saking tengah segarane. Satone punika matanduk adasa, tur tenggekipune pepitu. Sabilang tanduknyane madaging gegelungan asiki. Tur ring sabilang tenggeknyane matulis satunggiling wasta kanistan. |

Luckily, this verse combination is consistent across versions. Thus, whether or not we decide to split the verse into two subverses may not really matter here because parallelism is maintained.

!!! note

    Similarly, those additional verse identifiers are removed in the [NIV version](https://alkitab.mobi/niv/Why/13#v1).

But, if we're opting for a simple solution, again, we can just drop the additional verse identifier. Therefore, we retain the same "drop-verse-identifier" method we opted for variation #1.

## Variation 3: Verse Ranges

Now, the last variation is the one that I find to be the most problematic due to its inconsistency across different versions of the Bible. If I'm not mistaken, this variation is known as "verse ranges", where one text may correspond to more than one verse identifiers. I will take **Acts 8:28** as an example:

| Language   | Version              | Verse                                                                                                         |
| ---------- | -------------------- | ------------------------------------------------------------------------------------------------------------- |
| Javanese   | Jawa                 | Nalika samono panjenengane lagi tindak kondur nitih kreta karo maos kitabe Nabi Yesaya.                       |
| Indonesian | Terjemahan Baru (TB) | Sekarang orang itu sedang dalam perjalanan pulang dan duduk dalam keretanya sambil membaca kitab nabi Yesaya. |
| Sundanese  | Sunda                | (8:27)                                                                                                        |
| Madurese   | Madura               | (8:27)                                                                                                        |
| Balinese   | Bali                 | (8:27)                                                                                                        |

Notice that in languages like Sundanese, Madurese, and Balinese, **Acts 8:28** is just pointing to **Acts 8:27**. This is because, in those versions, the "text" in **Acts 8:27** actually corresponds to **Acts 8:27-28**, **both verses**. But observe that this is not the case for other languages! Clearly, the Javanese and Indonesian versions do not have that "verse range". Instead, there is an explicit split/distinction between verses 27 and 28.

See the following table[^1] for a comparison of how verse ranges differ across languages:

| Version                         | #         | Verse                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| New International Version (NIV) | Acts 8:27 | {++So he started out, and on his way he met an Ethiopian eunuch, an important official in charge of all the treasury of Candace, queen of the Ethiopians. This man had gone to Jerusalem to worship,++}                                                                                                                                                                                                                                                               |
|                                 | Acts 8:28 | {==and on his way home was sitting in his chariot reading the book of Isaiah the prophet.==}                                                                                                                                                                                                                                                                                                                                                                          |
| Terjemahan Baru (TB)            | Acts 8:27 | {++Lalu berangkatlah Filipus. Adalah seorang Etiopia, seorang sida-sida, pembesar dan kepala perbendaharaan Sri Kandake, ratu negeri Etiopia, yang pergi ke Yerusalem untuk beribadah. ++}                                                                                                                                                                                                                                                                            |
|                                 | Acts 8:28 | {==Sekarang orang itu sedang dalam perjalanan pulang dan duduk dalam keretanya sambil membaca kitab nabi Yesaya.==}                                                                                                                                                                                                                                                                                                                                                   |
| Sunda                           | Acts 8:27 | {++(8:27-28) Pilipus geuwat angkat. Di eta jalan aya hiji pajabat luhur urang Etiopia, anu ngurus harta kakayaan Sri Kandasi ratu nagri Etiopia, tas ti Yerusalem ngalakonan ibadah.++} {==Eta pajabat tunggang kareta seja mulih ka nagarana, sajajalan ngaos Kitab Nabi Yesaya.==}                                                                                                                                                                                  |
|                                 | Acts 8:28 | (8:27)                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Bali                            | Acts 8:27 | {++Irika Dane Pilipus makinkin raris mamargi. Duk punika wenten prakangge agung saking jagat Etiopia nuju mamargi mantuk. Prakangge agung punika, dados prakangge buat ngetangang druen Sri Kandake, Sang Raja Putri ring jagat Etiopia. Dane sampun lunga ka kota Yerusalem ngaturang bakti ring Ida Sang Hyang Widi Wasa,++} {==tur sane mangkin dane mawali mantuk nglinggihin kreta. Sajeroning pamargin danene punika, dane ngwacen cakepan dane Nabi Yesaya.==} |
|                                 | Acts 8:28 | (8:27)                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

You can quickly observe that verse ranges are highly inconsistent. In versions like NIV and TB, the verses are separated. But for those that are combined, the point where they split is not stated, i.e., verses are grouped into "ranges".

How to best approach this variation remains unclear for the time being. If we were to ignore the verse identifiers just like in variations #1 and #2 above, we would end up producing verses that don't align to each other. One verse may contain "additional texts" that seem to just be "neglected" during the translation process -- where in fact, that's certainly not the case.

One solution that I could think of is mark verses with ranges as actual verse ranges, instead of treating them as a single verse. The updated version of the table above should describe this better:

| Version | #                                  | Verse                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------- | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sunda   | {--Acts 8:27--} {++Acts 8:27-28++} | {++Pilipus geuwat angkat. Di eta jalan aya hiji pajabat luhur urang Etiopia, anu ngurus harta kakayaan Sri Kandasi ratu nagri Etiopia, tas ti Yerusalem ngalakonan ibadah. Eta pajabat tunggang kareta seja mulih ka nagarana, sajajalan ngaos Kitab Nabi Yesaya.++}                                                                                                                                                                                            |
|         | {--Acts 8:28--}                    | {--(8:27) --}                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Bali    | {--Acts 8:27--} {++Acts 8:27-28++} | {++Irika Dane Pilipus makinkin raris mamargi. Duk punika wenten prakangge agung saking jagat Etiopia nuju mamargi mantuk. Prakangge agung punika, dados prakangge buat ngetangang druen Sri Kandake, Sang Raja Putri ring jagat Etiopia. Dane sampun lunga ka kota Yerusalem ngaturang bakti ring Ida Sang Hyang Widi Wasa, tur sane mangkin dane mawali mantuk nglinggihin kreta. Sajeroning pamargin danene punika, dane ngwacen cakepan dane Nabi Yesaya.++} |
|         | {--Acts 8:28--}                    | {--(8:27) --}                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

Notice that we can not only drop verse identifiers, which was the solution we chose for the two aforementioned variations, but also avoid aligning verses that do not correspond. We can treat the new verse ranges as the "primary key" of that text.

Therefore, when we do a table join with other Bible versions that do not have verse ranges, the invalid translation pair will not be produced. On the flipside, when we match Bible versions that have the same verse ranges as primary keys, the two will match and hence produce a new valid translation pair.

We can apply the same solution for ranges that span more than two verses, it will just be a longer text. This also remains applicable even if there may be sub-splits of verses (e.g. verse 6a, 6b, etc.). Taking **Matthew 1** in [Sundanese](https://alkitab.mobi/sunda/Mat/1/) as an example, we can modify:

| #            | Verse                                                                                                                                                                                                                                                                                                      |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Matthew 1:1  | Ieu daptar karuhun-karuhun Yesus Kristus turunan Daud, ari Daud turunan Ibrahim.                                                                                                                                                                                                                           |
| Matthew 1:2  | (1:2-6a) Ti Ibrahim turun-tumurun nepi ka Raja Daud kieu pareleanana: Ibrahim, Ishak, Yakub, Yuda jeung saderek-saderekna, Peres, Serah (ti ibu Tamar), Hesron, Ram, Aminadab, Nahson, Salmon, Boas (ibuna Boas nya eta Rahab), Obed, Isai, Raja Daud.                                                     |
| Matthew 1:3  | (1:2)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:4  | (1:2)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:5  | (1:2)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:6  | (1:6b-11) Ti Daud turun-tumurun nepi ka jaman urang Israil diboyong ka Babul kieu pareleanana: Daud ti geureuhana anu asalna garwa Uria, puputra Suleman, ti Suleman turun-tumurun: Rehabam, Abia, Asa, Yosapat, Yehoram, Usia, Yotam, Ahas, Hiskia, Menase, Amon, Yosia, Yoyakin jeung saderek-saderekna. |
| Matthew 1:7  | (1:6)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:8  | (1:6)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:9  | (1:6)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:10 | (1:6)                                                                                                                                                                                                                                                                                                      |
| Matthew 1:11 | (1:6)                                                                                                                                                                                                                                                                                                      |

as:

| #                    | Verse                                                                                                                                                                                                                                                                                            |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Matthew 1:1          | Ieu daptar karuhun-karuhun Yesus Kristus turunan Daud, ari Daud turunan Ibrahim.                                                                                                                                                                                                                 |
| {++Matthew 1:2-5++}  | Ti Ibrahim turun-tumurun nepi ka Raja Daud kieu pareleanana: Ibrahim, Ishak, Yakub, Yuda jeung saderek-saderekna, Peres, Serah (ti ibu Tamar), Hesron, Ram, Aminadab, Nahson, Salmon, Boas (ibuna Boas nya eta Rahab), Obed, Isai, Raja Daud.                                                    |
| {++Matthew 1:6-11++} | Ti Daud turun-tumurun nepi ka jaman urang Israil diboyong ka Babul kieu pareleanana: Daud ti geureuhana anu asalna garwa Uria, puputra Suleman, ti Suleman turun-tumurun: Rehabam, Abia, Asa, Yosapat, Yehoram, Usia, Yotam, Ahas, Hiskia, Menase, Amon, Yosia, Yoyakin jeung saderek-saderekna. |

Interestingly, the [Balinese version](https://alkitab.mobi/bali/Mat/1/) of **Matthew 1:1-11** are **not** ranged (!), unlike the Sundanese version, despite the fact that they do have similar ranges in **Acts 8:27-28** as we have just seen earlier. We could potentially avoid non-matching translation pairs by assigning a verse range as primary key.

## Closing Thoughts

If my hypothesis is correct and there remains no other variations to be kept in mind, then we should be able to produce a decently aligned[^2] Bible translation dataset, which we then can use to train a neural machine translation (NMT) model.

---

_Written by Wilson Wongso. Last updated 12 December 2022._

[^1]: Highlights added manually. Highlights are also just estimates, they may not correspond/align perfectly.
[^2]: "Decently aligned" because Bible verses may not even be 1-to-1 to begin with! How much this impacts the quality of the translation model could be further investigated.
