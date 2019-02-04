# TP4 - Spéléologie réseau : descente dans les couches

## I. Mise en place du lab :
### 1. Création des réseaux :
### 2. Création des VMs :
### 3. Mise en place du routage :

## II. Spéléologie réseau :
### 1. ARP :

#### A. Manip 1
##### 1 : 
Pour vider la table ARP, j'utilise la commande suivante :
sudo ip neigh flush all

##### 2 :
- Pour afficher la table ARP, j'utilise la commande suivante :
ip neigh show

- On obtiendra :
10.1.0.1 dev enp0s3 lladdr 0a:00:27:00:00:11 DELAY

- C'est la connexion entre putty et mon oridinateur.
##### 3 : 
- J'effectue la commande pour afficher la table ARP vue ci-dessus.
10.2.0.1 dev enp0s3 lladdr 0a:00:27:00:00:12 DELAY

- C'est la connexion entre putty et mon oridinateur.
##### 4 :
- J'effectue la commande : 
ping server1.tp4

- J'effectue la commande pour afficher la table ARP vue ci-dessus.
10.1.0.254 dev enp0s3 lladdr 08:00:27:16:c7:61 REACHABLE
10.1.0.1 dev enp0s3 lladdr 0a:00:27:00:00:11 REACHABLE

- 1ère ligne : C'est la connexion entre mon client et mon routeur.
- 2ème ligne : C'est la connexion entre putty et mon oridinateur.
##### 5 :
- J'effectue la commande pour afficher la table ARP vue ci-dessus.
10.2.0.1 dev enp0s3 lladdr 0a:00:27:00:00:12 DELAY
10.2.0.254 dev enp0s3 lladdr 08:00:27:1a:55:e9 STALE

- 1ère ligne : C'est la connexion entre putty et mon oridinateur.
- 2ème ligne : C'est la connexion entre mon client et mon routeur.
#### B. Manip 2
##### 1.
Pour vider la table ARP, j'utilise la commande suivante :
sudo ip neigh flush all

##### 2.
- Pour afficher la table ARP, j'utilise la commande suivante :
ip neigh show

- 10.1.0.1 dev enp0s3 lladdr 0a:00:27:00:00:12 DELAY

##### 3.
- J'effectue la commande : 
ping server1.tp4

- Après cela le client 1 ping le serveur 

##### 4.
- J'effectue la commande vue ci-dessus pour afficher la table ARP.
- Pour transmettre la requete ping de notre client elle passe d'abord par le routeur pour etre envoyer ensuite au serveur 

#### C. Manip 3
##### 1.
- Pour vider la table ARP sur mon PC, j'utilise la commande suivante :
arp -d

##### 2.
- Sur mon PC, j'effectue la commande suivante :
arp -a
 
- ![sparkles](./arp.PNG)

#### D. Manip 4
##### 1.
- Pour vider la table ARP, j'utilise la commande suivante :
sudo ip neigh flush all

##### 2.
- J'affiche la table ARP de client1.
- Pour activer la carte NAT :
    - J'éteind la machine client1
    - Dans configurations puis dans réseau, je crée une nouvelle carte en NAT.
    - Je rallum