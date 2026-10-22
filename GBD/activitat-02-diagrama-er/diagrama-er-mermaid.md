erDiagram

    PERSONATGE {
        string DNI PK
        string Nom "NOT NULL"
        string Cognom
        int Vida
        int Forca
        int Agilitat
        int Carisma
    }

    HABILITAT {
        string Codi PK
        string Nom "NOT NULL"
        int Cost
        int Dany
        float Cooldown
        string Tipus "NOT NULL"
    }

    ENEMIC {
        string Codi PK
        string Nom "NOT NULL"
        string Tipus "NOT NULL"
        int Nivell "NOT NULL"
        int Vida
        int Forca
        int Agilitat
        int Carisma
    }

    MASCOTA {
        string Num_Chip PK
        string Nom "NOT NULL"
        boolean Motxilla
    }

    ITEM {
        string Codi PK
        string Nom "NOT NULL"
        boolean Equipable
        boolean Comerciable "NOT NULL"
        string Tipus "NOT NULL"
        float Pes "NOT NULL"
        string Qualitat "NOT NULL"
        %% Mesures (atribut compost) -> separat en X, Y, Z
        float Mesura_X "NOT NULL"
        float Mesura_Y "NOT NULL"
        float Mesura_Z "NOT NULL"
    }

    PERSONATGE }o--o{ HABILITAT : "posseeix"
    PERSONATGE }o--o{ ENEMIC : "enfrenta"
    PERSONATGE }o--o{ ITEM : "equipa"
    PERSONATGE ||--|| MASCOTA : "acompanya"

    HABILITAT }o--o{ HABILITAT : "combina amb"
    HABILITAT }o--o{ ENEMIC : "enfrenta"

    MASCOTA }o--o{ ITEM : "carrega"
