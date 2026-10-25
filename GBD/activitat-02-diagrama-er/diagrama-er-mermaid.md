# Model E/R (en Mermaid)


## Per fer el diagrama primer cal crear l'entitat que connecta tot: ```Personatge```.

```mermaid
erDiagram
    Personatge
```

### Li afegim el atributs que tindra el ```Personatge```
    
> ```PK```: Clau Primaria (Atribut Identificador).
>
> ```"NOT NULL"```: Ha de tenir un valor obligatoriament (Atributs no nul).

### Cada **Atribut** ha de tenir un tipus de dada.
    
> ```string```: Text literal.
> 
> ```int```: Nombre sencer.
> 
> ```float```: Nombre amb decimals.
> 
> ```boolean```: Vertader o Fals.

```mermaid
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
```

Repetim aquest procés fins a tenir totes les entitats creades:

```Habilitat```

```mermaid
erDiagram
    HABILITAT {
        string Codi PK
        string Nom "NOT NULL"
        int Cost
        int Dany
        float Cooldown
        string Tipus "NOT NULL"
    }
```

```Enemic```

```mermaid
erDiagram
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
```

```Mascota```

```mermaid
erDiagram
    MASCOTA {
        string Num_Chip PK
        string Nom "NOT NULL"
        boolean Motxilla
    }
```

```Item```

```mermaid
erDiagram
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
```

### **Relacions** utilitzats en aquesta diagrama:

Relació Molts a Molts (M:N), és representa amb ```}o-```

```mermaid
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
    PERSONATGE }o--o{ HABILITAT : "posseeix"
```

Relació Un a Un (1:1), és representa amb ```||-```

```mermaid
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
    MASCOTA {
        string Num_Chip PK
        string Nom "NOT NULL"
        boolean Motxilla
    }
    PERSONATGE ||--|| MASCOTA : "acompanya"
```

Ara li afegim les relacions que tenen entre ```Personatge```, ```Habilitat```, ```Mascota```, ```Enemic```, ```Item```

```mermaid
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
```
