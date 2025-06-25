+++
title = 'Clash Royale'
date = 2024-09-10T00:15:22-04:00
draft = false
+++

Around 2019, I was really into Clash Royale, the mobile game made by Supercell. This blog assumes familiarity with the game.

My goal was to train a Bayesian network to predict the opponent's next played card. I scraped decks used by the top players using a non-official Clash Royale API via a proxy. The goal was to provide utilities for time-series graph analysis of player trends and build a predictive model. However, I didn't get that far because the data from the API sucked. This project is deprecated because I no longer clash.

I wrote a basic wrapper around `networkx` to work with the graph-structured deck information. The original code used node2vec feature embeddings (lol!), but I was also exploring Graph Attention Networks at the time. The edges are undirected and weighted by how many times two cards are used together.

```Python
from RoyaleAPI import Client
import matplotlib.pyplot as plt

dev_key = ...
proxy_url = 'https://proxy.royaleapi.dev/v1'

# Sample decks used by the top 10 players in global
client = Client(token=dev_key, url=proxy_url)
g = client.build_graph(depth=10)

nx.draw_circular(g, with_labels=True)
plt.show()
```

![](/cards.png)

Disregarding individual card names, you can observe some popular connections. For example, node 84 is the Fireball card, which is very popular across all trophy levels.

Probabilities are more informative. The normalized attribute matrix has rows that sum to 1. It says that for all edges (u,v), the element A(i,j) is the P(v=types[j] | u=types[i]). Diagonal elements are the probability of the same type being used in a deck. Buildings were only used with other buildings in about 4.4% of decks sampled, a not so popular strategy.

```Python
client = Client(token=dev_key, url=proxy_url)
g = client.build_graph(depth=100)

types = ['Troop', 'Spell', 'Building']
probs = nx.attr_matrix(g, node_attr="type", edge_attr='usages', normalized=True, rc_order=types)
print(probs)
```
```
[[0.45658263 0.41936775 0.12404962]
 [0.78915663 0.10692771 0.10391566]
 [0.66098081 0.29424307 0.04477612]]
```

This image shows how many times each card was used by the top 500 players. There are clear tier levels. Players at this trophy range tend to use quick cycle decks (3 > elixir cost).

![](/deg500.png)

# disclaimer

This content is not affiliated with, endorsed, sponsored, or specifically approved by Supercell and Supercell is not responsible for it. For more information see Supercell’s Fan Content Policy: www.supercell.com/fan-content-policy.
