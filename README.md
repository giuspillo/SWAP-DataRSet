# Repository for recommendation datasets 

This repository contains the dasasets commonly used in RecSys settings.

These datastes are:
* Movielens 1M
* Dbbook
* Last-FM

For each dataset, **both graph and textual** information is available; moreover, for ML1M and DBbook, we provide the mapping to visual content (movie posters and book covers)
 
The structure is the following:
```
 <name_of_the_dataset>:
	-graph:
		-user-item:
			train_sorted.tsv
			test_sorted.tsv
		-item-prop:
			train_sorted.tsv
			test_sorted.tsv
		-user-item-prop:
			train_sorted.tsv
			test_sorted.tsv
		mapping_users.tsv
		mapping_items.tsv
		mapping_properp.tsv
		mapping_relations.tsv
	-text:
		map_text.csv
		idtext_idgraph.tsv
		<text_of_items>
	-images:
		mapping_dataset.tsv
```

The `graph` folder contains **pure collaborative** information (`user-item`), **only knowledge**-related information (`item-prop`), and the union of the two, the **hybrid** version (`user-item-prop`, in which the graph is triparted and encods collaborative information with the knowledge aboout the items. In addition, useful **mapping files** are available (to get the name/URI of an item, or a property, or a user).

The `text` folder contains textual information related to the items in the dataset. This information is encoded as a unique file for the datasets `movielens` and `lastfm`, while is split into several files for `dbbook` (each file with the ID of the item); the file `map_text` is useful to map the ID of an item with a name and/or URI, while the file `idtext_idgraph` is useful to map item IDs from `text` folder to `graph` folder.

The `images` folder contain the URLs to visual informaton related to the items in the dataset, due to copyright issue. Each item is mapped with the ID used in the graph, the DBpedia URI, e the URL of the image (most of them are from Wikipeida).