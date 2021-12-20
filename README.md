
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
1- Objectifs de ce TP:
**
  - Implémenter un sniffer passif simple
- Manipuler des logiciels de sniffing
2- Outils logiciels:
**
  Linux, wireshark, compilateur cc ou gcc
  
3- Informations utiles :
**
 - Les cartes réseau fonctionnent en deux modes
o mode normal (mode par défaut) : permet à une carte de filtrer les trames reçus
en fonction de l'adresse MAC destination
o mode promiscuous : consiste à accepter toutes les trames circulant dans un
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
4- Partie 1 :Implémentation d’un sniffer passif
L'annexe 1 présente le code source d’un sniffer passif qui permet de récupérer les trames reçues par
une interface réseau (exemple ETHERNET). Ce code source est écrit en langage C et peut être
compilé et exécuté sur une machine Linux. Les fonctions les plus importantes de ce code sont (voir
contenu de lafonction main):
- La fonction recvfrom qui permet de récupérer les trames reçues sur l’interface réseau.
- La fonction PrintPacketInHex qui permet d’afficher la trame sous format hexadécimal
- La fonction ParseEthernetHeader qui permet d’afficher quelques champs de l’entête ETHRNET
- La fonction ParseIpHeader qui permet d’afficher quelques champs de l’entête IP
- La fonction ParseTcpHeader qui permet d’afficher quelques champs de l’entête TCP
- La fonction ParseData qui permet d’afficher les données sous format hexadécimal



