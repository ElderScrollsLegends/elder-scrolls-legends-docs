---
title: /attributes
position: 3.0
type: get
description: Get All Attributes
right_code: |
  ~~~ json
  {
    "attributes": [
        "Agility",
        "Endurance",
        "Intelligence",
        "Neutral",
        "Strength",
        "Willpower"
    ],
    "_pageSize": 100,
    "_totalCount": 6
  }
  ~~~
  {: title="Response" }
---

This call will return a maximum of 100 attributes.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of attributes returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

~~~ ruby
require 'elder_scroll_legends_sdk'

attributes = ElderScrollsLegends::Attribute.all
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Attribute

attributes = Attribute.all()
~~~
{: title="python"}

~~~ bash
curl "https://api.elderscrollslegends.io/v1/attributes"
~~~
{: title="bash"}