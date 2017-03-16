# Twig for Craft 2
> Adds a comprehensive set of Craft 2 snippets to use in your Twig templates.

## Tab Trigger Reference

### Generic Triggers

```twig

}}                {{  }}
%%                {%  %}
##                {#  #}

do                {% do ... %}
extends           {% extends 'template' %}
from              {% from 'template' import 'macro' %}
import            {% import 'template' as name %}
importself        {% import _self as name %}
inc, include      {% include 'template' %}
incp              {% include 'template' with params %}
inckv             {% include 'template' with { key: value } %}
use               {% use 'template' %}

autoescape        {% autoescape 'type' %}...{% endautoescape %}
block, blockb     {% block name %} ... {% endblock %}
blockf            {{ block('...') }}
embed             {% embed "template" %}...{% endembed %}
filter, filterb   {% filter name %} ... {% endfilter %}
macro             {% macro name(params) %}...{% endmacro %}
set, setb         {% set var = value %}
spaceless         {% spaceless %}...{% endspaceless %}
verbatim          {% verbatim %}...{% endverbatim %}

if, ifb           {% if condition %} ... {% endif %}
ife               {% if condition %} ... {% else %} ... {% endif %}
for               {% for item in seq %} ... {% endfor %}
fore              {% for item in seq %} ... {% else %} ... {% endfor %}

else              {% else %}
endif             {% endif %}
endfor            {% endfor %}
endset            {% endset %}
endblock          {% endblock %}
endfilter         {% endfilter %}
endautoescape     {% endautoescape %}
endembed          {% endembed %}
endfilter         {% endfilter %}
endmacro          {% endmacro %}
endspaceless      {% endspaceless %}
endverbatim       {% endverbatim %}
```

### Craft Triggers

```twig
asset                    craft.assets.first()
assets, assetso          craft.assets loop
categories, categorieso  craft.categories loop
entries, entrieso        craft.entries loop
feed                     craft.feeds.getFeedItems loop
t                        |t
tags, tagso              craft.tags loop
users, userso            craft.users loop

cache                    {% cache %}...{% endcache %}
children                 {% children %}
exit                     {% exit 404 %}
ifchildren               {% ifchildren %}...{% endifchildren %}
includecss               {% includecss %}...{% endincludecss %}
includecssfile           {% includeCssFile "/resources/css/global.css" %}
includehirescss          {% includehirescss %}...{% endincludehirescss %}
includejs                {% includejs %}...{% endincludejs %}
includejsfile            {% includeJsFile "/resources/js/global.js" %}
matrix, matrixif         Basic Matrix field loop using if statements
matrixifelse             Basic Matrix field loop using if/elseif
matrixswitch             Basic Matrix field loop using switch
nav                      {% nav item in items %}...{% endnav %}
paginate                 Outputs example of pagination and prev/next links
redirect                 {% redirect 'login' %}
requirelogin             {% requireLogin %}
requirepermission        {% requirePermission "spendTheNight" %}
switch                   {% switch variable %}...{% endswitch %}

csrf                     {{ getCsrfInput() }}
getfoothtml              {{ getFootHtml() }}
getheadhtml              {{ getHeadHtml() }}

getparam                 craft.request.getParam()
getpost                  craft.request.getPost()
getquery                 craft.request.getQuery()
getsegment               craft.request.getSegment()

case                     {% case "value" %}
endcache                 {% endcache %}
endifchildren            {% endifchildren %}
endincludecss            {% endincludecss %}
endincludehirescss       {% endincludehirescss %}
endincludejs             {% endincludejs %}
endnav                   {% endnav %}

ceil                     ceil()
floor                    floor()
max                      max()
min                      min()
round                    round()
shuffle                  shuffle()
url, urla                url('path'), url('path', params, 'http', false)

dd                      <pre>{{ dump() }}</pre>{% exit %}
dump                    <pre>{{ dump() }}</pre>
```

### Reference Hints
```
info            All craft.assets properties and template tags
info            All craft.crategories properties and template tags
info            All craft.config properties and template tags
info            All craft.entries properties and template tags
info            All craft.feeds properties and template tags
info            All craft.fields properties and template tags
info            All craft.globals properties and template tags
info            All craft.request properties and template tags
info            All craft.sections properties and template tags
info            All craft.session properties and template tags
info            All craft.tags properties and template tags
info            All craft.users properties and template tags
info            All craft globals (site info, date, users, template tags)
```

## Credits
This extension is _heavily_ influenced by the amazing work of [Ben Parizek] on [Craft Twig for Sublime/Textmate][craft-twig]

Thank you, Ben👍

## Changelog

### 0.4.0
- Fixed wrong path used in `includejs`
- Renamed `ciel` to `ceil` where necessary

Thank you, [Dominic](https://github.com/DominicVonk) 👍

### 0.3.0
- Added full tab trigger reference table
- Added `t` tab trigger for static translations
- Added `dd` tab trigger for the twig context
- Updated _snippets file_ to use spaces instead of tabs
- Removed `dd` tab trigger for _non-template_ contexts

### 0.2.0
- Added branding resources
- Added extension and repository metadata
- Fixed issue where snippets were not triggering suggestions

### 0.1.0
- Initial (alpha) release

[Ben Parizek]:https://github.com/BenParizek
[craft-twig]:https://github.com/barrelstrength/Craft-Twig.tmbundle
