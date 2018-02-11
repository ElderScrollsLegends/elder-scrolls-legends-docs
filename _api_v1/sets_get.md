---
title: /sets/:id
position: 2.1
type: get
description: Get Set
right_code: |
  ~~~ json
  {
  "set":
    {
      "name":"Core Set",
      "releaseDate":"2016-04-01",
      "totalCards":412,
      "id":"cs"
    }
  }
  ~~~
  {: title="Response" }
---

Returns a specific set by id

~~~ ruby
require 'elder_scrolls_legends_sdk'

set = ElderScrollsLegends::Set.find('cs')
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Set

set = Set.find('cs')
~~~
{: title="python" }

~~~ bash
curl "https://api.elderscrollslegends.io/v1/sets/cs"
~~~
{: title="bash"}
