# Desenvolupament del Backend. Programació de serveis REST

## Introducció

### Què són les API?

Una API (*Application Programming Interface*) es pot entendre com una mena d'*intermediari* entre diferents sistemes i aplicacions, que defineix el conjunt de regles que permet que aquests es comuniquen i compartisquen dades i funcionalitats.

Dit d’una altra manera, una API especifica *com un programa pot utilitzar els serveis o funcionalitats d’un altre* sense necessitat de conéixer-ne els detalls interns.

Alguns exemples d'APIs que ens podem trobar són:

* **APIs del sistema operatiu:** que permeten als programes accedir als recursos del sistema, com fitxers, dispositius, memòria o gestió de processos.
* **APIs de plataformes de desenvolupament:** que permeten als desenvolupadors una capa d'abstracció per sobre el sistema operatiu, com puga ser l'API que ens ofereix Android per accedir a la càmera, al GPS o mostrar notificacions.
* **APIs de serveis web:** En l’àmbit d’Internet, moltes empreses i serveis ofereixen APIs perquè altres aplicacions puguen consumir les seues dades o funcionalitats. Per exemple, l’API de Google Maps permet integrar mapes dins d’una aplicació, l’API de Twitter permet publicar o llegir tuits, i l’API d’un servei meteorològic pot oferir dades del temps en temps real.

### Cap als serveis REST

Dins d’aquest últim punt grup trobem les *APIs REST (o serveis REST)*, que són serveis web basats en el protocol *HTTP* i dissenyats seguint un conjunt de principis senzills i estandarditzats. Aquestes APIs permeten que diferents aplicacions, sovint allotjades en llocs distints d’Internet, puguen intercanviar dades de forma senzilla i eficient, utilitzant formats habituals com *JSON* o *XML*.

Les APIs REST són la base de gran part de la comunicació entre aplicacions actuals -tant en aplicacions web com mòbils-, i per això constitueixen un punt clau en la **programació de serveis i processos**, ja que ens permeten connectar, automatitzar i fer col·laborar diferents sistemes.

### El "Backend"

Les APIs podríem dir que són la **porta d’accés al backend**. 

En un context d’aplicacions client-servidor, el client (*front-end*, ja siga web o mòbil) és l’aplicació amb què interactua l’usuari, mentre que el servidor (o *backend*) és qui s’encarrega de processar les peticions, accedir a les dades, aplicar la lògica de negoci i retornar respostes.

En aquest tipus d'aplicacions, el client no es comunica directament amb la base de dades o els sistemes interns del servidor, sinò que ho fa a través d'una API que defineix com ha de fer aquestes peticions i quin tipus de respostes pot esperar.

Reprenent la definició inicial, l'*API* actúa com a intermediari entre el *frontend* i el *backend*. En el cas de les *APIs REST*, a més, l'intercanvi d'informació es realitza mitjançant el protocol HTTP (peticions GET, POST, PUT, DELETE...) i fent ús de formats com JSON o XML per a l'intercanvi de dades.


### Tipus de peticions i rutes en una API REST

En una API REST, la comunicació entre el **client** i el **servidor (backend)** es basa en **peticions HTTP**, el mateix protocol que fem servir per navegar per Internet.

Cada petició té dos elements fonamentals:

1. **El tipus de petició (mètode HTTP)**
2. **La ruta o recurs al qual s’accedeix**

#### Tipus principals de peticions HTTP

Els mètodes HTTP indiquen **quina acció volem realitzar** sobre un recurs:

* **GET**: Serveix per **consultar o obtindre informació**.
  Exemple: `GET /usuaris` podria retornar la llista d’usuaris.

* **POST**: Serveix per **crear un nou recurs**.
  Exemple: `POST /usuaris` podria afegir un nou usuari a la base de dades.

* **PUT**: Serveix per **actualitzar completament** un recurs existent.
  Exemple: `PUT /usuaris/3` podria modificar totes les dades de l’usuari amb id 3.

* **PATCH**: Serveix per **actualitzar parcialment** un recurs.
  Exemple: `PATCH /usuaris/3` només canviaria algunes propietats de l’usuari.

* **DELETE**: Serveix per **eliminar** un recurs.
  Exemple: `DELETE /usuaris/3` eliminaria l’usuari amb id 3.

#### Rutes, recursos o *endpoints*

Les **rutes** (també anomenades *endpoints*) indiquen **a quin recurs o servei** estem accedint dins l’API.

Per exemple:

```
GET     /productes
GET     /productes/12
POST    /productes
PUT     /productes/12
DELETE  /productes/12
```

Cada combinació de **mètode + ruta** defineix una acció concreta. Així, una API REST acaba funcionant com un **catàleg ordenat de rutes** que permeten al client comunicar-se amb el servidor d’una manera clara, estructurada i previsible.

Bé, ara que ja tenim més o menys clars els conceptes, anem a veure-ho en la pràctica a través de diversos exemples.