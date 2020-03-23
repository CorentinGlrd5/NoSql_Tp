Créer une collection sport avec 3-4 film.
Ajouter 2 nouveau film : title et required teams avec upsert

Mettre à jour tous les element avec une team en ajoutant un minimum de joureur

Mettre à kour tous les element qui on besoins d'une team en ajoutant des joueur par 10.

Dans tous les element, rajouter un array teams avec deux joueurs

MAJ tous les element de teams, rajouter une propriété titulaire = true

Démarer le server :

```bash
Start mongoD
```

Lancer la commande :

```bash
Mongo
```

Lister les database :

```bash
show dbs
```

Lister les tables :

```bash
show tables
```

Afficher les stats de la base de donnée

```bash
db.stats()
```

Creer la collection sports :

```bash
db.createCollection("sports")
```

Ce mettre sur la collection sports :

```bash
use sports
```

Insérer plusieurs film :

```bash
db.sports.insertMany([{ title: "Pelé : Naissance d'une légende", description: "L'incroyable ascension de la légende du football, qui, grâce à un style hors norme et à force de détermination, triompha de tous les obstacles, pour devenir l'inspiration d'un pays tout entier, et le changer à jamais." }, { title: "Spiker", description: "Spiker est un film dramatique sportif américain de 1986 avec Michael Parks et réalisé par Roger Tilton." }, { title: "Creed : L'Héritage de Rocky Balboa", description: "Adonis Johnson n'a jamais connu son père, le célèbre champion du monde poids lourd Apollo Creed décédé avant sa naissance. Pourtant, il a la boxe dans le sang et décide d'être entraîné par le meilleur de sa catégorie." }])
```

Ajouter 2 nouveau film : title et required teams avec upsert

```bash
db.sports.updateOne({ title: "La Rage au ventre" }, { $set: { description: "Champion du monde de boxe, Billy Hope mène une existence fastueuse avec sa superbe femme et sa fille qu'il aime plus que tout. Lorsque sa femme est tuée, son monde s'écroule, jusqu'à perdre sa maison et sa fortune." } }, { upsert: true })
```

```bash
db.sports.updateOne({ title: "Le stratège" }, { $set: { description: "À la fin de la saison 2001, les A's d'Oakland s'inclinent contre les Yankees de New York en série de division de la Ligue Américaine." } }, { upsert: true })
```

Lister les valeurs dans la collection sports avec une meilleur lisibilité :

```bash
db.products.find().pretty()
```

Mettre à jour tous les element avec une team en ajoutant un minimum de joureur :

```bash
db.sports.insertOne({ title: "Pelé : Naissance d'une légende"}, {team: 5})
```
