# E-ReportDT

**Report automatique des réponses de DT/DICT dans QGIS.**
E-ReportDT lit les réponses des exploitants (plans PDF, fichiers StaR-DT) et en fait un seul plan des réseaux : couches SIG, DXF, DWG et plan PDF.

> **E-ReportDT est un outil d'aide à la vectorisation et à la compréhension globale des réseaux. Ce document est dérivé des réponses des exploitants : il peut contenir des erreurs ou des oublis (calage, réseau non reporté, classe ou type mal attribué). Seuls les plans des réponses aux DT/DICT des exploitants font foi, notamment pour les terrassements. Il ne remplace ni la lecture de ces réponses, ni les investigations complémentaires, ni le marquage-piquetage.**

**État du projet : bêta fermée.** L'outil est essayé par un petit groupe de bêta-testeurs avant d'être ouvert à tous.

- 🙋 **[Devenir bêta-testeur](#devenir-bêta-testeur)**
- 🧭 [Comment ça fonctionne, en schémas](docs/FONCTIONNEMENT.md)
- 🗂️ [Exploitants pris en charge](EXPLOITANTS.md)
- 📈 [Nouveautés : ce qui fonctionne, ce qui reste à aboutir](NOUVEAUTES.md)

## Démonstration en vidéo (5 minutes)

https://github.com/user-attachments/assets/97bd2d49-0f59-498d-b7c8-cd19ed88630b

## Pourquoi cet outil

Sur un chantier de terrassement, la sécurité commence par savoir où passent les réseaux. E-ReportDT y contribue de deux façons :

- **un report précis** des réponses de DT/DICT, directement utilisable dans les logiciels de DAO (DXF, DWG, GeoPackage) ;
- **une vue d'ensemble**, grâce à un plan de synthèse en PDF qui réunit tous les réseaux.

Ce travail se fait encore souvent à la main, car beaucoup d'exploitants répondent par des plans en image, et chacun dessine à sa façon : son style de plan, sa charte graphique, son fond de plan. E-ReportDT lit chaque exploitant selon sa propre charte.

## Pour qui

- les bureaux d'études ;
- les chargés d'affaires ;
- les maîtres d'ouvrage ;
- les exploitants de réseaux ;
- les entreprises de travaux publics ;
- les opérateurs, encadrants et concepteurs AIPR ;
- toute personne qui prépare des travaux à proximité de réseaux.

## Comment ça fonctionne

L'outil est écrit en Python. Il reconnaît les textes et les objets des plans en s'appuyant sur un gabarit par exploitant : un fichier qui décrit sa charte. Le traitement suit six étapes.

1. **Reconnaissance de l'exploitant.** Le zip du guichet unique, un dossier ou des fichiers séparés : chaque fichier est rattaché à son exploitant d'après son contenu (récépissé, nom écrit sur le plan, modèle de plan).
2. **Calage des plans.** D'abord sur ce que le plan porte (coordonnées, carroyage, points levés), puis sur le cadastre et l'orthophoto publics. La qualité du calage dépend de la solidité des données fournies par l'exploitant.
3. **Vectorisation des réseaux.** Le gabarit de l'exploitant dit quel trait est quel réseau : l'outil trace les réseaux par exploitant et par classe de précision (A, B, C), avec les affleurants, et lit les textes.
4. **Résultats.** Un rapport dit, plan par plan, la précision du calage, ce qui est reporté, ce qui est à vérifier et ce qui reste à faire à la main.
5. **Retouche à la main, si besoin.** Calage à la main d'un plan non calé, dessin des réseaux (tracé libre, tracé qui suit la couleur du trait, recherche de tous les traits d'une même couleur), correction du report : supprimer un trait, changer son réseau ou sa classe, déplacer ses sommets.
6. **Livrables.** Pour la DAO et le SIG : DXF, DWG, GeoPackage. Les orthophotos à 5 cm des plans Enedis et GRDF, calées. Un plan de synthèse des réseaux en PDF, sur la zone de votre choix.

Un exploitant sans gabarit est signalé « non pris en charge » : rien n'est deviné. Son plan peut être calé et dessiné à la main. Les plans scannés ne sont pas lus.

## Vos plans restent sur votre poste

Tout le traitement se fait sur votre ordinateur. L'outil ne transmet ni plan ni statistique. Il télécharge seulement le cadastre et l'orthophoto publics de la zone (services de l'État) ; cette option se désactive.

Rien ne part vers l'auteur sans vous : le bouton « Participer à l'amélioration… » prépare un message dans votre messagerie, et c'est vous qui l'envoyez.

## Ce qui fonctionne, ce qui reste à aboutir

**Fonctionne :** la reconnaissance des exploitants, le calage des plans des exploitants pris en charge, le report automatique de leurs réseaux, les livrables (GeoPackage, DXF, DWG, orthophotos, rapport) et le plan de synthèse en PDF.

**À aboutir, avec vos retours :** les outils de calage et de dessin à la main, les aides au dessin par couleur et par la légende, le traitement des exploitants sans gabarit, et le nombre d'exploitants pris en charge.

## Devenir bêta-testeur

Vous préparez des travaux à proximité de réseaux et vous utilisez QGIS sous Windows (version 3.40 ou plus récente) ? Écrivez à **ereportdt@gmail.com** en indiquant :

- votre métier et votre structure ;
- les exploitants que vous rencontrez le plus souvent dans vos DT/DICT ;
- votre version de QGIS.

Vous recevrez par e-mail le lien d'installation et une courte notice. En retour, il vous sera demandé d'essayer l'outil sur vos propres DT/DICT et de répondre à un questionnaire. N'envoyez aucun plan de réseaux par ce premier message.

## Limites à connaître

- La précision du report dépend du calage de chaque plan ; elle est écrite dans le rapport. Un plan « à vérifier » doit être comparé au plan original.
- Sans orthophoto à 5 cm de la zone, le calage ne peut pas être contrôlé finement.
- Les exploitants changent leurs modèles de plan : un nouveau modèle reste « non pris en charge » jusqu'à ce que l'auteur crée son gabarit.

## Licence

E-ReportDT est distribué aux bêta-testeurs sous la licence [GNU General Public License, version 3 ou ultérieure](LICENSE) (GPL-3.0-or-later). Il est fourni sans aucune garantie. Le dépôt du code n'est pas encore ouvert.

Le symbole de l'outil reste la propriété de l'auteur et n'est pas couvert par cette licence : voir [MARQUE.md](MARQUE.md).

## Auteur

Julien Colin
