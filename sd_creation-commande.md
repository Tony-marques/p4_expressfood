```mermaid
  sequenceDiagram
    autonumber
    actor client
    
    Note over client,system: Authentification

    client ->>+ system: Consulter catalogue
    system -->>- client: Affichage catalogue

    loop pour chaque produit
      client ->>+ system: Ajout du produit dans le panier
      system -->>- client: Confirmation ajout
    end

    client ->>+ system: Confirmer panier
    activate system
    system -->> client: demande une adresse de livraison
    client ->> system: Renseigner adresse
    deactivate system
    
    system -->> client: Demande de paiement de la commande
    activate system
    client ->> system: Renseigner moyen de paiement
    client ->> system: Validation de la commande
    system -->> client: Confirmation Commande
    deactivate system

    client ->>+ system: Consulter statut de la commande
    system -->>- client: Envoie statut de la commande









```
