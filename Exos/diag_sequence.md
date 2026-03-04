# Diagramme de séquence : Traitement d’une commande en ligne

## Acteurs et Objets
- **Client**
- **Interface Web**
- **Système de Gestion des Commandes**
- **Système de Paiement**
- **Service de Livraison**

---

## Scénario principal

1. **Client** → **Interface Web** : Se connecter
2. **Interface Web** → **Système de Gestion des Commandes** : Vérifier identifiants
3. **Client** → **Interface Web** : Ajouter produit(s) au panier
4. **Interface Web** → **Système de Gestion des Commandes** : Mettre à jour le panier
5. **Client** → **Interface Web** : Valider le panier
6. **Système de Gestion des Commandes** → **Système de Gestion des Commandes** : Vérifier disponibilité des produits
   - Si un produit est indisponible :  
     - **Système** → **Interface Web** : Afficher message et demander modification
7. **Client** → **Interface Web** : Choisir mode de livraison
8. **Client** → **Interface Web** : Effectuer le paiement
9. **Interface Web** → **Système de Paiement** : Vérifier paiement
   - Si paiement échoue :  
     - **Système de Paiement** → **Interface Web** : Message d’erreur  
     - Retour à l’étape de paiement
   - Si paiement validé :
     1. **Système de Gestion des Commandes** → **Système de Gestion des Commandes** : Générer facture
     2. **Système de Gestion des Commandes** → **Système de Gestion des Commandes** : Mettre à jour stock
     3. **Système de Gestion des Commandes** → **Client** : Envoyer email de confirmation
10. **Système de Gestion des Commandes** → **Service de Livraison** : Planifier livraison
11. **Fin du processus**