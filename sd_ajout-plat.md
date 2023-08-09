```mermaid
sequenceDiagram
    autonumber
    actor Chef

    Note over Chef,system: Authentification

    Chef->>+system: consulter plat
    system-->>-Chef: affichage des plats du jour

    loop Pour chaque plat
        alt Ajout plat
        Chef->>+system: Ajout titre
        Chef->>+system: Ajout description
        Chef->>+system: Ajout prix
        system-->>Chef: Confirmation ajout plat du jour
        else Erreur
        system-->>-Chef: Erreur ajout plat du jour
        end
    end
    
    Chef->>+system: mise à jour des quantités
    system-->>-Chef: confirmation mise à jour quantités

```
