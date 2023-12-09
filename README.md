# Tensor Network Contraction
Tensor Network Contraction using Glen Evenbly's ncon.py routine (see [http://tensors.net/code](http://tensors.net/code))

## How to use ncon.py in Jupyter or Google Colab notebooks
```python 
import requests
from pathlib import Path

url = 'https://raw.githubusercontent.com/inaki-ortizdelandaluce/ncon/main/ncon.py'
file_name = 'ncon.py'

if Path(file_name).is_file():
  print(f"{file_name} already exists, skipping download")
else:
  print(f"Downloading {file_name}...")
  request = requests.request('GET', url)
  with open('ncon.py','wb') as f:
    f.write(request.content)
    print(f"... done.")

from ncon import ncon
```
## Sample contraction
!(tn.jpg)
```python
d=20
A = np.random.rand(d, d, d)
B = np.random.rand(d, d, d)
C = np.random.rand(d, d, d)
D = ncon([A, B, C], [[1, -2, 2], [-1, 1, 3], [3, 2, -3]], [1, 2, 3])
```
