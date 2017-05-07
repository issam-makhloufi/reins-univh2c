# reins-univh2c
app de reins pour univh2c
ReIns UnivH2c est une application web java/JEE qui permet d'automatiser au max les réins à l'université à savoir:
*- la gestion de la réinscription administrative, les dérogations.
$- automatiser la partie de gestion des assurrances.

les technologies utilisés pour le moment:
Eclipse avec le plugin Spring tool suite.
spring boot.
jpa implémenté par hibernate.
mysql pour la bd de la reins et le résumé pédago des étudiants.
oracle d'où lire le résumé pédago des étudiants et la structure des enseignements.

pour la partie présentation, il y a le choix de html5, angular Js, Rest et MVC coté client.
l'application doit s'intégrer au SSO de l'université jasig CAS 3.5

le package root:  ma.univh2c.reins
package des entités de la réins (mapping de la bd des reins) ma.univh2c.reins.dao.entites
package des entités de la BD oracle  pour la scolarité ma.univh2c.reins.dao.apogee.entites
package des JpaRepository pour la gestion des entités de reins  ma.univh2c.reins.dao.repos
package des JpaRepository pour la gestion des entités issus d'apogee  ma.univh2c.reins.dao.apogee.repos
package des classes métier ma.univh2c.reins.service et contient un package utils

