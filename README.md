# Organization Map Generator

## Installation

```sh
pip install organization-map
```

## Dependencies

* PIL (pip install pillow)

## Organization structure
```python
orgs=[
    [{'id':11,'name':'Main Org\nLine 2','childs':[21,22],'fill':'#384891','color':'white'}]
    ,[{'arrowtext':'50%','id':21,'name':'Leaf 21','childs':[31,32,33]},{'id':22,'name':'leaf3','childs':[34]}]
    ,[{'id':31,'name':'leaf4','childs':[40]},{'id':32,'name':'leaf5'},{'id':33,'name':'leaf6','childs':[41,42]},{'id':34,'name':'leaf7'}]
    ,[{'id':40,'name':'leaf40'},{'id':41,'name':'Bottom Leaf','childs':[51],'fill':'red','color':'white'},{'id':42,'name':'Bottom Leaf'}]
    ,[{'id':51,'name':'Bottom Leaf 2\nLine 2\nLong Line 3'}]
]
```

Code example:

```python
from organization_map import generator

generator.generate_image(orgs).show()
```

## Output

![Screenshot](https://raw.githubusercontent.com/snuids/organization_map/master/media/Example.jpg?raw=true "Screenshot")

## Multi Level
```python
orgs=[[{'id': '2',
   'name': 'Father',
   'labels': ['', '', ''],
   'childs': [['22'], ['22', '23'], []],
   'parents': [[], [], []],
   'level': 0}],
 [{'id': '22',
   'name': 'Daughter',
   'labels': ['111 %', '222 %', ''],
   'childs': [[], [], []],
   'parents': [['2'], ['2'], []],
   'level': 1},
  {'id': '23',
   'name': 'Son',
   'labels': ['', '223 %', ''],
   'childs': [[], ['33'], []],
   'parents': [[], ['2'], []],
   'level': 1}],
 [{'id': '33',
   'name': 'Daughter 2',
   'labels': ['', '2333 %', ''],
   'childs': [[], [], []],
   'parents': [[], ['23'], []],
   'level': 2}]]
```

Code example:

```python
from organization_map import generator

generator.generate_image(orgs,multi_level=True).show()
```

## Output

![Screenshot](https://raw.githubusercontent.com/snuids/organization_map/master/media/Example2.jpg?raw=true "Screenshot")
