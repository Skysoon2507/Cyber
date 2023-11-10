---


---

<h1 id="access-control">Access control</h1>
<h2 id="aaa-and-identification">AAA and identification</h2>
<h3 id="authentication">Authentication</h3>
<h3 id="autorisation">Autorisation</h3>
<ul>
<li>Chaque personne authentifié aura des <strong>rôles attribués et des droits</strong></li>
</ul>
<h3 id="accountability">Accountability</h3>
<ul>
<li>Journaliser les évenements si une cyberattaque survient plus tard</li>
<li>Peu courant dans les SI mais nécessaire pour être certifié par ISO…</li>
<li>Exemple : permet d’enquêter sur les accès effectués sur un fichier</li>
<li>Important de sécuriser ces journaux pour maintenir l’intégrité et la confidentialité</li>
</ul>
<h2 id="authentication-factors">Authentication Factors</h2>
<h3 id="types-">Types :</h3>
<ul>
<li>Type 1:
<ul>
<li>Quelque chose que l’on connait (mot de passe, PIN…)</li>
</ul>
</li>
<li>Type 2 :
<ul>
<li>Quelque chose que <strong>l’on a</strong> comme une clé USB, un token, un disque dur…</li>
</ul>
</li>
<li>Type 3 :
<ul>
<li>Quelque chose que <strong>l’on sait</strong> ou que <strong>l’on fait</strong> comme une caractéristique physique ou la biométrie</li>
</ul>
</li>
</ul>
<p>💡 Pour être considéré comme sécurisé, un système doit avoir au <strong>moins 2 facteurs d’authentification</strong><br>
▶️ <em>2 Factors autentication (2FA) ou Multiple Authentication Factors (MFA)</em></p>
<hr>
<h3 id="context-aware-auth">Context-Aware Auth</h3>
<ul>
<li>Mesure de sécurité basée sur la <strong>confiance des utilisateurs</strong></li>
<li>Exemple : <em>heure de connexion</em> au SI de son entreprise, la <em>localisation</em> de connexion</li>
<li><strong>Système + complexe</strong> à mettre en place et nécessaire d’analyser tt les actions</li>
</ul>
<h2 id="identity-and-authentication-management-iam">Identity and Authentication Management (IAM)</h2>
<ul>
<li>Système de contrôle <strong>centralisée</strong> ou <strong>décentraliser</strong></li>
</ul>
<h3 id="centralisé">Centralisé</h3>
<ul>
<li>
<p><strong>Single Sign-On :</strong>  une seule authentification pour plusieurs application</p>
<ul>
<li>Lors d’une connexion à une App, le contrôle d’ID est envoyer à un SSO système</li>
</ul>
</li>
<li>
<p><strong>Lightwaeight Directory Access Control (LDAP) :</strong> centralisé dans une BDD centralisée pour des <em>personnes</em> ou des <em>objets</em></p>
<ul>
<li>Plus connu : <em>Active directory</em></li>
<li><em>Kerberos protocol :</em> méthode d’auth utilisé par Microsoft AD. Solution SSO qui utilise le chiffrement symétrique (AES). C’est un vieux protocole</li>
</ul>
</li>
<li>
<p><strong>Kerberos :</strong></p>
<ul>
<li>Aucun mot de passe est échangé, c’est un challenge qui est échangé et basé sur notre mot de passe qui nous permet de déchiffrer la clé de session qui est envoyé par le serveur kerberos</li>
<li><em>Processus :</em>
<ol>
<li>Un client et un serveur kerberos. Le client s’identifie au serveur avec son le mdp de son compte LDAP.</li>
<li>Le serveur renvoie 2 messages que le client doit décrypter avec son mot de passe</li>
<li>Le client récupère une clé de session. Il envoie un paquet avec son nom au serveur de ticket (TGS) et le chiffre avec la clé de session temporaire</li>
</ol>
</li>
</ul>
</li>
</ul>
<hr>
<h3 id="non-centralisé">Non-centralisé</h3>
<ul>
<li><strong>802.1x : Auth in LAN/WLAN</strong>
<ul>
<li><strong>Supplicant :</strong> (voir cours) Par exemple, lorqu’on souhaite se connecter à un WIFI, la requête est envoyé à un switch qui transmet la requête à un serveur RADIUS qui traite la demande.</li>
</ul>
</li>
</ul>
<h2 id="need-to-know-and-least-privilege">Need-to-Know and Least Privilege</h2>
<ul>
<li>Limité les accès aux éléments auquelles les utilisateurs ont besoin seulement pour travailler par exemple</li>
</ul>
<h3 id="need-to-know">Need to know</h3>
<ul>
<li>Resteindre l’accès aux données seulement nécessaire</li>
<li>Réduire la perte de <strong>confidentialité</strong></li>
</ul>
<h3 id="the-least-privilege">The least privilege</h3>
<ul>
<li>MeP de permissions sur des données pour excécuter des tâches sur le SI. Donner le moins de privilege possible pour la bonne excution des tâches des utilisateurs. Le but étant de se rapprocher le plus du principe de <em>“Least privilege”</em></li>
</ul>
<h3 id="rbac-role-based-access-control">RBAC (Role-based Access Control)</h3>
<ul>
<li>Basé sur les foctions de chacun</li>
<li>Possibilité de créer des rôles pour chaque “job”</li>
<li>Le + utilisé</li>
</ul>
<h3 id="abac--attribute-based-access-control">ABAC ( Attribute-Based Access Control)</h3>
<ul>
<li>Même utilité que RBAC mais plus dynamique</li>
<li>Politiques de fonctionnement crées en fct des ressources et services</li>
<li>Facilité d’amélioration et de chgmt</li>
<li>Possibilités supplémentaires d’automatisation</li>
</ul>

