####### infrastructure-creation-in-aws ##############

Ce script permet de créer les ressources suivantes :

Une instance EC2 pour le serveur WordPress, lancée dans un sous-réseau public, associée à un groupe de sécurité pour ouvrir le port 80 et lancée avec une commande Docker pour exécuter le serveur WordPress.
Un groupe Auto Scaling pour les instances EC2 du serveur WordPress, configuré pour surveiller la charge CPU et lancer des instances supplémentaires si la charge dépasse 80% en moyenne sur 5 minutes.
Une instance EC2 pour le serveur VPN, lancée dans un sous-réseau public et associée à un groupe de sécurité pour ouvrir les ports nécessaires pour la liaison VPN.
Un ensemble de ressources pour configurer la liaison VPN entre le serveur VPN et le sous-réseau privé AWS, comprenant un Customer Gateway, un Virtual Private Gateway, une connexion VPN et une route pour le trafic du sous-réseau privé.
Une sortie pour l'URL du serveur WordPress et l'adresse IP publique du serveur VPN.

####################################################
