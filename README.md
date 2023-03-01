# Consulta de API
 Codigo para realização de consulta de API, tratativa e criação de graficos.
 
 
 ```python
import requests
import json

cotacoes = requests.get('https://economia.awesomeapi.com.br/json/all')
cotacoes_dic = cotacoes.json()
print(cotacoes_dic)

```

 ```python
print('Dolar {}'.format(cotacoes_dic['USD']['bid']))
print('Euro {}'.format(cotacoes_dic['EUR']['bid']))
print('Bitcoin {}'.format(cotacoes_dic['BTC']['bid']))

Dolar 5.3291
Euro 5.1809
Bitcoin 102.836
```

 ```python
cotacoes_dolar30 = requests.get('https://economia.awesomeapi.com.br/json/daily/USD-BRL/30')
cotacoes_dolar30_dic = cotacoes_dolar30.json()
lista_cotacoes_dolar = [float(item['bid']) for item in cotacoes_dolar30_dic]
print(lista_cotacoes_dolar)

[5.2941, 5.2605, 5.293, 5.2929, 5.1881, 5.201, 5.2032, 5.2217, 5.1961, 5.1768, 5.1646, 5.4084, 5.3973, 5.376, 5.3791, 5.3906, 5.2599, 5.2633, 5.2625, 5.1171, 5.1716, 5.1425, 5.1723, 5.2541, 5.2486, 5.247, 5.1641, 5.1903, 5.093, 5.1465]
 ```
 
 
 ```python
import matplotlib.pyplot as plt
plt.figure(figsize=(15, 5))
plt.plot(cotacoes_btc)
plt.xlabel(15)
plt.ylabel(15)
plt.title('Grafico')
plt.show()
 ```
 
![image](https://user-images.githubusercontent.com/33934341/195917201-9fb38f3e-39df-4e28-b610-09221743e37d.png)
