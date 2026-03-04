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

- Client 1 ── * Panier
- Panier * ── * Produit
- Commande 1 ── 1 Client
- Commande 1 ── * Produit
- Commande 1 ── 1 Paiement
- Commande 1 ── 1 Livraison
- ProduitPhysique et ProduitNumerique héritent de Produit
- ClientParticulier et ClientProfessionnel héritent de Client