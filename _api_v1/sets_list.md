---
title: /sets
position: 2.0
type: get
description: Get All Sets
right_code: |
  ~~~ json
  {
  "sets":[
    {
      "name":"Core Set",
      "releaseDate":"2016-04-01",
      "totalCards":412,
      "id":"cs"
    },
    {
      "name":"Madhouse Collection",
      "releaseDate":"2016-12-14",
      "totalCards":10,
      "id":"mc"
    },
    {
      "name":"Monthly Rewards",
      "releaseDate":"",
      "totalCards":17,
      "id":"mr"
    },
    {
      "name":"The Fall of the Dark Brotherhood",
      "releaseDate":"2017-04-05",
      "totalCards":40,
      "id":"fodb"
    },
    {
      "name":"Heroes of Skyrim",
      "releaseDate":"2017-06-29",
      "totalCards":154,
      "id":"hos"
    },
    {
      "name":"Return to Clockwork City ",
      "releaseDate":"2017-11-30",
      "totalCards":55,
      "id":"rcc"
    }
  ],
  "_pageSize":100,
  "_totalCount":6
  }
  ~~~
  {: title="Response" }
---

This call will return a maximum of 100 sets.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of sets returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

Each field below can be used as a query parameter. By default, fields that have a singular value such as rarity, type, and name will always use a logical "or" operator when querying with a list of values. Fields that can have multiple values such as attributes and keywords can use a logical "and" or a logical "or" operator.

The accepted delimiters when querying fields are the pipe character or a comma character. The pipe represents a logical "or", and a comma represents a logical "and".

Example:`name=core|brotherhood`

More examples: `name=dark,brother` versus `kenameywords=dark|brother`

name
: The set name. Put the name in double quotes for an exact match, otherwise partial matching will be applied.

releaseDate
: The date the set was released. Formatted as YYYY-MM-DD

totalCards
: The total number of cards in the set

id
: The id of the set

~~~ ruby
require 'elder_scroll_legends_sdk'

# Get all sets
sets = ElderScrollsLegends::Set.all

# Filter sets
sets = ElderScrollsLegends::Set.where(name: 'core')

# Get specific page of data
sets = ElderScrollsLegends::Set.where(page: 1)
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Set

# Get all sets
sets = Set.all()

# Filter sets
sets = Set.where(name='core')

# Get specific page of data
sets = Set.where(page=1) 
~~~
{: title="python" }

~~~ bash
# Get all sets
curl "https://api.elderscrollslegends.io/v1/sets"

# Filter sets
curl "https://api.elderscrollslegends.io/v1/sets?name=core"

# Get specific page of data
curl "https://api.elderscrollslegends.io/v1/sets?page=1"
~~~
{: title="bash"}