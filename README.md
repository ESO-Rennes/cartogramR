# cartogramR
cartogramR: a R package for fast computing contiguous cartograms

Release: 2021-07-05


<p><a target="_blank" rel="noopener noreferrer"><img src="https://github.com/ESO-Rennes/cartogramR/blob/main/Logo_cartogramR.png" style="max-width:200%;"></a></p>



<br><strong>ENGLISH-------------</strong>

<strong>What is a cartogram and what is cartogramR meant for?</strong>

Cartograms are a speciﬁc type of map on which the size of spatial units is proportional to a statistical weight (number of inhabitants, amount of CO2 emitted, etc.). Cartograms have long been used and are nowadays widely present in books, newspapers and on the web. Over the last decades, several methods have been proposed to build contiguous cartograms and many algorithms exist today optimizing different components, such as statistical accuracy, shape accuracy, and topological accuracy. Nonetheless, the running time of these algorithms remained a problem for a long time until the algorithm of Gastner, Seguy, and More (2018) was released. These authors introduced a fast flow-based algorithm whose equations are easier to solve compared to previous methods. 

The objective of this post is to present a new easy-to-use R package, called <i>cartogramR</i>, which implements this last high-performance algorithm along with two other widespread algorithms (Gastner and Newman (2004); Dougenik, Chrisman, and Niemeyer (1985)). The <i>cartogramR</i> package works with sf objects, a common storage and access model of geographic feature formalized by both the Open Geospatial Consortium and the International Organization for Standardization. 

</br> <strong>Development team</strong>

<i>cartogramR</i> was developped by <a href="https://perso.univ-rennes2.fr/pierre-andre.cornillon" target="_new" rel="noopener"><strong>Pierre-André Cornillon</strong></a>  (UMR CNRS 6625 - IRMAR : Institut de Recherche Mathématique de Rennes - Université Rennes 2) and <a href="https://perso.univ-rennes2.fr/florent.demoraes" target="_new" rel="noopener"><strong>Florent Demoraes</strong></a> (UMR CNRS 6590 - ESO : Espaces et Sociétés - Université Rennes 2).

<a target="_blank" rel="noopener noreferrer"><img src="https://github.com/ESO-Rennes/cartogramR/blob/main/Logo_irmar.png" width="60"></a>    <a target="_blank" rel="noopener noreferrer"><img src="logo_ESO.png" width="50"></a>


<i>cartogramR</i> user guide: https://hal.archives-ouvertes.fr/hal-03280009/document

<br>
Link to download <i>cartogramR</i> from the CRAN : https://cran.r-project.org/web/packages/cartogramR/index.html

<br>Note that if you install package from sources, you will need first to install FFTW (http://www.fftw.org/)


</br> <strong>Acknowledgements</strong>


Many thanks to:

- Michael T. Gastner for his flow based cartogram programs on which cartogramR is based.
- Timothée Giraud (UMS 2414 RIATE / CNRS Paris) for suggestions and careful reading.


<br>
<br><strong>FRANÇAIS-------------</strong>




</br> <strong>Qu'est-ce qu'un cartogramme et à quoi sert cartogramR ?</strong>

Les cartogrammes sont un type d'anamorphose cartographique sur lequel la taille des unités spatiales est proportionnelle à un poids statistique (nombre d'habitants, quantité de CO2 émise, etc.). Les cartogrammes sont utilisés depuis longtemps et sont aujourd'hui largement présents dans les livres, les journaux et sur le web. Au cours des dernières décennies, plusieurs méthodes ont été proposées pour construire des cartogrammes contigus et il existe aujourd'hui de nombreux algorithmes optimisant différentes composantes, telles que la précision statistique, la précision de forme et la précision topologique. Néanmoins, le temps d'exécution de ces algorithmes est resté longtemps un problème jusqu'à la sortie de l'algorithme de Gastner, Seguy et More (2018). Ces auteurs ont introduit un algorithme rapide utilisé pour modéliser la diffusion des  fluides et dont les équations sont plus faciles à résoudre par rapport aux méthodes précédentes. 

L'objectif de ce billet est de présenter un nouveau package R facile à utiliser, appelé <i>cartogramR</i>, qui implémente ce dernier algorithme performant ainsi que deux autres algorithmes répandus (Gastner et Newman (2004) ; Dougenik, Chrisman et Niemeyer (1985)). Le package <i>cartogramR</i> fonctionne avec des objets sf, un modèle commun de stockage et d'accès aux objets géographiques formalisé à la fois par l'Open Geospatial Consortium et l'Organisation internationale de normalisation. 

</br> <strong>Équipe de développement</strong>

<i>cartogramR</i> a été développé par <a href="https://perso.univ-rennes2.fr/pierre-andre.cornillon" target="_new" rel="noopener"><strong>Pierre-André Cornillon</strong></a> (UMR CNRS 6625 - IRMAR : Institut de Recherche Mathématique de Rennes - Université Rennes 2) et <a href="https://perso. univ-rennes2.fr/florent.demoraes" target="_new" rel="noopener"><strong>Florent Demoraes</strong></a> (UMR CNRS 6590 - ESO : Espaces et Sociétés - Université Rennes 2).

<a target="_blank" rel="noopener noreferrer"><img src="https://github.com/ESO-Rennes/cartogramR/blob/main/Logo_irmar.png" width="60"></a> <a target="_blank" rel="noopener noreferrer"><img src="logo_ESO.png" width="50"></a>.


Guide d'utilisation de <i>cartogramR</i> : https://hal.archives-ouvertes.fr/hal-03280009/document

<br> Lien pour télécharger <i>cartogramR</i> depuis le CRAN : https://cran.r-project.org/web/packages/cartogramR/index.html

<br> Notez que si vous installez le package à partir des sources, vous aurez besoin d'installer au préalable FFTW (http://www.fftw.org/)


</br> <strong>Remerciements</strong>


Un grand merci à :

- Michael T. Gastner pour ses programmes de diffusion des fluides et sur lesquels cartogramR repose.
- Timothée Giraud (UMS 2414 RIATE / CNRS Paris) pour ses suggestions et sa lecture attentive.



</br> <p><a target="_blank" rel="noopener noreferrer"><img src="https://github.com/ESO-Rennes/cartogramR/blob/main/carto_france_pop_doctors.png" width="750"></a></p>


Script to create the above cartogram <br>(no extra package, just cartogramR and R base functions)
---------

###Population and number of general practitioners for 100,000 inhabitants in France in 2018####

library(cartogramR)<br>
data(france_dept)

#compute cartogram based on population size<br>
france_cartogram <- cartogramR(france_dept, count="pop2018")

#create a color palette<br>
ColorPalette <- c('#fee5d9','#fcae91','#fb6a4a','#cb181d')<br>
palette(ColorPalette)

#cut the second variable into quantiles for choropleth map<br>
breaks <- quantile(france_cartogram$initial_data$n_gp_per100000)<br>
ngalpractFac <- cut(france_dept$n_gp_per100000, breaks, include.lowest=TRUE)<br>

#coerce cartogram to sf object<br>
france_cartogram <- as.sf(france_cartogram)

#main plot<br>
plot(france_cartogram$geometry, 
     main = "Population and number of general practitioners \nfor 100,000 inhabitants in France in 2018", 
     col = ngalpractFac, add=FALSE)

#bounding box and size<br>
bbox <- sf::st_bbox(as.sfc(france_cartogram))<br>
Deltax <- bbox["xmax"] -  bbox["xmin"]<br>
Deltay <- bbox["ymax"] -  bbox["ymin"]<br>

#sources and credits<br>
auth <- "Authors: F. Demoraes, P.-A. Cornillon"<br>
sources <- "Sources: INSEE (2018), DREES,\nASIP-Santé RPPS (2018)"<br>
desc <- "Distortion based on population size"<br>
ttext <- paste(auth, "|", sources, "-", desc)<br>
mtext(text = ttext, side = 4, line = -0.01, adj = 0, cex = 0.5, col = "grey50")<br>
text(bbox["xmax"]-0.15*Deltax, bbox["ymax"]-0.02*Deltay, "N\↑",cex = 1.2)<br>

#histogram<br>
op <- par(fig = c(0.03,0.3,0.1,0.3), mar = c(0,0,0,0), mgp=c(0,0.5,0), omi=c(0,0,0,0), new = TRUE, bty="n")<br>
hist(france_dept[["n_gp_per100000"]], breaks = breaks, freq = FALSE, col = 1:4, axes = F, ann=F,  border = "White")<br>
axis(side = 1, at = breaks, labels = round(breaks), cex.axis = 0.5, tick = FALSE, line = -1, col.axis = "Black")<br>
par(op)


-----

</br> <strong>Other examples / Autres exemples</strong>

Tutorial published within the framework of the <a href="https://transcarto.sciencesconf.org/" target="_new" rel="noopener">École Thématique TRANSCARTO (Transformations cartographiques)</strong></a> 18-22/10/2021 in Aussois (Savoy-France).
 -  https://transcarto.github.io/rcartograms/TRANSCARTO_cartograms.html#les-algos-pour-les-cartogrammes-continus-avec-le-package-cartogramr <br> 

Didacticiels et scripts préparés à l'occasion de <a href="https://transcarto.sciencesconf.org/" target="_new" rel="noopener">l'École Thématique TRANSCARTO (Transformations cartographiques)</strong></a> 18-22/10/2021 à Aussois (Savoie).
-  https://transcarto.github.io/rcartograms/TRANSCARTO_cartograms.html#les-algos-pour-les-cartogrammes-continus-avec-le-package-cartogramr <br> 



</br> <strong>Animated cartograms / Cartogrammes animés</strong>

cartogramR can also be used to generate animated cartograms. See example below. 
 -  More info here: https://github.com/ESO-Rennes/Animated-Cartograms

<i>cartogramR</i> peut être utilisé également pour produire des cartogrammes animés. Voir l'exemple ci-dessous. 
 -  Plus d'info ici : https://github.com/ESO-Rennes/Animated-Cartograms


![](https://i.imgur.com/NJuz5ez.gif)


</br> <strong>References</strong>

Bertin J (1967). Sémiologie graphique: les diagrammes, les réseaux, les cartes. Mouton & Gauthier-Villars, Paris-La Haye.

Bertin J (1983). Semiology of graphics: diagrams, networks, maps. The University of Wisconsin Press, Madison, (trans. W. j. Berg). ISBN 0-299-09060-4.

Cauvin C, Escobar F, Serradj A (2007). Cartographie thématique 2 – Des transformations incontournables. Traité IGAT  – Information Géographique et Aménagement du Territoire ; Aspects fondamentaux de l’analyse spatiale. Hermès-Lavoisier.

Cauvin C, Escobar F, Serradj A (2010).  Cartography and the Impact of the Quantitative Revolution. John Wiley & Sons, Inc. https://onlinelibrary.wiley.com/doi/book/10.1002/9781118558126.

Demoraes F., Bouquet M., Mericskay B.,(2021) – How visually effective are animated cartograms? Potential improvements based on the example of segregation in Bogotá (1993-2005), M@ppemonde. DOI:10.4000/mappemonde.5928 - https://hal.archives-ouvertes.fr/hal-03152983 

Demoraes F., Bouquet M., Mericskay B.,(2021) – L’efficacité visuelle des cartogrammes animés en question - Une piste d’amélioration à travers l’exemple de la ségrégation à Bogotá (1993-2005), M@ppemonde. DOI:10.4000/mappemonde.5813 - https://hal.archives-ouvertes.fr/hal-03029241 

Dorling D (1996).  “Area Cartograms: Their  Use and Creation.”   In Concepts and Techniques in Modern Geography, 59. University of East Anglia: Environmental Publications, Norwich. ISBN I-872464-09-2. URL http://www.dannydorling.org/wp-content/files/dannydorling_publication_id1448.pdf.

Dougenik JA, Chrisman NR, Niemeyer DR (1985). “An  Algorithm  To Construct Continuous Area Cartograms.”   The Professional Geographer, 37(1), 75–81. https://onlinelibrary.wiley.com/doi/abs/10.1111/j.0033-0124.1985.00075.x

Gastner MT,  Newman MEJ  (2004).   “Diffusion-Based Method  for  Producing Density-Equalizing Maps.”  Proceedings of the National Academy of Sciences, 101(20), 7499–7504. https://doi.org/10.1073/pnas.0400280101

Gastner MT,  Seguy V, More P (2018). “Fast Flow-Based Algorithm  for Creating Density-Equalizing Map Projections.”  Proceedings of the National Academy of Sciences, 115(10), E2156–E2164. https://doi.org/10.1073/pnas.1712674115

Guseyn-Zade SM, Tikunov VS (1994). “Compilation of linear transformed images.” Mapping Sciences and Remote Sensing, 31(1), 34–48. doi:10.1080/07493878.1994.10641952.

House D, Kocmoud C (1998). “Continuous cartogram construction.”  In Proceedings Visual- ization ’98 (Cat. No.98CB36276), pp. 197–204. doi:10.1109/VISUAL.1998.745303.

Nusrat S, Kobourov S (2016). “The State of the Art  in Cartograms.”  Computer Graphics Forum, 35(3), 619–642. https://onlinelibrary.wiley.com/doi/abs/10.1111/cgf.12932

Olson JM (1976). “Noncontiguous Area Cartograms.”  The Professional Geographer, 28(4), 371–380. https://onlinelibrary.wiley.com/doi/abs/10.1111/j.0033-0124.1976.00371.x

Pebesma E (2018). “Simple Features for R: Standardized Support for Spatial Vector Data.” The R Journal, 10(1), 439–446. doi:10.32614/RJ-2018-009. https://journal.r-project.org/archive/2018/RJ-2018-009/index.html

Tennekes M (2018). “Tmap:  Thematic Maps in R.”  Journal of Statistical Software, 84(6). doi:10.18637/jss.v084.i06. https://www.jstatsoft.org/v84/i06/

Thomas H., Demoraes F. (2023). Uncovering urban circadian pulses based on an animated cartogram: the example of Bogotá. International Journal of Cartography, doi:10.1080/23729333.2023.2207333. https://hal.science/hal-04130267

Tobler W (2004). “Thirty Five Years of Computer Cartograms.”  Annals of the Association of American Geographers, 94(1), 58–73. https://onlinelibrary.wiley.com/doi/full/10.1111/j.1467-8306.2004.09401004.x

van Kreveld M, Speckmann B (2007). “On Rectangular Cartograms.”  Computational Geometry, 37(3), 175–187. https://doi.org/10.1016/j.comgeo.2006.06.002

