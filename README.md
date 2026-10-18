# PROJET-AJDN-S

## Espace membre

La connexion et la création de profil sont temporairement retirées de l’interface du site. Le script [`supabase/profiles.sql`](./supabase/profiles.sql) est conservé comme préparation technique, mais aucun service de compte n’est actuellement activé.

Pour rétablir cette fonctionnalité, il faudra d’abord créer et configurer un projet Supabase, puis réintégrer l’authentification dans le site et le publier en HTTPS. Ne jamais exposer une clé `service_role` dans le code public.