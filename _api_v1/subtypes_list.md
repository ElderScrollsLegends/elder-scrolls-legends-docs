---
title: /subtypes
position: 6.0
type: get
description: Get All Subtypes
right_code: |
  ~~~ json
  {
    "subtypes": [
        "Argonian",
        "Ash Creature",
        "Beast",
        "Breton",
        "Centaur",
        "Chaurus",
        "Daedra",
        "Dark Elf",
        "Defense",
        ...
    ],
    "_pageSize": 100,
    "_totalCount": 50
  }
  ~~~
  {: title="Response" }
---

This call will return a maximum of 100 subtypes.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of subtypes returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

~~~ ruby
require 'elder_scroll_legends_sdk'

subtypes = ElderScrollsLegends::Subtype.all
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Subtype

subtypes = Subtype.all()
~~~
{: title="python"}

~~~ bash
curl "https://api.elderscrollslegends.io/v1/subtypes"
~~~
{: title="bash"}