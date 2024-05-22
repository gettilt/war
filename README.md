<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# War
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Nationalism is on the rise, increasing the threat of war globally. Governments will build up arms to prepare.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| BA | Boeing, while known for commercial planes, also has a significant defense segment that could benefit from increased military spending. | chat_gpt,claude,twitter,google |
| CAE | CAE Inc. offers simulation technologies and training services for defense forces, likely to see higher demand for military preparedness. | chat_gpt |
| CW | Curtiss-Wright provides high-tech components for defense markets, likely to benefit from increased military spending. | chat_gpt,claude |
| GD | General Dynamics offers a range of defense products and services, likely to see demand rise with military buildups. | chat_gpt,claude,twitter,google |
| HEI | Heico Corporation provides aerospace and electronics products, likely to see increased sales with defense sector growth. | chat_gpt |
| HII | Huntington Ingalls Industries, as a major shipbuilding company, would benefit from naval expansion efforts. | chat_gpt,claude,google |
| KTOS | Kratos Defense & Security Solutions offers unmanned systems and satellite communications, relevant for modern warfare. | chat_gpt,claude |
| LHX | L3Harris Technologies provides advanced defense communications and electronic systems, likely to see increased demand. | chat_gpt,claude,twitter,google |
| LMT | Lockheed Martin is a leading defense contractor, likely to see increased orders for military hardware. | chat_gpt,claude,twitter,google |
| MRCY | Mercury Systems offers processing systems and software for defense applications, standing to gain from tech-focused defense upgrades. | chat_gpt,claude |
| NOC | Northrop Grumman specializes in aerospace and defense technology, standing to gain from increased defense budgets. | chat_gpt,claude,twitter,google |
| OSK | Oshkosh Corporation manufactures military vehicles and could see increased orders as nations bolster their ground forces. | chat_gpt |
| RTX | Raytheon Technologies provides advanced defense systems and could benefit from heightened military spending. | chat_gpt,claude,twitter,google |
| TDG | TransDigm Group manufactures aerospace components, potentially benefiting from increased production of military aircraft. | chat_gpt |
| TXT | Textron is involved in aircraft, defense, and industrial products, with potential gains from increased defense spending. | chat_gpt,claude,twitter,google |
| AVAV |  | claude |
| BWXT |  | claude |
| HXL |  | claude |
| LUV |  | twitter |
| HWM |  | google |
| LDOS |  | google |
| PFE |  | google |
| PG |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/war/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/war" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
