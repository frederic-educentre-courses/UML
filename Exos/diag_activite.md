# Cas : Système de gestion d’une commande en ligne

## Contexte
Une entreprise de e-commerce souhaite modéliser le processus de traitement d’une commande passée par un client sur son site web.

## Scénario

1. Le client se connecte à son compte.
2. Il ajoute des produits à son panier.
3. Il valide son panier.
4. Le système vérifie la disponibilité des produits.
   - Si un produit est indisponible → afficher un message et permettre au client de modifier son panier.
   - Si tous les produits sont disponibles → continuer.
5. Le client choisit un mode de livraison.
6. Le client effectue le paiement.
7. Le système vérifie le paiement.
   - Si le paiement échoue → afficher un message d’erreur et proposer une nouvelle tentative.
   - Si le paiement est validé :
       - Générer la facture.
       - Mettre à jour le stock.
       - Envoyer un email de confirmation.
8. La commande est enregistrée.
9. Fin du processus.

## Éléments à inclure dans le diagramme d’activité

- Nœud initial
- Nœud final
- Actions (ex : "Vérifier disponibilité")
- Décisions (paiement validé ? produit disponible ?)
- Boucle (si paiement échoue ou produit indisponible)