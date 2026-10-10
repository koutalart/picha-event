# PICHA Event — Cahier des charges MVP

## Vision
Plateforme SaaS multi-organisateurs pour piloter plusieurs événements. Chaque organisateur dispose d'un espace privé, de ses équipes et de ses documents. Tropikal Xmas 2026 est le pilote, sans règles métier codées en dur.

## Utilisateurs et permissions
- Administrateur plateforme PICHA : gestion de la plateforme, sans accès implicite au contenu privé des organisateurs.
- Propriétaire organisateur : paramètres et membres de son organisation.
- Administrateur organisateur : gestion des événements et invitations autorisées.
- Responsable événement : gestion de son événement, des équipes, missions et prestataires.
- Membre : accès aux événements et missions autorisés.
- Prestataire invité : accès limité à ses propres missions et documents explicitement partagés.
Un utilisateur peut appartenir à plusieurs organisations. Chaque requête et chaque fichier doivent être autorisés côté serveur, avec organisation_id et événement_id contrôlés. Refuser par défaut.

## MVP
1. Authentification sécurisée, invitation par email, changement d'organisation, déconnexion.
2. Organisations : création, membres, invitations, rôles.
3. Événements : création, dates, lieu, description, état, équipe et pôles.
4. Missions : titre, description, responsable, échéance, priorité, statut (à faire, en cours, à valider, terminé), checklist, commentaires, pièces jointes, historique et validation.
5. Vues liste, Kanban, calendrier des échéances, « Mes missions ».
6. Prestataires : contact, type de prestation, engagement attendu, dates, présence confirmée, documents, incidents, compte rendu et remontée au coordinateur.
7. Documents privés : stockage objet S3 compatible, URL signée de courte durée, validation taille/type, autorisations.
8. Notifications dans l'application et emails transactionnels via Resend.
9. Tableau de bord événement : retards, missions en attente de validation, prestataires à confirmer.

## Exemple pilote — Tropikal Xmas
Brayan : direction et billetterie. Aska : coordination générale, administration, finances, sécurité et bar/restauration avec Chenilla. Hafez : logistique, contrôle de présence et réalisation des prestations, remontées à Aska. Josué : communication et presse. Innocent : programmation artistique. Chenilla : artistes/VIP et bar/restauration avec Aska. Ces personnes sont des données d'exemple, jamais des rôles applicatifs figés.

## Hors périmètre V1
Paiement et billetterie, budgets comptables détaillés, CRM, IA, application mobile native, synchronisation PICHA Ticket/Scan, facturation SaaS, portail public d'événement.

## Critères d'acceptation
- Un membre de l'organisation A ne peut lire/modifier aucun contenu de B, y compris par ID deviné, téléchargement ou API.
- Une personne invitée à A et B peut basculer d'espace sans fuite de données.
- Une mission a un responsable, une date, des commentaires, des documents et un historique de validation.
- Un prestataire peut être marqué présent/absent, sa mission contrôlée, et un incident remonté au coordinateur.
- Responsive sur téléphone et ordinateur; interface française, accessible et sobre.
- Tests automatiques des permissions, de l'isolation des fichiers et des principales actions.
- Sauvegardes, migrations, logs sans secrets, configuration via variables d'environnement.
