```mermaid
  sequenceDiagram
    autonumber
    actor livreur

    Note over livreur,system: Authentification

    system ->> livreur: Vérification stock
    system ->> livreur: Proposition de commande

    alt commande refusée
      loop pour chaque commande refusée
        livreur -->>+ system: Commande refusée
        system -->>- livreur: Cherche nouveau livreur pour cette commande
      end
    else commande acceptée
      livreur -->>+ system: Commande acceptée
      system -->>- client: Notification livraison en cours
    end
    
      livreur -->>+ system: Commande livrée
      system -->>- client: Notification commande livrée
      livreur -->>+ system: Mise à jour des stocks
      system -->>- livreur: Confirmation mise à jour des stocks
```
