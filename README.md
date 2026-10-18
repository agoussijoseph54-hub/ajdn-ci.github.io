# PROJET-AJDN-S

## Comptes et profils (Supabase)

La page `#/connexion` propose la connexion, la création d’un profil et sa modification. Les mots de passe sont gérés par Supabase Auth et ne sont jamais enregistrés par le site. Les profils sont conservés dans `public.profiles`, avec des règles RLS qui limitent chaque membre à ses propres données.

L’activation réelle nécessite un projet Supabase et une mise en ligne du site :

1. Créer un projet sur Supabase.
2. Dans le SQL Editor du projet, exécuter le script [`supabase/profiles.sql`](./supabase/profiles.sql).
3. Dans les paramètres API du projet, copier l’URL du projet et la clé **anon/publicable** dans `window.AJDN_SUPABASE_CONFIG`, au début des scripts de [`index.html`](./index.html), respectivement dans `url` et `anonKey`.
4. Dans les paramètres Auth, activer l’inscription par courriel et définir l’URL du site et ses URL de redirection. En production, utiliser l’adresse HTTPS du site.
5. Publier le site sur un hébergement HTTPS et tester l’inscription, la confirmation du courriel, la connexion et la modification du profil.

Ne jamais mettre une clé `service_role` dans le site. Tant que l’URL et la clé publique ne sont pas renseignées, les formulaires restent désactivés et le site indique clairement que l’authentification n’est pas configurée. Le site ouvert directement en `file://` ne suffit pas pour tester le flux de confirmation par courriel.