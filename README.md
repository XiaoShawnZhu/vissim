#VISSIM Tools

##VISSIM v8.x (/vissim_v8)

###Current VISSIM objects supported:
- VISSIM network attributes and parameters
- Vehicle Inputs
- Links
- Static Route Decisions

###Current methods supported:
- Import data from .INPX file
- Export data to .INPX file
- Get object attributes
- Set object attributes 
- Create objects
- Remove objects

###Install:
``` python
python setup_v8.py install
```

###Usage:
```python
import vissim_v8 as vissim
v = vissim.Vissim('vissim_v8/example/Busmall.inpx')
```
Access VISSIM object data:
```
links = vissim.Links
# Access data for link 2
>>> links[2]
>>> {'assumSpeedOncom': '60.000000',
 'costPerKm': '0.000000',
 'direction': 'ALL',
 'displayType': '1',
 'emergStopDist': '5.000000',
 'gradient': '0.000000',
 'hasOvtLn': 'false',
 'isPedArea': 'false',
 'lane': ['3.500000', '3.500000'],
 'level': '1',
 'linkBehavType': '1',
 'linkEvalAct': 'false',
 'linkEvalSegLen': '10.000000',
 'lnChgDist': '200.000000',
 'lnChgDistIsPerLn': 'false',
 'lnChgEvalAct': 'true',
 'lookAheadDistOvt': '250.000000',
 'mesoFollowUpGap': '0.000000',
 'mesoSpeed': '50.000000',
 'mesoSpeedModel': 'VEHICLEBASED',
 'name': '',
 'no': '2',
 'ovtOnlyPT': 'false',
 'ovtSpeedFact': '1.300000',
 'point3D': [('-530.781000', '3904.459000', '0.000000'),
  ('-178.082000', '3905.115000', '0.000000')],
 'showClsfValues': 'true',
 'showLinkBar': 'true',
 'showVeh': 'true',
 'surch1': '0.000000',
 'surch2': '0.000000',
 'thickness': '0.000000',
 'vehRecAct': 'true'}
```
Create new VISSIM objects:
```
# Create link from coord 0,0 to 10,15
coords = {'points3D': [(0,0,0), (10,15,0)]}
links.createLink(**coords)
```
Export VISSIM model to new file:
```
v.export('example_new.inpx')
```

##VISSIM v5.x (/vissim_v5)

###Current VISSIM objects supported:
- Vehicle Inputs
- Links
- Connectors
- Route Decisions

###Current methods supported:
- Import data from .INP file
- Export data to .INP file
- Get object attributes
- Set object attributes 
- Create objects

###Install:
``` python
python setup.py install
```

###Usage:
```python
import vissim_v5 as vissim

links = vissim.Links('example.inp')
# Create link from coord 0,0 to 10,15
links.create((0,0), (10,15))
# Export loaded link data and new link
links.export('example_new.inp')
```
