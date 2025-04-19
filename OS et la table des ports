>You can use [Google Translate](https://translate.google.com/) to read them in your preferred language.


quand une machine reçoit des paquets à travers son NIC, ces paquets normalement ils sont dédiés à un processus qui tourne sur cette machine réceptrice, le paquet a été créé par le client du protocole en question dans le sending host, donc forcément le paquet sera destiné au serveur lié à ce protocole, c'est pour ça que le OS pour identifier quel processus il faut appeler, est-ce que httpd ou bien sshd... il utilise cette correspondance de port. Par exemple, un paquet rédigé par le client ssh sera traité par le serveur sshd dans l’autre machine réceptrice.

mais on sait que les paquets ça passe par plusieurs couches : application, transport, réseau, liaison de données, la couche physique. Puisque le client lié à un protocole s’en charge de la partie couche application, c’est-à-dire il réalise la requête associée à ce protocole (requête HTTP si le client est HTTP), le reste des informations provenant des autres couches, c’est-à-dire transport, réseau, liaison de données, physique, est géré par le OS, puisque dans son code source y a une partie qui traite les autres couches, c’est ce qu’on appelle la pile réseau.

