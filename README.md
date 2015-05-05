# TpNoSQL
#Compte Rendu du Tp :Decouverte des bases de Nosql 
#Reponse des Questions du TP
#Questions :
Quelles sont les limites des bases  de donnees orientes document?
#Reponses:
Il est clair que les bases de données orientées document comme NoSQL   ne sont  pas adapté à toutes les situations.
Les bases de données orientées document comme NoSQL sont généralement assez limitées au niveau du support des transactions.
Si l'édition d'un objet se fait en principe de manière atomique, dès qu'il s'agit de modifier
plusieurs objets dépendant les uns des autres, la base n'offre plus les garanties qu'on retrouve avec le relationnel.
Plus globalement, les Propriétés ACID ainsi que les contraintes d'intégrité ne sont généralement pas implémentées 
par les bases de données orientées document comme NoSQL   , cela délègue cette gestion à la partie applicative.
Les optimistes diront qu'il est souvent plus facile de répartir la charge du côté applicatif que sur la base de données 
et que cela permet donc d'avoir de meilleurs performances globales.
Le relationnel dispose également d'un langage de requête extrêmement puissant, qui offre des possibilités très larges, 
avec en particulier la possibilité de lier des tables entre elles, filtrer et trier selon de nombreux critères ou
agréger les données. Ceci est particulièrement utile quand il s'agit de générer des rapports complexes,
domaine dans le lequel les bases de données relationnelles sont très à l'aise.
Du fait de son langage de requête plus poussé et des optimisations qui peuvent en être tirées, 
les bases SQL sont souvent plus performantes sur les requêtes complexes qui nécessiteraient de rapatrier plus de données 
que nécessaire pour les traiter en NoSQL. Sinon, tant qu'on peut conserver les index en cache, 
les performances sont très bonnes quelque soit le type de bases de données.
Par contre, certaines recherches spécifiques sont bien plus performantes avec des systèmes adaptés (par exemple, 
la recherche full-textavec Lucene via ElasticSearch).

#Questions :
Quelles sont les types de donnees stockes dans Redis , que peut on faire comme type de requetes?
#Reponses:
<u>type de donnees manipuler</u>:
-Redis Permet de manipuler types de donnees simples :typage des données en chaîne de caractères, listes, 
tableaux associatifs et ensembles triés d'éléments, et propose des opérations avancées propres à chaque type.
-Dans Notre  projet ci-precit  les types de donnees stockees dans redis sont des collections  d'objets non ordonnées
avec des valeurs uniques couple cle/valeur (chaîne de caractères)
avec la commande :  jedis.sadd(cacheKey,"Python);//SADD on ajoute 
                  jedis.smembers(CacheKey ) //SMEMBERS (pour récupérer le set)
                    
<u>Requetes possibles </u>:
on a la  possibilité de gérer l'expiration des données avec la commande expire:
                     jedis.expire(cachekey,15); //ce qui rend  Redis comme  un outil idéal pour gérer du cache.
on a la possibilité d'incrementer la valeur Redis:
                      jedis.incr("counter");
                      
