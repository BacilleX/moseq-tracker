# MoSeq Tracker

Ce projet est né d'un besoin simple : faciliter le suivi de mes souris face à un test de comportement (le MoSeq).

### Pourquoi j'ai fait ça ?

Je voulais **suivre mes cohortes de souris** sans me prendre la tête.
- J'avais besoin de savoir qui était testé, à quel âge et combien il manquait d'animaux pour remplir le "n" qui était défini.
- J'en avais marre de recompter manuellement mes groupes.
- Je voulais que mes données soient accessibles partout (au labo, au bureau, chez moi), pas coincées sur un seul ordi.

### Comment j'ai fait ?

Pour résoudre ça, j'ai construit une petite application web à l'aide de l'IA Gemini 3 Pro (High):
1.  **Interface Simple** : J'ai fait une page unique (`index.html`) pour que ce soit léger.
2.  **Données** : J'ai utilisé **JSONBin.io** pour la base de données sous forme de fichier json : c'est gratuit et facile d'utilisation.
3.  **Sécurité** : Je ne voulais pas que n'importe qui modifie mes données, donc j'ai mis un système de **verrouillage par mot de passe**.
    - Tant que  le mot de passe n'est pas rentré, l'app est en "Lecture Seule".
    - La clé secrète liée à l'API pour modifier les données est chiffrée : le navigateur ne peut la lire que si le bon mot de passe est rentré.
4.  **Backups** : Comme je suis parano avec les données, j'ai ajouté un bouton **"Backup"** pour télécharger les données en un fichier JSON, et un bouton **"Restaurer"** au cas où.