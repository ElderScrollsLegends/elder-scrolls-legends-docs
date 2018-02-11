---
title: /types
position: 5.0
type: get
description: Get All Types
right_code: |
  ~~~ json
  {
    "types": [
        "Action",
        "Creature",
        "Item",
        "Support"
    ],
    "_pageSize": 100,
    "_totalCount": 4
  }
  ~~~
  {: title="Response" }
---

This call will return a maximum of 100 types.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of types returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

~~~ ruby
require 'elder_scroll_legends_sdk'

types = ElderScrollsLegends::Type.all
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Type

types = Type.all()
~~~
{: title="python"}

~~~ bash
curl "https://api.elderscrollslegends.io/v1/types"
~~~
{: title="bash"}