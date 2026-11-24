# Nouveautés

## Version 0.5.0 — première version (bêta)

### Ce qui fonctionne

- Fonctionne — Reconnaissance des exploitants d'une DT/DICT (zip du guichet, dossier ou fichiers) d'après le contenu des réponses.
- Fonctionne — Calage des plans des exploitants pris en charge, avec la précision écrite au rapport ; un plan douteux est dit « à vérifier ».
- Fonctionne — Report automatique des réseaux des exploitants qui ont un gabarit, par classe A, B, C et aérien, avec les affleurants et les textes.
- Fonctionne — Livrables : GeoPackage, DXF, DWG, orthophotos 5 cm des plans Enedis et GRDF calées, rapport de traitement.
- Fonctionne — Plan de synthèse des réseaux en PDF : page de garde, folios A3 sur la zone de votre choix, légende.

### À aboutir : à essayer, vos retours comptent

- À aboutir — Outils manuels : « Caler et dessiner… », « Compléter la vectorisation… » et « Retoucher sur la carte… ». Ils sont récents : vérifiez chaque résultat sur le plan original.
- À aboutir — Aides au dessin : « Tracé auto par couleur », « Proposer tous les traits de couleur » (avec la légende du plan) et « Textes par couleur ». Ce sont des propositions : il peut manquer des traits, et certains ne sont pas des réseaux.
- À aboutir — Exploitant sans gabarit : rien n'est reporté automatiquement ; son plan se cale et se dessine à la main, une revue des couleurs est préparée pour vous aider.
- À aboutir — Peu d'exploitants ont un gabarit pour l'instant : proposez les vôtres par « Proposer cet exploitant ».
- À aboutir — Plans scannés : non lus. Sans orthophoto à 5 cm de la zone, le calage ne peut pas être contrôlé finement.

## Détail des fonctions

- Revue des couleurs préparée : elle s'ouvre directement, même sur une page non calée ; vos choix sont gardés, et les traits gardés ne sont dessinés qu'après la validation du calage.
- Exploitant sans gabarit : pour ses pages de plan en image, le traitement prépare la revue des couleurs (groupes de couleur et légende) ; le rapport dit « réseaux à vérifier ». Rien n'est reporté sans vous.
- Bloc « Corriger le report » au-dessus du rapport d'exécution : « Retoucher sur la carte… » et « Compléter la vectorisation… » de l'exploitant choisi, sans défiler le tableau.
- Fenêtre de dessin et retouche sur la carte : une seule liste « Calque », avec les calques que le moteur sort pour l'exploitant (nommés comme dans le DXF, aperçu du trait) : d'abord ceux de la DT, puis les autres réseaux du gabarit de l'exploitant (mention « autre réseau du gabarit », en gris), lus dans le dossier des gabarits de l'étape « Sources ».
- Boutons d'amélioration de l'outil (participer, signaler, proposer) en bleu, distincts des boutons d'action.
- Rapport d'exécution : la ligne d'un exploitant calé ou dessiné à la main le dit dès l'enregistrement, sans relancer le traitement (« dessiné à la main — moteur : non reporté », calage, tronçons et plan à la main) ; le rapport PDF et la page de garde du plan de synthèse aussi.
- « Retoucher sur la carte… » marche aussi sur les traits que vous avez dessinés (tracé libre, assisté, auto par couleur, revue des couleurs) : calque, d'où à d'où, revue des non lus, rétablir, retour arrière.
- « Proposer tous les traits de couleur » lit la légende du plan : libellé, couleur et motif du trait (continu, tirets, double) proposés pour chaque groupe, groupes de même couleur séparés par motif, discordance signalée ; le réseau et la classe restent à votre choix.
- « Proposer tous les traits de couleur » : tous les traits de couleur de la page, regroupés par couleur ; vous les passez en revue un groupe à la fois et nommez chacun (réseau, classe) ou l'écartez. Vos choix sont proposés sur les autres pages du même exploitant.
- Plan de synthèse des réseaux : une page de garde (commune et adresse des travaux, exploitants présents, plans de DICT qui font foi, situation du chantier dans la commune, assemblage des folios, légende générale du plan), à décocher si besoin ; le rapport de traitement n'est plus dans le plan PDF (livré à part).
- Tampons d'eaux usées, d'eaux pluviales et unitaires : petit rond noir à fond marron transparent, partout.
- Fond du plan PDF « Orthophoto IGN + PCRS Enedis / GRDF calés » : les orthophotos 5 cm des plans calés sur l'orthophoto de la zone.
- Fenêtre de dessin : « Enregistrer et envoyer sur le plan général » montre aussitôt vos traits, affleurants, textes et corrections dans la carte de QGIS, dans le calque de leur réseau et de leur classe, comme dans le DXF.
- « Retoucher sur la carte… » (bouton au marteau, au-dessus du rapport d'exécution) : la carte suit aussitôt, le tronçon retouché passe dans le calque de son réseau et de sa classe.
- « Textes par couleur » : un clic sur une lettre d'un texte du plan, et les textes de la même couleur sont lus (sur votre poste) et proposés encadrés ; vous les corrigez, en écartez, puis les gardez comme textes de l'exploitant.
- « Retour arrière » annule la dernière action dans la fenêtre de dessin.
- « Retoucher sur la carte… » : donnez un réseau et une classe aux traits non lus, un par un (passage en revue) ou par clic, ou à une portion d'un trait seulement.
- Fenêtre de dessin : le report du traitement toujours visible (case pour le masquer), « Supprimer au clic » et « Modifier les sommets ».
- « Tracé auto par couleur » : un clic sur un trait du plan, et tous les traits de la même couleur sur la page sont proposés en surbrillance ; vous les vérifiez, en écartez, réglez la tolérance, puis les gardez au réseau et à la classe choisis.
- « Compléter la vectorisation de la DT… » : sur un plan reporté, voyez le report du moteur sur le plan calé, ajoutez des traits, supprimez ou corrigez ceux du moteur, déclarez une page vérifiée ; les livrables suivent vos corrections.
- « Participer à l'amélioration… » : un seul bouton, à côté de « Ouvrir le dossier », pour envoyer en un seul message vos résultats, vos DT et vos corrections (avec les seules pages concernées du plan) ; vous envoyez vous-même.
- Plan PDF sur une zone : « Dessiner la zone à imprimer… », les folios couvrent la zone dessinée sur la carte.
- Plans calés dans la carte : niveau « PCRS » (orthophoto 5 cm d'Enedis et de GRDF) et niveau « Plan » (page du plan) séparés.
- « Caler et dessiner… » : calez vous-même un plan sur l'orthophoto, le cadastre, OpenStreetMap ou les plans déjà calés, puis dessinez les réseaux à la main (tracé libre ou qui suit la couleur du trait).
- « Proposer cet exploitant » et « Signaler un défaut de report » : une courte fiche, envoyée avec ou sans les plans.
- Gabarits rangés par exploitant : la mise à jour dit quels exploitants ont été ajoutés ou mis à jour.
- Plan d'un exploitant sans gabarit, au modèle d'un prestataire connu : calé, réseaux à reporter (gabarit à créer).
- Tout en un : le moteur de calcul est livré avec l'extension, rien d'autre à installer.
- Gabarits mis à jour par un bouton, sans réinstaller l'extension ; leur version est dans le rapport.
- Colonne « Gabarit » : choisissez le gabarit d'un exploitant non reconnu ; le choix est dit au rapport.
- Trois onglets : Présentation, Import, Livrable.
- Onglet Livrable : avancement, puis une ligne par exploitant (état, calage, tronçons).
- Livrables complémentaires à cocher : DXF, DWG, orthophoto des plans, plan PDF.
- Le traitement ne fait plus de DXF : cochez la case DXF des livrables complémentaires.
- « Poste électrique » écrit dans le rectangle des postes (carte, DXF, plan PDF).
- Plan PDF : vue « réseaux et affleurants » ou vue complète avec les caractéristiques.
- Orthophoto des plans : l'image aérienne des plans Enedis et GRDF, en GeoTIFF.
- Calques du DXF et du DWG préfixés « ERDT_ ».
- Téléchargement automatique du cadastre et de l'orthophoto de la zone.
- Exploitant non pris en charge : demande de gabarit préparée pour l'auteur en un clic.
- Tout est livré en Lambert 93.
