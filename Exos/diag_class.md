# Diagramme de classes avec héritage : Système de gestion d’une commande en ligne

## Classes principales et spécialisées

### Client (classe générale)
- **Attributs :**
  - idClient : int
  - nom : string
  - email : string
  - motDePasse : string
- **Méthodes :**
  - seConnecter()
  - validerPanier()
  - effectuerPaiement()

#### Héritage : types de clients
- **ClientParticulier** : Client
  - + dateNaissance : Date
  - + fidelitePoints : int
- **ClientProfessionnel** : Client
  - + siret : string
  - + remisePro : float

---

### Produit (classe générale)
- **Attributs :**
  - idProduit : int
  - nom : string
  - prix : float
  - stock : int
- **Méthodes :**
  - mettreAJourStock(qte)

#### Héritage : types de produits
- **ProduitPhysique** : Produit
  - + poids : float
  - + dimensions : string
- **ProduitNumerique** : Produit
  - + tailleFichier : float
  - + format : string

---

### Autres classes

#### Panier
- idPanier : int
- listeProduits : List<Produit>
- total : float
- + ajouterProduit(produit)
- + supprimerProduit(produit)
- + calculerTotal()

#### Commande
- idCommande : int
- dateCommande : Date
- statut : string
- modeLivraison : string
- + genererFacture()
- + mettreAJourStock()
- + envoyerConfirmation()

#### Paiement
- idPaiement : int
- montant : float
- statut : string
- + verifierPaiement()

#### Livraison
- idLivraison : int
- adresse : string
- dateLivraison : Date
- + planifierLivraison()

---

## Relations

- 1 Client **peut commander** 0 ou * panier
- 1 Panier **peut être commandé** par 1 Client
- 1 Panier **contient** 1 ou Produit
- 1 Produit **peut être contenu** par 0 ou * Panier
- 1 Client **dispose** de 0 ou * Commande
- 1 Commande **est disposé** par 1 Client
- 1 Commande **contient** 1 ou * Produit
- 1 Produit **est contenu** par 0 ou * Commande
- 1 Commande **correspond** à 1 Paiement
- 1 Commande **correspond** à 1 Livraison
- ProduitPhysique et ProduitNumerique héritent de Produit
- ClientParticulier et ClientProfessionnel héritent de Client
