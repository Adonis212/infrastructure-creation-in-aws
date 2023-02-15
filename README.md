# OC Projet 10 maîtriser votre infrastructure Cloud

Ce script permet de créer les ressources pour répondre au projet 10 de création d'infrastructure dans le cloud

## Scénario 

Vous travaillez dans une petite entreprise qui se développe à l'international. L'entreprise ne dispose que de quelques machines pour la gestion de ses outils internes et pour héberger son site internet. Des incidents matériels sur le serveur de messagerie ont pénalisé l'entreprise le mois dernier. Le directeur veut éviter que la situation ne se reproduise mais réalise que fiabiliser les services en interne coûterait très cher.

L'entreprise décide donc de migrer l’ensemble de son SI vers le cloud. Les outils collaboratifs seront migrés vers Google Apps et le site de l’entreprise sera hébergé sur AWS.

L’entreprise garde simplement un serveur de fichiers dans ses locaux pour profiter de la vitesse du réseau local pour le transfert de fichiers volumineux. Ce serveur est également accessible par une liaison VPN depuis un site intranet privé hébergé sur AWS.

## Instructions 

Installez un serveur WordPress (le site de l’entreprise) sur AWS en utilisant :
RDS pour le stockage de la base de données
S3 pour le stockage des médias (via le plugin amazon-web-services)
EC2 et Docker pour le serveur web
ELB pour distribuer les requêtes sur les instances EC2
CloudFormation pour automatiser la création de l’infrastructure
Tous les éléments de votre infrastructure publique devront être répartis sur plusieurs zones de disponibilité (multi-AZ). Vous utiliserez le service ELB pour la répartition des requêtes vers les différentes zones de disponibilité (AZ).
Vous monterez une instance EC2 destinée à héberger l’application intranet sur un sous-réseau privé. Dans le cadre de ce cours, le contenu de l’intranet sera une simple page web HTML.

En local sur votre machine, vous créerez deux machines virtuelles Linux : une pour le serveur de fichiers et une pour le serveur VPN.
Vous établirez une liaison VPN entre votre serveur VPN local et le sous-réseau privé AWS via une instance EC2.
Vous mettrez en place de l’auto-scaling sur les instances EC2 pour augmenter le nombre de machines dès que la charge CPU des serveurs atteint 80% en moyenne sur 5 minutes et vous veillerez à être informé par un mail à chaque fois que l'événement survient.
Vous évaluerez les coûts de votre infrastructure AWS à partir de différentes hypothèses d'usage que vous formulerez.

Une instance EC2 pour le serveur WordPress, lancée dans un sous-réseau public, associée à un groupe de sécurité pour ouvrir le port 80 et lancée avec une commande Docker pour exécuter le serveur WordPress.
Un groupe Auto Scaling pour les instances EC2 du serveur WordPress, configuré pour surveiller la charge CPU et lancer des instances supplémentaires si la charge dépasse 80% en moyenne sur 5 minutes.
Une instance EC2 pour le serveur VPN, lancée dans un sous-réseau public et associée à un groupe de sécurité pour ouvrir les ports nécessaires pour la liaison VPN.

Un ensemble de ressources pour configurer la liaison VPN entre le serveur VPN et le sous-réseau privé AWS, comprenant un Customer Gateway, un Virtual Private Gateway, une connexion VPN et une route pour le trafic du sous-réseau privé.
Une sortie pour l'URL du serveur WordPress et l'adresse IP publique du serveur VPN.
