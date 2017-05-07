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
l'application doit s'intégrer au SSO de l'université jasig CAS

le package root:  ma.univh2c.reins
package des entités de la réins (mapping de la bd des reins) ma.univh2c.reins.dao.entites
package des entités de la BD oracle  pour la scolarité ma.univh2c.reins.dao.apogee.entites
package des JpaRepository pour la gestion des entités de reins  ma.univh2c.reins.dao.repos
package des JpaRepository pour la gestion des entités issus d'apogee  ma.univh2c.reins.dao.apogee.repos
package des classes métier ma.univh2c.reins.service et contient un package utils
package des classes web pour intégration au SSO et filtres/rôles  ma.univh2c.reins.web.filter 
package des classes pour les opérations Bash et traitements en masse ma.univh2c.reins.bash

pour l'intégration du SSO, des tutoriels montrenet l'ajout de Beans existant de la bibliothèque java-cas (qu'on va ajouté au fichier Pom du projet et update-maven), l'autre Bean qui permettera le filtrage par profil (étudiant master licence, personnel autorisé/non) le filtre doit être développé manuellement à base du login récupéré depuis le SSO et le filtre java-cas.

pour le déploiment, on a 3 instance de la VM ENT qui contient java et tomcat, on va tester les fichiers war existants de l'ENT et différents portlets installés sur le tomcat embarqué avec spring boot, si tout marche alors on déploit la solution en War en plus des war existants sur la nouvelle version de tomcat. Sinon on déploit la reins en Jar, et on lance dans la même instance en configurant le tomcat embarqué pour un environnment de production (validation de la charge par instance dans la phase de test par les outils adéquats JMeter...)

Pour la gestion des versions, on utilise Git et GitHub, on veillera à ne pas mettre des données sensibles étant donnée que l'accès gratuit impose que ce soit public, l'accès en privé coute 70DH/mois.
