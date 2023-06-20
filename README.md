Tout d'abord, nous avons cloné le projet et rajouté la bdd.
Afin de pouvoir accéder à la partie admin de l'application il a fallu rajouter un mot de passe crypté dans la table admin de la bdd.
Une fois cela fait, nous avons installé php mailer ainsi que php stan sur le projet.
Php stan nous a permis d'analyser notre code.
Nous avons créé un fichier phpstan.neon afin d'exclure les dossiers non voulus et définir le niveau d'erreur que phpstan doit analyser dans le code.

Une fois le fichier créée, nous avons pu analyser le code à l'aide de phpstan et ainsi corriger les différentes erreurs qui nous étaient remontées.


Pour le plan de test, nous avons dégroupé cela en deux, la partie admin et la partie user.

Le plan de test était de faire un chemin qui se suit du fait que l'on avait vu comment l'application fonctionnait.

En premier lieu le chemin le plus facile et logique était d'arriver sur l'application, de créer un compte utilisateur, ensuite de se connecter en tant qu'administrateur et de refuser l'inscription de l'utilisateur et se déconnecter. A la suite de cela, on imagine un autre scénario ou l'utilisateur serait approuvé par l'administrateur. Une fois cela fait, l'utilisateur se connecte et arrive sur sa page, il réinitialise son mot de passe et se reconnecte pour vérifier que tout fonctionne puis se déconnecte manuellement. Enfin, il se reconnecte pour aller voter. Ensuite c'est la partie administrateur. L'administrateur vérifie les différentes actions qui lui sont disponibles dans le menu candidate details qui sont la vue, l'édition, la création et la suppression de candidats.

Pour les Tests Fonctionnels il faut suivre les fichiers suivants :
    ->TestVotingRegister
    ->TestVotingDisapprove
    ->TestVotingRegister
    ->TestVotingApprove
    ->TestVotingUserConnect
    ->TestVotingAdmin