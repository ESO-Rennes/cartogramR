# cartogramR
cartogramR: a R package for fast computing contiguous cartograms


Cartograms are a speciﬁc type of map on which the size of spatial units is proportional to a statistical weight (number of inhabitants, amount of CO2 emitted, etc.). Cartograms have long been used and are nowadays widely present in books, newspapers and on the web. Over the last decades, several methods have been proposed to build contiguous cartograms and many algorithms exist today optimizing different components, such as statistical accuracy, shape accuracy, and topological accuracy. Nonetheless, the running time of these algorithms remained a problem for a long time until the algorithm of Gastner, Seguy, and More (2018) was released. These authors introduced a fast flow-based algorithm whose equations are easier to solve compared to previous methods. The objective of this paper is to present a new easy-to-use R package, called cartogramR, which implements this last high-performance algorithm along with two other widespread algorithms (Gastner and Newman (2004); Dougenik, Chrisman, and Niemeyer (1985)). The cartogramR package works with sf objects, a common storage and access model of geographic feature formalized by both the Open Geospatial Consortium and the International Organization for Standardization. 


Bertin J (1967). Sémiologie graphique: les diagrammes, les réseaux, les cartes. Mouton & Gauthier-Villars, Paris-La Haye.

Bertin J (1983). Semiology of graphics: diagrams, networks, maps. The University of Wisconsin Press, Madison, (trans. W. j. Berg). ISBN 0-299-09060-4.

Cauvin C, Escobar F, Serradj A (2007). Cartographie thématique 2 – Des transformations incontournables. Traité IGAT  – Information Géographique et Aménagement du Territoire ; Aspects fondamentaux de l’analyse spatiale. Hermès-Lavoisier.

Cauvin C, Escobar F, Serradj A (2010).  Cartography and the Impact of the Quantitative Revolution. John Wiley & Sons, Inc. doi:10.1002/9781118558126.

Dorling D (1996).  “Area Cartograms: Their  Use and Creation.”   In Concepts and Techniques in Modern Geography, 59. University of East Anglia: Environmental Publications, Norwich. ISBN I-872464-09-2. URL http://www.dannydorling.org/wp-content/files/dannydorling_publication_id1448.pdf.

Dougenik JA, Chrisman NR, Niemeyer DR (1985). “AN  Algorithm  To Construct Continuous Area Cartograms.”   The Professional Geographer, 37(1), 75–81. doi:10.1111/j.
0033-0124.1985.00075.x.

Gastner MT,  Newman MEJ  (2004).   “Diffusion-Based Method  for  Producing Density-Equalizing Maps.”  Proceedings of the National Academy of Sciences, 101(20), 7499–7504. doi:10.1073/pnas.0400280101.

Gastner MT,  Seguy V, More P (2018). “Fast Flow-Based Algorithm  for Creating Density-Equalizing Map Projections.”  Proceedings of the National Academy of Sciences, 115(10), E2156–E2164. doi:10.1073/pnas.1712674115.

Guseyn-Zade SM, Tikunov VS (1994). “Compilation of linear transformed images.” Mapping Sciences and Remote Sensing, 31(1), 34–48. doi:10.1080/07493878.1994.10641952.

House D, Kocmoud C (1998). “Continuous cartogram construction.”  In Proceedings Visual- ization ’98 (Cat. No.98CB36276), pp. 197–204. doi:10.1109/VISUAL.1998.745303.

Nusrat S, Kobourov S (2016). “The State of the Art  in Cartograms.”  Computer Graphics Forum, 35(3), 619–642. doi:10.1111/cgf.12932.

Olson JM (1976). “Noncontiguous Area Cartograms.”  The Professional Geographer, 28(4), 371–380. doi:10.1111/j.0033-0124.1976.00371.x.

Pebesma E (2018). “Simple Features for R: Standardized Support for Spatial Vector Data.” The R Journal, 10(1), 439–446. doi:10.32614/RJ-2018-009.

Tennekes M (2018). “Tmap:  Thematic Maps in R.”  Journal of Statistical Software, 84(6). doi:10.18637/jss.v084.i06.

Tobler W (2004). “Thirty Five Years of Computer Cartograms.”  Annals of the Association of American Geographers, 94(1), 58–73. doi:10.1111/j.1467-8306.2004.09401004.x.

van Kreveld M, Speckmann B (2007). “On Rectangular Cartograms.”  Computational Geometry, 37(3), 175–187. doi:10.1016/j.comgeo.2006.06.002.

