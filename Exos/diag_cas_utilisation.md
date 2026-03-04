# Cas : Système de gestion d’une commande en ligne

## Contexte
Une entreprise de e-commerce souhaite modéliser les interactions entre les acteurs et le système lors du traitement d’une commande.

---

## Acteurs

- Client
- Système de paiement (acteur externe)
- Service de livraison (acteur externe)
- Administrateur

---

## Cas d’utilisation principaux

### Côté Client
- S’inscrire
- Se connecter
- Consulter les produits
- Ajouter un produit au panier
- Modifier le panier
- Valider le panier
- Choisir un mode de livraison
- Effectuer le paiement
- Consulter l’historique des commandes

### Côté Administrateur
- Gérer les produits
- Mettre à jour le stock
- Consulter les commandes

---

## Relations entre cas d’utilisation

- "Valider le panier" <<include>> "Vérifier disponibilité"
- "Effectuer le paiement" <<include>> "Vérifier paiement"
- "Effectuer le paiement" <<extend>> "Réessayer paiement"
- "Valider commande" <<include>> 
  - Générer facture
  - Mettre à jour stock
  - Envoyer email de confirmation

---

## Frontière du système

Nom du système : "Système de gestion des commandes"

Les acteurs sont à l’extérieur de la frontière.
Les cas d’utilisation sont à l’intérieur.