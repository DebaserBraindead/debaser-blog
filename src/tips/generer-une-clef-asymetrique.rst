Générer une clef asymétrique
############################

:date: 2012-07-22 22:38
:tags: cypherpunk, cryptographie, tips
:author: Debaser
:slug: generer-une-clef-asymetrique
:lang: fr

J'ai constaté que j'avais de la peine à retrouver la bonne commande
pour génerer rapidement une clef asymétrique et un certificat associé, malgré
la documentation de openssl_.

Voilà donc la solution :

.. code-block:: sh

    openssl req -new -newkey rsa:2048 -x509 -nodes -out nginx.pem -keyout nginx.key

- **-newkey rsa:2048 :** Clef rsa de 2048 bits (attention à la légisalation en vigueur ;) )
- **-x509 :** pour indiquer la génération du certificat.
- **-out et -keyout :** Indiquent les fichiers de sortis pour la clef et le certificat.

Je vous épargne les détails liés à la pure configuration du server http, c'est assez trivial que ce soit avec `nginx <http://wiki.nginx.org/HttpSslModule>`_, `apache <http://onlamp.com/onlamp/2008/03/04/step-by-step-configuring-ssl-under-apache.html>`_, `node.js <http://nodejs.org/docs/v0.3.7/api/https.html#https.createServer>`_ et plus encore.

PS: Cette article marque donc aussi l'ouverture de l'accès à ce blog en https, mettez à jour vos bookmarks!

.. _openssl: http://www.openssl.org/
