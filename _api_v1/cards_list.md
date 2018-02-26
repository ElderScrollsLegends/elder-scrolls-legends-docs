---
title: /cards
position: 1.0
type: get
description: Get All Cards
right_code: |
  ~~~ json
  {
    "cards": [
      {
        "name": "Adoring Fan",
        "rarity": "Legendary",
        "type": "Creature",
        "subtypes": ["Wood Elf"],
        "cost": 3,
        "power": 0,
        "health": 1,
        "set": {
          "id": "cs",
          "name": "Core Set",
          "_self": "https://api.elderscrollslegends.io/v1/sets/cs"
        },
        "soulSummon": 1200,
        "soulTrap": 400,
        "text": "Prophecy, Guard. Last Gasp: Adoring Fan will return. Adoring Fan is immune to Silence.",
        "attributes": [
          "Neutral"
        ],
        "keywords": [
          "Guard",
          "Last Gasp",
          "Prophecy"
        ],
        "unique": true,
        "imageUrl": "https://images.elderscrollslegends.io/cs/adoring_fan.png",
        "id": "21909c205c443aa683d32133514db5cc3435f712"
      }
    ],
    "_pageSize": 100,
    "_totalCount": 1
  }
  ~~~
  {: title="Response" }
---
This call will return a maximum of 100 cards.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of cards returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

Each field below can be used as a query parameter. By default, fields that have a singular value such as rarity, type, and name will always use a logical "or" operator when querying with a list of values. Fields that can have multiple values such as attributes and keywords can use a logical "and" or a logical "or" operator.

The accepted delimiters when querying fields are the pipe character or a comma character. The pipe represents a logical "or", and a comma represents a logical "and".

Example:`name=alduin|glenumbra`

More examples: `keywords=guard,prophecy` versus `keywords=guard|prophecy`

name
: The card name. Put the name in double quotes for an exact match, otherwise partial matching will be applied.

rarity
: The rarity of the card (ex. Common, Epic, Rare, Legendary)

type
: The type of the card (ex. Action, Creature, Item, Support)

subtypes
: The subtypes of the card (ex. Argonian, Dragon, Imperial)

cost
: How much it costs to cast the card

power
: How much damage the card can do

health
: The total health of the card

set.id
: The id of the set the card belongs to

set.name
: The name of the set the card belongs to

soulSummon
: The number of soul gems it costs to soul summon

soulTrap
: The number of soul gems it costs to soul trap

text
: Rules of the card

attributes
: The attributes of the card (ex. Agility, Endurance, Intelligence)

keywords
: The keywords of the card (ex. Assemble, Breakthrough, Charge)

unique
: Is the card unique? Unqiue cards can only be included once per deck.

id
: A unique id for this card. It is made up via a SHA1 of the {card name}-{set name}


#### Other Fields in Response

The fields below are also part of the response (if not null), but cannot currently be used as query parameters

imageUrl
: The image url for a card.

~~~ ruby
require 'elder_scroll_legends_sdk'

# Get all cards
cards = ElderScrollsLegends::Card.all

# Filter cards
cards = ElderScrollsLegends::Card.where(type: 'creature', keywords: 'assemble|breakthrough')

# Get specific page of data
cards = ElderScrollsLegends::Card.where(page: 3)
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Card

# Get all cards
cards = Card.all()

# Filter cards
cards = Card.where(type='creature', keywords='assemble|breakthrough')

# Get specific page of data
cards = Card.where(page=3) 
~~~
{: title="python" }

~~~ bash
# Get all cards
curl "https://api.elderscrollslegends.io/v1/cards"

# Filter cards
curl "https://api.elderscrollslegends.io/v1/cards?type=creature&keywords=assemble|breakthrough"

# Get specific page of data
curl "https://api.elderscrollslegends.io/v1/cards?page=3"
~~~
{: title="bash"}