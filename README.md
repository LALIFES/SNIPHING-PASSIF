
![Cyberattaque-Cybersécurité-crédit-Blogtrepreneur-Flickr-Cc](https://user-images.githubusercontent.com/96391221/146798070-e4675a75-284d-4119-94ae-1e3c3b66092b.jpg)

# SNIPHING-PASSIF
***
## INTRODUCTION

Les sniffers (appelé aussi «analyseurs de protocoles » ou « analyseurs de réseau ») sont desoutils logiciels qui peuvent capturer les trames circulant sur un réseau local et afficher leurscontenus (entêtes des protocoles, identités des utilisateurs, mot de passe non cryptés, etc). Cesoutils   sont   utilisés   par   les   administrateurs   pour   analyser   leurs   réseaux   et   localiser   lesproblèmes dans ces derniers. Ils sont aussi utilisés par les attaquants pour espionner lesdonnées circulant dans un réseau local.

Le tableau 1 présente une comparaison de quelques sniffers (GUI : graphical User Interface,
CLI : Command Line Interface)
***
![image](https://user-images.githubusercontent.com/96391221/146802720-f233c4ab-9d1b-422f-9e87-8d889f4a9f35.png)
****
# Objectifs de ce TP:
  - Implémenter un sniffer passif simple
  - Manipuler des logiciels de sniffing
# Outils et logiciels:
  - Linux, wireshark, compilateur cc ou gcc
# Informations utiles :
  - Les cartes réseau fonctionnent en deux modes
   o mode normal (mode par défaut) : permet à une carte de filtrer les trames reçus
   en fonction de l'adresse MAC destination o mode promiscuous : consiste à accepter toutes les trames circulant dans un
   réseau, même ceux qui ne sont pas destinés à la carte.
 - Sous Unix, la commande # ifconfig promisc permet d’activer le mode promiscuous.
 - La plupart des logiciels sniffers permettent d’activer le mode promoscuous lors de
   leur lancement.
 - Dans un réseau commuté, le sniffing passif de toutes les trames qui circulent dans le réseau
   est impossible àréaliser puisqu'un nœud ne peut recevoir que les trames qui lui sont
   destinées.
 - Le sniffing actif (qui sera traité au niveau du TP2) permet de faire du sniffing sur un
   réseau même s'il est commuté.
 - Le sniffer doit être sur le même réseau à sniffer. Sinon, il doit faire du « remote sniffing »
   en contrôlant à distance une machine qui se trouve sur le réseau à sniffer.
# Partie 1 : # Implémentation d’un sniffer passif
 L'annexe 1 présente le code source d’un sniffer passif qui permet de récupérer les trames reçu par une
interface réseau (exemple ETHERNET). Ce code source est écrit en langage C et peut être compilé et
exécuté sur une machine Linux. Les fonctions les plus importantes de ce code sont (voir contenu de la
fonction main):
 - La fonction recvfrom qui permet de récupérer les trames reçues sur l’interface réseau.
 - La fonction PrintPacketInHex qui permet d’afficher la trame sous format hexadécimal
 - La fonction ParseEthernetHeader qui permet d’afficher quelques champs de l’entête ETHRNET
 - La fonction ParseIpHeader qui permet d’afficher quelques champs de l’entête IP
 - La fonction ParseTcpHeader qui permet d’afficher quelques champs de l’entête TCP
 - La fonction ParseData qui permet d’afficher les données sous format hexadécimal
## Manipulations a faire (sous LINUX)
  1) Compiler (cc -c sniffer_eth_ip_tcp_data.c) le code source et générer l’exécutable (cc
     sniffer_eth_ip_tcp_data.c – o sniffer).
  
  ![image](https://user-images.githubusercontent.com/96391221/146825323-a1453193-fd50-443e-9fea-e56bc5a4e151.png)
  ![image](https://user-images.githubusercontent.com/96391221/146825671-6545b60f-d53c-408d-8276-744dfb29b5ea.png)

  ****
  2) Exécuter (en mode root : « sudo commande » sous ubuntu) le sniffer (exemple : pour sniffer
     les 100 premières trames reçu sur l’interface eth0 tapez ./sniffer eth0 100). Vous pouvez
     utiliser wlan0 à la place de eth0 si vous êtes connecté en sans fil (les trames Wifi sont
     traduites en ETHERNET) ou lo (loopback) si vous n'avez aucune
     connexion. Si rien ne s’affiche, cela veut dire que vous n’êtes pas en train de recevoir des
     paquets, exécuter alors (dans une nouvelle fenêtre) un ping vers une autre machine et
     consulter de nouveau le résultat du sniffer.
     ![image](https://user-images.githubusercontent.com/96391221/146825796-9db7ed5b-e746-4ca5-ae16-f854eb1de4cd.png)
***
3) Dans la manipulation précédente, les trames sont affichées sous format hexadécimal. Pour
   afficher le contenu de l’entête ETHERNET, il faut enlever le commentaire de la fonction
   ParseEthernetHeader, recompiler, régénérer l’exécutable et refaire l’étape 2).
4) Pour Afficher le contenu des entêtes des protocoles des niveaux supérieurs, enlevez les
   commentaires des fonctions correspondantes (au niveau de la fonction main), recompiler,
   régénérer l’exécutable et exécuter de nouveau le sniffer. Pensez à faire un échange de trafic
   TCP (en utilisant par exemple le serveur vsftpd ou en se connectant à Internet).  
   ``` Etape1```
![image](https://user-images.githubusercontent.com/96391221/146826258-16041179-e4a2-4ecd-9526-df68e21708d6.png)

   ```Etape2```
   ![image](https://user-images.githubusercontent.com/96391221/146837556-eeb13d23-f750-474f-92c9-31cdf54ac7ca.png)

   
     






