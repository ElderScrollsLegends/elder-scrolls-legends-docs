---
title: /cards/:id
position: 1.1
type: get
description: Get Card
right_code: |
  ~~~ json
  {
    "name": "Alduin",
    "rarity": "Legendary",
    "type": "Creature",
    "subtype": "Dragon",
    "cost": 20,
    "power": 12,
    "health": 12,
    "set": {
      "id": "hos",
      "name": "Heroes of Skyrim",
      "_self": "https://api.elderscrollslegends.io/v1/sets/hos"
    },
    "soulSummon": 1200,
    "soulTrap": 400,
    "text": "Costs 2 less for each Dragon in your discard pile. Summon: Destroy all other creatures. At the start of your turn, summon a random Dragon from your discard pile.",
    "attributes": [
      "Neutral"
    ],
    "keywords": [],
    "unique": true,
    "imageUrl": "https://images.elderscrollslegends.io/hos/alduin.png",
    "id": "1fd81123ab3eca0b29c4c19757045db9757b4f1a"
  }
  ~~~
  {: title="Response" }
---

Returns a specific card by id

~~~ ruby
require 'elder_scrolls_legends_sdk'

card = ElderScrollsLegends::Card.find('1fd81123ab3eca0b29c4c19757045db9757b4f1a')
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Card

card = Card.find('1fd81123ab3eca0b29c4c19757045db9757b4f1a')
~~~
{: title="python" }

~~~ bash
curl "https://api.elderscrollslegends.io/v1/cards/1fd81123ab3eca0b29c4c19757045db9757b4f1a"
~~~
{: title="bash"}
