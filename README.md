# Elastic_Restaurants

Pour pouvoir faire des aggrégations sur les champs cuisine, borough et name,<br>
j'ai utilisé le rajout d'un champ raw de type keyword à chacun de ces 3 champs.<br>
Ainsi, lorsque je fais un regroupement sur borough.raw par exemple, il ne me fait pas<br>
un regroupement pour "Staten", un autre regroupement pour "Island", mais bien un seul<br>
pour "Staten Island".<br>
Il faut donc recréer l'index avec la commande:<br>
curl -X PUT "localhost:9200/restaurants?pretty" -H 'Content-Type: application/json' --data-binary @createRestaurantsIndex.json
