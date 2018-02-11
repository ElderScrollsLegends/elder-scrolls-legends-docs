---
title: /keywords
position: 4.0
type: get
description: Get All Keywords
right_code: |
  ~~~ json
  {
    "keywords": [
        "Assemble",
        "Breakthrough",
        "Charge",
        "Drain",
        "Guard",
        "Last Gasp",
        "Lethal",
        "Pilfer",
        "Prophecy",
        "Regenerate",
        "Shackle",
        "Slay",
        "Treasure Hunt",
        "Ward"
    ],
    "_pageSize": 100,
    "_totalCount": 14
  }
  ~~~
  {: title="Response" }
---

This call will return a maximum of 100 keywords.
{: .info }

Paginate the response using the `page` parameter. You can change the amount of keywords returned with the `pageSize` parameter. Anywhere from 1-100 is valid.

~~~ ruby
require 'elder_scroll_legends_sdk'

keywords = ElderScrollsLegends::Keyword.all
~~~
{: title="ruby" }

~~~ python
from elderscrollslegendssdk import Keyword

keywords = Keyword.all()
~~~
{: title="python"}

~~~ bash
curl "https://api.elderscrollslegends.io/v1/keywords"
~~~
{: title="bash"}