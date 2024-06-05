```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```


```python
#Desplegando el DF completo solo usando el delimitador ";" y el encoding "utf-8" y "latin1" para que pueda hacer la lectura correcta del DF
try:
        df_nba = pd.read_csv("2022-2023 NBA Player Stats - Regular.csv", delimiter=';', encoding='utf-8')
except UnicodeDecodeError:
    df_nba = pd.read_csv("2022-2023 NBA Player Stats - Regular.csv", delimiter=';', encoding='latin1')
    
df_nba
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rk</th>
      <th>Player</th>
      <th>Pos</th>
      <th>Age</th>
      <th>Tm</th>
      <th>G</th>
      <th>GS</th>
      <th>MP</th>
      <th>FG</th>
      <th>FGA</th>
      <th>...</th>
      <th>FT%</th>
      <th>ORB</th>
      <th>DRB</th>
      <th>TRB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>TOV</th>
      <th>PF</th>
      <th>PTS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Precious Achiuwa</td>
      <td>C</td>
      <td>23</td>
      <td>TOR</td>
      <td>55</td>
      <td>12</td>
      <td>20.7</td>
      <td>3.6</td>
      <td>7.3</td>
      <td>...</td>
      <td>0.702</td>
      <td>1.8</td>
      <td>4.1</td>
      <td>6.0</td>
      <td>0.9</td>
      <td>0.6</td>
      <td>0.5</td>
      <td>1.1</td>
      <td>1.9</td>
      <td>9.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Steven Adams</td>
      <td>C</td>
      <td>29</td>
      <td>MEM</td>
      <td>42</td>
      <td>42</td>
      <td>27.0</td>
      <td>3.7</td>
      <td>6.3</td>
      <td>...</td>
      <td>0.364</td>
      <td>5.1</td>
      <td>6.5</td>
      <td>11.5</td>
      <td>2.3</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>1.9</td>
      <td>2.3</td>
      <td>8.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Bam Adebayo</td>
      <td>C</td>
      <td>25</td>
      <td>MIA</td>
      <td>75</td>
      <td>75</td>
      <td>34.6</td>
      <td>8.0</td>
      <td>14.9</td>
      <td>...</td>
      <td>0.806</td>
      <td>2.5</td>
      <td>6.7</td>
      <td>9.2</td>
      <td>3.2</td>
      <td>1.2</td>
      <td>0.8</td>
      <td>2.5</td>
      <td>2.8</td>
      <td>20.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Ochai Agbaji</td>
      <td>SG</td>
      <td>22</td>
      <td>UTA</td>
      <td>59</td>
      <td>22</td>
      <td>20.5</td>
      <td>2.8</td>
      <td>6.5</td>
      <td>...</td>
      <td>0.812</td>
      <td>0.7</td>
      <td>1.3</td>
      <td>2.1</td>
      <td>1.1</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.7</td>
      <td>1.7</td>
      <td>7.9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Santi Aldama</td>
      <td>PF</td>
      <td>22</td>
      <td>MEM</td>
      <td>77</td>
      <td>20</td>
      <td>21.8</td>
      <td>3.2</td>
      <td>6.8</td>
      <td>...</td>
      <td>0.750</td>
      <td>1.1</td>
      <td>3.7</td>
      <td>4.8</td>
      <td>1.3</td>
      <td>0.6</td>
      <td>0.6</td>
      <td>0.8</td>
      <td>1.9</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>674</th>
      <td>535</td>
      <td>Thaddeus Young</td>
      <td>PF</td>
      <td>34</td>
      <td>TOR</td>
      <td>54</td>
      <td>9</td>
      <td>14.7</td>
      <td>2.0</td>
      <td>3.7</td>
      <td>...</td>
      <td>0.692</td>
      <td>1.3</td>
      <td>1.8</td>
      <td>3.1</td>
      <td>1.4</td>
      <td>1.0</td>
      <td>0.1</td>
      <td>0.8</td>
      <td>1.6</td>
      <td>4.4</td>
    </tr>
    <tr>
      <th>675</th>
      <td>536</td>
      <td>Trae Young</td>
      <td>PG</td>
      <td>24</td>
      <td>ATL</td>
      <td>73</td>
      <td>73</td>
      <td>34.8</td>
      <td>8.2</td>
      <td>19.0</td>
      <td>...</td>
      <td>0.886</td>
      <td>0.8</td>
      <td>2.2</td>
      <td>3.0</td>
      <td>10.2</td>
      <td>1.1</td>
      <td>0.1</td>
      <td>4.1</td>
      <td>1.4</td>
      <td>26.2</td>
    </tr>
    <tr>
      <th>676</th>
      <td>537</td>
      <td>Omer Yurtseven</td>
      <td>C</td>
      <td>24</td>
      <td>MIA</td>
      <td>9</td>
      <td>0</td>
      <td>9.2</td>
      <td>1.8</td>
      <td>3.0</td>
      <td>...</td>
      <td>0.833</td>
      <td>0.9</td>
      <td>1.7</td>
      <td>2.6</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>0.4</td>
      <td>1.8</td>
      <td>4.4</td>
    </tr>
    <tr>
      <th>677</th>
      <td>538</td>
      <td>Cody Zeller</td>
      <td>C</td>
      <td>30</td>
      <td>MIA</td>
      <td>15</td>
      <td>2</td>
      <td>14.5</td>
      <td>2.5</td>
      <td>3.9</td>
      <td>...</td>
      <td>0.686</td>
      <td>1.7</td>
      <td>2.6</td>
      <td>4.3</td>
      <td>0.7</td>
      <td>0.2</td>
      <td>0.3</td>
      <td>0.9</td>
      <td>2.2</td>
      <td>6.5</td>
    </tr>
    <tr>
      <th>678</th>
      <td>539</td>
      <td>Ivica Zubac</td>
      <td>C</td>
      <td>25</td>
      <td>LAC</td>
      <td>76</td>
      <td>76</td>
      <td>28.6</td>
      <td>4.3</td>
      <td>6.8</td>
      <td>...</td>
      <td>0.697</td>
      <td>3.1</td>
      <td>6.8</td>
      <td>9.9</td>
      <td>1.0</td>
      <td>0.4</td>
      <td>1.3</td>
      <td>1.5</td>
      <td>2.9</td>
      <td>10.8</td>
    </tr>
  </tbody>
</table>
<p>679 rows × 30 columns</p>
</div>




```python
try:
        df_nba = pd.read_csv("2022-2023 NBA Player Stats - Regular.csv", delimiter=';', encoding='utf-8')
except UnicodeDecodeError:
    df_nba = pd.read_csv("2022-2023 NBA Player Stats - Regular.csv", delimiter=';', encoding='latin1')

# Estas tomando los filtros para que te despliegues solo los datos que requieres
col_statst = ['Player', 'Pos', 'Age', 'Tm', 'G', 'GS', 'MP', 'FG', 'FGA', '3PA', '3P%','2P','2PA','2P%','FT','FTA','FT%','ORB','DRB','TRB','AST','BLK','TOV','PF','PTS']

#Elige con las abreviaciones el equipo que quieres consultar. En este caso tomamos Golden State Warriors (GSW)
df_statst = df_nba[df_nba['Tm'] == 'GSW'][col_statst]

# Estamos calculando la suma por columnas y asi estamos obteniendo el total
col_sum = df_statst.select_dtypes(include='number').sum()

# Estamos calculando la media por columnas y agregando una nueva columna
df_statst.loc['Mean'] = df_statst.select_dtypes(include='number').mean()

# Aqui estamos agregando la columna del total tomando el col_sum que da la sumatoria de todos los campos numericos
df_statst.loc['Total'] = col_sum

# Desplegar el DataFrame
df_statst
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Player</th>
      <th>Pos</th>
      <th>Age</th>
      <th>Tm</th>
      <th>G</th>
      <th>GS</th>
      <th>MP</th>
      <th>FG</th>
      <th>FGA</th>
      <th>3PA</th>
      <th>...</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>ORB</th>
      <th>DRB</th>
      <th>TRB</th>
      <th>AST</th>
      <th>BLK</th>
      <th>TOV</th>
      <th>PF</th>
      <th>PTS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>23</th>
      <td>Patrick Baldwin Jr.</td>
      <td>SF</td>
      <td>20.000000</td>
      <td>GSW</td>
      <td>31.000000</td>
      <td>0.000000</td>
      <td>7.3</td>
      <td>1.400000</td>
      <td>3.500000</td>
      <td>2.700000</td>
      <td>...</td>
      <td>0.200000</td>
      <td>0.667000</td>
      <td>0.000000</td>
      <td>1.300000</td>
      <td>1.300000</td>
      <td>0.400000</td>
      <td>0.10</td>
      <td>0.400000</td>
      <td>0.500000</td>
      <td>3.900000</td>
    </tr>
    <tr>
      <th>139</th>
      <td>Stephen Curry</td>
      <td>PG</td>
      <td>34.000000</td>
      <td>GSW</td>
      <td>56.000000</td>
      <td>56.000000</td>
      <td>34.7</td>
      <td>10.000000</td>
      <td>20.200000</td>
      <td>11.400000</td>
      <td>...</td>
      <td>5.000000</td>
      <td>0.915000</td>
      <td>0.700000</td>
      <td>5.400000</td>
      <td>6.100000</td>
      <td>6.300000</td>
      <td>0.40</td>
      <td>3.200000</td>
      <td>2.100000</td>
      <td>29.400000</td>
    </tr>
    <tr>
      <th>159</th>
      <td>Donte DiVincenzo</td>
      <td>SG</td>
      <td>26.000000</td>
      <td>GSW</td>
      <td>72.000000</td>
      <td>36.000000</td>
      <td>26.3</td>
      <td>3.300000</td>
      <td>7.500000</td>
      <td>5.300000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>0.817000</td>
      <td>1.100000</td>
      <td>3.400000</td>
      <td>4.500000</td>
      <td>3.500000</td>
      <td>0.10</td>
      <td>1.600000</td>
      <td>1.800000</td>
      <td>9.400000</td>
    </tr>
    <tr>
      <th>227</th>
      <td>Draymond Green</td>
      <td>PF</td>
      <td>32.000000</td>
      <td>GSW</td>
      <td>73.000000</td>
      <td>73.000000</td>
      <td>31.5</td>
      <td>3.400000</td>
      <td>6.500000</td>
      <td>1.800000</td>
      <td>...</td>
      <td>1.500000</td>
      <td>0.713000</td>
      <td>0.900000</td>
      <td>6.300000</td>
      <td>7.200000</td>
      <td>6.800000</td>
      <td>0.80</td>
      <td>2.800000</td>
      <td>3.100000</td>
      <td>8.500000</td>
    </tr>
    <tr>
      <th>229</th>
      <td>JaMychal Green</td>
      <td>PF</td>
      <td>32.000000</td>
      <td>GSW</td>
      <td>57.000000</td>
      <td>1.000000</td>
      <td>14.0</td>
      <td>2.400000</td>
      <td>4.400000</td>
      <td>1.900000</td>
      <td>...</td>
      <td>1.200000</td>
      <td>0.776000</td>
      <td>1.300000</td>
      <td>2.300000</td>
      <td>3.600000</td>
      <td>0.900000</td>
      <td>0.40</td>
      <td>0.900000</td>
      <td>1.800000</td>
      <td>6.400000</td>
    </tr>
    <tr>
      <th>290</th>
      <td>Andre Iguodala</td>
      <td>SF</td>
      <td>39.000000</td>
      <td>GSW</td>
      <td>8.000000</td>
      <td>0.000000</td>
      <td>14.1</td>
      <td>0.900000</td>
      <td>1.900000</td>
      <td>1.100000</td>
      <td>...</td>
      <td>0.400000</td>
      <td>0.667000</td>
      <td>0.400000</td>
      <td>1.800000</td>
      <td>2.100000</td>
      <td>2.400000</td>
      <td>0.40</td>
      <td>1.100000</td>
      <td>1.400000</td>
      <td>2.100000</td>
    </tr>
    <tr>
      <th>307</th>
      <td>Ty Jerome</td>
      <td>SG</td>
      <td>25.000000</td>
      <td>GSW</td>
      <td>45.000000</td>
      <td>2.000000</td>
      <td>18.1</td>
      <td>2.600000</td>
      <td>5.400000</td>
      <td>2.000000</td>
      <td>...</td>
      <td>0.900000</td>
      <td>0.927000</td>
      <td>0.200000</td>
      <td>1.600000</td>
      <td>1.700000</td>
      <td>3.000000</td>
      <td>0.10</td>
      <td>0.700000</td>
      <td>1.400000</td>
      <td>6.900000</td>
    </tr>
    <tr>
      <th>354</th>
      <td>Jonathan Kuminga</td>
      <td>PF</td>
      <td>20.000000</td>
      <td>GSW</td>
      <td>67.000000</td>
      <td>16.000000</td>
      <td>20.8</td>
      <td>3.900000</td>
      <td>7.400000</td>
      <td>2.200000</td>
      <td>...</td>
      <td>2.100000</td>
      <td>0.652000</td>
      <td>1.000000</td>
      <td>2.400000</td>
      <td>3.400000</td>
      <td>1.900000</td>
      <td>0.50</td>
      <td>1.400000</td>
      <td>2.300000</td>
      <td>9.900000</td>
    </tr>
    <tr>
      <th>356</th>
      <td>Anthony Lamb</td>
      <td>SF</td>
      <td>25.000000</td>
      <td>GSW</td>
      <td>62.000000</td>
      <td>4.000000</td>
      <td>19.3</td>
      <td>2.400000</td>
      <td>5.100000</td>
      <td>3.200000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>0.767000</td>
      <td>0.900000</td>
      <td>2.600000</td>
      <td>3.500000</td>
      <td>1.500000</td>
      <td>0.30</td>
      <td>0.900000</td>
      <td>2.200000</td>
      <td>6.700000</td>
    </tr>
    <tr>
      <th>377</th>
      <td>Kevon Looney</td>
      <td>C</td>
      <td>26.000000</td>
      <td>GSW</td>
      <td>82.000000</td>
      <td>70.000000</td>
      <td>23.9</td>
      <td>3.000000</td>
      <td>4.700000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>1.900000</td>
      <td>0.606000</td>
      <td>3.300000</td>
      <td>5.900000</td>
      <td>9.300000</td>
      <td>2.500000</td>
      <td>0.60</td>
      <td>0.500000</td>
      <td>2.700000</td>
      <td>7.000000</td>
    </tr>
    <tr>
      <th>432</th>
      <td>Moses Moody</td>
      <td>SG</td>
      <td>20.000000</td>
      <td>GSW</td>
      <td>63.000000</td>
      <td>3.000000</td>
      <td>13.0</td>
      <td>1.700000</td>
      <td>3.600000</td>
      <td>2.100000</td>
      <td>...</td>
      <td>0.800000</td>
      <td>0.698000</td>
      <td>0.400000</td>
      <td>1.200000</td>
      <td>1.700000</td>
      <td>0.800000</td>
      <td>0.10</td>
      <td>0.500000</td>
      <td>0.900000</td>
      <td>4.800000</td>
    </tr>
    <tr>
      <th>487</th>
      <td>Gary Payton II</td>
      <td>PG</td>
      <td>30.000000</td>
      <td>GSW</td>
      <td>7.000000</td>
      <td>0.000000</td>
      <td>16.0</td>
      <td>2.400000</td>
      <td>4.000000</td>
      <td>1.300000</td>
      <td>...</td>
      <td>0.400000</td>
      <td>0.667000</td>
      <td>2.000000</td>
      <td>2.300000</td>
      <td>4.300000</td>
      <td>1.100000</td>
      <td>0.60</td>
      <td>0.600000</td>
      <td>2.000000</td>
      <td>5.700000</td>
    </tr>
    <tr>
      <th>497</th>
      <td>Jordan Poole</td>
      <td>PG</td>
      <td>23.000000</td>
      <td>GSW</td>
      <td>82.000000</td>
      <td>43.000000</td>
      <td>30.0</td>
      <td>6.700000</td>
      <td>15.600000</td>
      <td>7.800000</td>
      <td>...</td>
      <td>5.100000</td>
      <td>0.870000</td>
      <td>0.400000</td>
      <td>2.400000</td>
      <td>2.700000</td>
      <td>4.500000</td>
      <td>0.30</td>
      <td>3.100000</td>
      <td>2.600000</td>
      <td>20.400000</td>
    </tr>
    <tr>
      <th>513</th>
      <td>Lester Quinones</td>
      <td>SG</td>
      <td>22.000000</td>
      <td>GSW</td>
      <td>4.000000</td>
      <td>0.000000</td>
      <td>4.5</td>
      <td>0.500000</td>
      <td>1.300000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>1.500000</td>
      <td>0.667000</td>
      <td>0.300000</td>
      <td>0.500000</td>
      <td>0.800000</td>
      <td>0.500000</td>
      <td>0.00</td>
      <td>1.300000</td>
      <td>0.000000</td>
      <td>2.500000</td>
    </tr>
    <tr>
      <th>536</th>
      <td>Ryan Rollins</td>
      <td>PG</td>
      <td>20.000000</td>
      <td>GSW</td>
      <td>12.000000</td>
      <td>0.000000</td>
      <td>5.2</td>
      <td>0.600000</td>
      <td>1.700000</td>
      <td>0.800000</td>
      <td>...</td>
      <td>0.500000</td>
      <td>1.000000</td>
      <td>0.300000</td>
      <td>0.800000</td>
      <td>1.000000</td>
      <td>0.500000</td>
      <td>0.10</td>
      <td>1.300000</td>
      <td>0.800000</td>
      <td>1.900000</td>
    </tr>
    <tr>
      <th>598</th>
      <td>Klay Thompson</td>
      <td>SG</td>
      <td>32.000000</td>
      <td>GSW</td>
      <td>69.000000</td>
      <td>69.000000</td>
      <td>33.0</td>
      <td>7.900000</td>
      <td>18.100000</td>
      <td>10.600000</td>
      <td>...</td>
      <td>1.900000</td>
      <td>0.879000</td>
      <td>0.600000</td>
      <td>3.600000</td>
      <td>4.100000</td>
      <td>2.400000</td>
      <td>0.40</td>
      <td>1.800000</td>
      <td>1.900000</td>
      <td>21.900000</td>
    </tr>
    <tr>
      <th>650</th>
      <td>Andrew Wiggins</td>
      <td>SF</td>
      <td>27.000000</td>
      <td>GSW</td>
      <td>37.000000</td>
      <td>37.000000</td>
      <td>32.2</td>
      <td>6.800000</td>
      <td>14.300000</td>
      <td>6.100000</td>
      <td>...</td>
      <td>1.900000</td>
      <td>0.611000</td>
      <td>1.600000</td>
      <td>3.400000</td>
      <td>5.000000</td>
      <td>2.300000</td>
      <td>0.80</td>
      <td>1.300000</td>
      <td>2.900000</td>
      <td>17.100000</td>
    </tr>
    <tr>
      <th>668</th>
      <td>James Wiseman</td>
      <td>C</td>
      <td>21.000000</td>
      <td>GSW</td>
      <td>21.000000</td>
      <td>0.000000</td>
      <td>12.5</td>
      <td>2.800000</td>
      <td>4.500000</td>
      <td>0.100000</td>
      <td>...</td>
      <td>1.800000</td>
      <td>0.684000</td>
      <td>0.900000</td>
      <td>2.600000</td>
      <td>3.500000</td>
      <td>0.700000</td>
      <td>0.30</td>
      <td>0.700000</td>
      <td>1.900000</td>
      <td>6.900000</td>
    </tr>
    <tr>
      <th>Mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>26.333333</td>
      <td>NaN</td>
      <td>47.111111</td>
      <td>22.777778</td>
      <td>19.8</td>
      <td>3.483333</td>
      <td>7.205556</td>
      <td>3.411111</td>
      <td>...</td>
      <td>1.616667</td>
      <td>0.754611</td>
      <td>0.905556</td>
      <td>2.766667</td>
      <td>3.655556</td>
      <td>2.333333</td>
      <td>0.35</td>
      <td>1.338889</td>
      <td>1.794444</td>
      <td>9.522222</td>
    </tr>
    <tr>
      <th>Total</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>474.000000</td>
      <td>NaN</td>
      <td>848.000000</td>
      <td>410.000000</td>
      <td>356.4</td>
      <td>62.700000</td>
      <td>129.700000</td>
      <td>61.400000</td>
      <td>...</td>
      <td>29.100000</td>
      <td>13.583000</td>
      <td>16.300000</td>
      <td>49.800000</td>
      <td>65.800000</td>
      <td>42.000000</td>
      <td>6.30</td>
      <td>24.100000</td>
      <td>32.300000</td>
      <td>171.400000</td>
    </tr>
  </tbody>
</table>
<p>20 rows × 25 columns</p>
</div>




```python
#Tomamos del df_nba las posiciones de la liga.
df_pos = df_nba[df_nba['Pos'].isin(['PG', 'SG', 'PF', 'C', 'SF','PF-SF','SF-SG', 'SG-PG'])]

#Contamos los valores de 'Pos'
count = df_pos['Pos'].value_counts()

#Sacamos el porcentage
percentage = (count / len(df_pos)) * 100

#Desplegamos el DF el cual indicara la posicion, frecuencia absoluta y porcentage
df_freq_rel = pd.DataFrame({'Posición': count.index, 'Frecuencia': count.values, 'Porcentaje (%)': percentage.values})

#Desplegamos los valores de mayor a menor.
df_freq_rel = df_freq_rel.sort_values(by='Frecuencia', ascending=False)

#Calculamos el número total de filas en df_pos y guarda este valor en la variable 'total'
total = df_pos.shape[0]

#Agregamos una nueva fila al final de df_freq_rel con los valores ['Total', total, 100].
df_freq_rel.loc['Total'] = ['Total', total, 100]

#Desplegamos el DF
df_freq_rel
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Posición</th>
      <th>Frecuencia</th>
      <th>Porcentaje (%)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>SG</td>
      <td>168</td>
      <td>24.742268</td>
    </tr>
    <tr>
      <th>1</th>
      <td>PG</td>
      <td>135</td>
      <td>19.882180</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>129</td>
      <td>18.998527</td>
    </tr>
    <tr>
      <th>3</th>
      <td>SF</td>
      <td>125</td>
      <td>18.409426</td>
    </tr>
    <tr>
      <th>4</th>
      <td>PF</td>
      <td>117</td>
      <td>17.231222</td>
    </tr>
    <tr>
      <th>5</th>
      <td>PF-SF</td>
      <td>3</td>
      <td>0.441826</td>
    </tr>
    <tr>
      <th>6</th>
      <td>SF-SG</td>
      <td>1</td>
      <td>0.147275</td>
    </tr>
    <tr>
      <th>7</th>
      <td>SG-PG</td>
      <td>1</td>
      <td>0.147275</td>
    </tr>
    <tr>
      <th>Total</th>
      <td>Total</td>
      <td>679</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>



Con esta informacion podemos identificar la cantidad de jugadores por posiciones dentro de la liga durante la temporada 2022-2023.

Por otra parte, podemos ver que existen posiciones como 'PF-SF', 'SF-SG' y 'SG-PG' las cuales estan catalogada para jugadores que pueden abarcar ambas posiciones, por lo tanto, se desglosan a parte.


```python
import pandas as pd

# Leemos otro CSV el cual tiene la informacion de todos los resultados de los partidos sean 'home' o 'away'
try:
    df_nbast = pd.read_csv("game2 - game (1).csv")
except UnicodeDecodeError:
    df_nbast = pd.read_csv("game2 - game (1).csv")

# Seleccionamos solo las columnas necesarias
cols_res = ['game_date', 'team_name_home', 'pts_home', 'team_name_away', 'pts_away']
df_res = df_nbast[cols_res]

# Convertir la columna de fechas a tipo datetime
df_res['game_date'] = pd.to_datetime(df_res['game_date'])

# Filtrar las fechas para el rango deseado. Estas fechas son las que abarcan la temporada regular.
start_date = '2022-10-01'
end_date = '2023-12-31'
filtered_df = df_res[(df_res['game_date'] >= start_date) & (df_res['game_date'] <= end_date)]

# Contar el número de juegos en los que cada equipo jugó como local y como visitante
home_games_count = filtered_df['team_name_home'].value_counts()
away_games_count = filtered_df['team_name_away'].value_counts()

print("Número de juegos en casa por equipo:")
print(home_games_count)

print("\nNúmero de juegos fuera de casa por equipo:")
print(away_games_count)
```

    Número de juegos en casa por equipo:
    team_name_home
    Boston Celtics            41
    Golden State Warriors     41
    New Orleans Pelicans      41
    LA Clippers               41
    Oklahoma City Thunder     41
    Denver Nuggets            41
    Orlando Magic             41
    Milwaukee Bucks           41
    Chicago Bulls             41
    Dallas Mavericks          41
    Washington Wizards        41
    New York Knicks           41
    Charlotte Hornets         41
    Portland Trail Blazers    41
    Houston Rockets           41
    Los Angeles Lakers        41
    Philadelphia 76ers        41
    Atlanta Hawks             41
    Miami Heat                41
    Memphis Grizzlies         41
    Toronto Raptors           41
    Minnesota Timberwolves    41
    San Antonio Spurs         41
    Phoenix Suns              41
    Sacramento Kings          41
    Indiana Pacers            41
    Brooklyn Nets             41
    Utah Jazz                 41
    Detroit Pistons           41
    Cleveland Cavaliers       41
    Name: count, dtype: int64
    
    Número de juegos fuera de casa por equipo:
    team_name_away
    Philadelphia 76ers        41
    Los Angeles Lakers        41
    Miami Heat                41
    Golden State Warriors     41
    Brooklyn Nets             41
    Indiana Pacers            41
    Sacramento Kings          41
    Minnesota Timberwolves    41
    Boston Celtics            41
    Detroit Pistons           41
    San Antonio Spurs         41
    Utah Jazz                 41
    Phoenix Suns              41
    Toronto Raptors           41
    Memphis Grizzlies         41
    LA Clippers               41
    Milwaukee Bucks           41
    Houston Rockets           41
    Chicago Bulls             41
    New York Knicks           41
    Cleveland Cavaliers       41
    Oklahoma City Thunder     41
    Charlotte Hornets         41
    Dallas Mavericks          41
    Portland Trail Blazers    41
    Washington Wizards        41
    New Orleans Pelicans      41
    Denver Nuggets            41
    Orlando Magic             41
    Atlanta Hawks             41
    Name: count, dtype: int64


    /var/folders/x4/0c15_f2j2y1381db2_6zgnwr0000gn/T/ipykernel_2977/2634263741.py:14: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df_res['game_date'] = pd.to_datetime(df_res['game_date'])



```python
import pandas as pd

# Leemos otro CSV el cual tiene la informacion de todos los resultados de los partidos sean 'home' o 'away'
try:
    df_nbast = pd.read_csv("game 2 final - game 2.csv")
except UnicodeDecodeError:
    df_nbast = pd.read_csv("game 2 final - game 2.csv")

# Seleccionamos solo las columnas necesarias
cols_res = [
    'game_date', 'team_name_home', 'pts_home', 'team_name_away', 'pts_away',
    'oreb_home', 'dreb_home', 'reb_home', 'ast_home', 'stl_home', 'blk_home', 'tov_home', 'pf_home',
    'oreb_away', 'dreb_away', 'reb_away', 'ast_away', 'stl_away', 'blk_away', 'tov_away', 'pf_away',
    'fgm_home', 'fga_home', 'fg_pct_home', 'fg3m_home', 'fg3a_home', 'fg3_pct_home', 'ftm_home', 'fta_home', 'ft_pct_home',
    'fgm_away', 'fga_away', 'fg_pct_away', 'fg3m_away', 'fg3a_away', 'fg3_pct_away', 'ftm_away', 'fta_away', 'ft_pct_away'
]
df_res = df_nbast[cols_res]

# Convertir la columna de fechas a tipo datetime
df_res['game_date'] = pd.to_datetime(df_res['game_date'])

# Filtrar las fechas para el rango deseado. Estas fechas son las que abarcan la temporada regular.
start_date = '2022-10-01'
end_date = '2023-12-31'
filtered_df = df_res[(df_res['game_date'] >= start_date) & (df_res['game_date'] <= end_date)]

# Contar el número de juegos en los que cada equipo jugó como local y como visitante
home_games_count = filtered_df['team_name_home'].value_counts()
away_games_count = filtered_df['team_name_away'].value_counts()

# Calcular los puntos totales por equipo
total_team_points = filtered_df.groupby('team_name_home')['pts_home'].sum() + filtered_df.groupby('team_name_away')['pts_away'].sum()

# Calcular el número total de partidos jugados por cada equipo
total_games_played = home_games_count.add(away_games_count, fill_value=0)

# Calcular la media de puntos por partido para cada equipo
average_points_per_game = total_team_points / total_games_played

# Sumar las estadísticas de casa y fuera de casa para cada equipo y calcular el promedio
stats = ['oreb', 'dreb', 'reb', 'ast', 'stl', 'blk', 'tov', 'pf', 'fgm', 'fga', 'fg3m', 'fg3a', 'ftm', 'fta']
team_stats = {}
for stat in stats:
    home_stat = filtered_df.groupby('team_name_home')[f'{stat}_home'].sum()
    away_stat = filtered_df.groupby('team_name_away')[f'{stat}_away'].sum()
    total_stat = home_stat.add(away_stat, fill_value=0)
    team_stats[stat] = total_stat / total_games_played

# Crear un DataFrame para mostrar los resultados
result_df = pd.DataFrame({'Team': average_points_per_game.index, 'Average Points Per Game': average_points_per_game.values})

# Agregar las estadísticas adicionales al DataFrame
for stat in stats:
    result_df[f'Average {stat.upper()} Per Game'] = team_stats[stat].values

# Calcular los porcentajes
result_df['Average FG%'] = (result_df['Average FGM Per Game'] / result_df['Average FGA Per Game']) * 100
result_df['Average FG3%'] = (result_df['Average FG3M Per Game'] / result_df['Average FG3A Per Game']) * 100
result_df['Average FT%'] = (result_df['Average FTM Per Game'] / result_df['Average FTA Per Game']) * 100

# Remover los equipos especificados
teams_to_remove = ['Adelaide 36ers', 'Ra\'anana Maccabi Ra\'anana', 'Team Giannis', 'Team LeBron']
result_df = result_df[~result_df['Team'].isin(teams_to_remove)]

# Resetear el índice para que comience desde 0
result_df.reset_index(drop=True, inplace=True)

# Mostrar el DataFrame con los promedios de puntos por partido y las estadísticas adicionales
result_df
```

    /var/folders/x4/0c15_f2j2y1381db2_6zgnwr0000gn/T/ipykernel_2977/26051152.py:20: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df_res['game_date'] = pd.to_datetime(df_res['game_date'])





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Team</th>
      <th>Average Points Per Game</th>
      <th>Average OREB Per Game</th>
      <th>Average DREB Per Game</th>
      <th>Average REB Per Game</th>
      <th>Average AST Per Game</th>
      <th>Average STL Per Game</th>
      <th>Average BLK Per Game</th>
      <th>Average TOV Per Game</th>
      <th>Average PF Per Game</th>
      <th>Average FGM Per Game</th>
      <th>Average FGA Per Game</th>
      <th>Average FG3M Per Game</th>
      <th>Average FG3A Per Game</th>
      <th>Average FTM Per Game</th>
      <th>Average FTA Per Game</th>
      <th>Average FG%</th>
      <th>Average FG3%</th>
      <th>Average FT%</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Atlanta Hawks</td>
      <td>118.426829</td>
      <td>11.219512</td>
      <td>33.158537</td>
      <td>44.378049</td>
      <td>24.987805</td>
      <td>7.073171</td>
      <td>4.890244</td>
      <td>12.926829</td>
      <td>18.792683</td>
      <td>44.609756</td>
      <td>92.365854</td>
      <td>10.756098</td>
      <td>30.548780</td>
      <td>18.451220</td>
      <td>22.560976</td>
      <td>48.296805</td>
      <td>35.209581</td>
      <td>81.783784</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Boston Celtics</td>
      <td>117.939024</td>
      <td>9.707317</td>
      <td>35.621951</td>
      <td>45.329268</td>
      <td>26.658537</td>
      <td>6.353659</td>
      <td>5.243902</td>
      <td>13.353659</td>
      <td>18.804878</td>
      <td>42.195122</td>
      <td>88.756098</td>
      <td>16.036585</td>
      <td>42.585366</td>
      <td>17.512195</td>
      <td>21.573171</td>
      <td>47.540533</td>
      <td>37.657503</td>
      <td>81.175806</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Brooklyn Nets</td>
      <td>113.353659</td>
      <td>8.219512</td>
      <td>32.292683</td>
      <td>40.512195</td>
      <td>25.524390</td>
      <td>7.134146</td>
      <td>6.170732</td>
      <td>13.743902</td>
      <td>21.097561</td>
      <td>41.451220</td>
      <td>85.097561</td>
      <td>12.780488</td>
      <td>33.792683</td>
      <td>17.670732</td>
      <td>22.085366</td>
      <td>48.710232</td>
      <td>37.820281</td>
      <td>80.011044</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Charlotte Hornets</td>
      <td>110.951220</td>
      <td>10.987805</td>
      <td>33.548780</td>
      <td>44.536585</td>
      <td>25.146341</td>
      <td>7.731707</td>
      <td>5.182927</td>
      <td>14.195122</td>
      <td>20.256098</td>
      <td>41.280488</td>
      <td>90.402439</td>
      <td>10.743902</td>
      <td>32.548780</td>
      <td>17.646341</td>
      <td>23.573171</td>
      <td>45.663024</td>
      <td>33.008617</td>
      <td>74.857734</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Chicago Bulls</td>
      <td>113.121951</td>
      <td>8.463415</td>
      <td>33.890244</td>
      <td>42.353659</td>
      <td>24.463415</td>
      <td>7.853659</td>
      <td>4.524390</td>
      <td>13.378049</td>
      <td>18.914634</td>
      <td>42.536585</td>
      <td>86.780488</td>
      <td>10.414634</td>
      <td>28.865854</td>
      <td>17.634146</td>
      <td>21.804878</td>
      <td>49.016301</td>
      <td>36.079425</td>
      <td>80.872483</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cleveland Cavaliers</td>
      <td>112.256098</td>
      <td>9.695122</td>
      <td>31.390244</td>
      <td>41.085366</td>
      <td>24.939024</td>
      <td>7.146341</td>
      <td>4.682927</td>
      <td>13.341463</td>
      <td>19.024390</td>
      <td>41.560976</td>
      <td>85.170732</td>
      <td>11.585366</td>
      <td>31.573171</td>
      <td>17.548780</td>
      <td>22.487805</td>
      <td>48.797251</td>
      <td>36.693704</td>
      <td>78.036876</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Dallas Mavericks</td>
      <td>114.219512</td>
      <td>7.621951</td>
      <td>31.170732</td>
      <td>38.792683</td>
      <td>22.926829</td>
      <td>6.268293</td>
      <td>3.707317</td>
      <td>12.219512</td>
      <td>20.695122</td>
      <td>40.036585</td>
      <td>84.256098</td>
      <td>15.195122</td>
      <td>41.000000</td>
      <td>18.951220</td>
      <td>25.085366</td>
      <td>47.517730</td>
      <td>37.061273</td>
      <td>75.546913</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Denver Nuggets</td>
      <td>115.792683</td>
      <td>10.097561</td>
      <td>32.914634</td>
      <td>43.012195</td>
      <td>28.878049</td>
      <td>7.536585</td>
      <td>4.487805</td>
      <td>14.536585</td>
      <td>18.597561</td>
      <td>43.585366</td>
      <td>86.439024</td>
      <td>11.817073</td>
      <td>31.207317</td>
      <td>16.804878</td>
      <td>22.365854</td>
      <td>50.423251</td>
      <td>37.866354</td>
      <td>75.136314</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Detroit Pistons</td>
      <td>110.304878</td>
      <td>11.170732</td>
      <td>31.268293</td>
      <td>42.439024</td>
      <td>22.975610</td>
      <td>7.000000</td>
      <td>3.756098</td>
      <td>15.085366</td>
      <td>22.109756</td>
      <td>39.560976</td>
      <td>87.073171</td>
      <td>11.390244</td>
      <td>32.426829</td>
      <td>19.792683</td>
      <td>25.682927</td>
      <td>45.434174</td>
      <td>35.125987</td>
      <td>77.065527</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Golden State Warriors</td>
      <td>118.939024</td>
      <td>10.536585</td>
      <td>34.060976</td>
      <td>44.597561</td>
      <td>29.829268</td>
      <td>7.170732</td>
      <td>3.939024</td>
      <td>16.292683</td>
      <td>21.426829</td>
      <td>43.146341</td>
      <td>90.158537</td>
      <td>16.621951</td>
      <td>43.170732</td>
      <td>16.024390</td>
      <td>20.182927</td>
      <td>47.856080</td>
      <td>38.502825</td>
      <td>79.395770</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Houston Rockets</td>
      <td>110.743902</td>
      <td>13.414634</td>
      <td>32.865854</td>
      <td>46.280488</td>
      <td>22.378049</td>
      <td>7.317073</td>
      <td>4.560976</td>
      <td>16.243902</td>
      <td>20.475610</td>
      <td>40.597561</td>
      <td>88.865854</td>
      <td>10.439024</td>
      <td>31.939024</td>
      <td>19.109756</td>
      <td>25.341463</td>
      <td>45.684095</td>
      <td>32.684231</td>
      <td>75.409047</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Indiana Pacers</td>
      <td>116.280488</td>
      <td>10.146341</td>
      <td>31.402439</td>
      <td>41.548780</td>
      <td>26.987805</td>
      <td>7.695122</td>
      <td>5.829268</td>
      <td>14.926829</td>
      <td>21.231707</td>
      <td>42.000000</td>
      <td>89.573171</td>
      <td>13.560976</td>
      <td>36.951220</td>
      <td>18.719512</td>
      <td>23.707317</td>
      <td>46.889040</td>
      <td>36.699670</td>
      <td>78.960905</td>
    </tr>
    <tr>
      <th>12</th>
      <td>LA Clippers</td>
      <td>113.585366</td>
      <td>9.792683</td>
      <td>33.439024</td>
      <td>43.231707</td>
      <td>23.890244</td>
      <td>7.073171</td>
      <td>4.439024</td>
      <td>14.231707</td>
      <td>19.487805</td>
      <td>41.097561</td>
      <td>86.085366</td>
      <td>12.695122</td>
      <td>33.353659</td>
      <td>18.695122</td>
      <td>23.926829</td>
      <td>47.740473</td>
      <td>38.062157</td>
      <td>78.134557</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Los Angeles Lakers</td>
      <td>117.170732</td>
      <td>9.975610</td>
      <td>35.731707</td>
      <td>45.707317</td>
      <td>25.268293</td>
      <td>6.414634</td>
      <td>4.609756</td>
      <td>14.073171</td>
      <td>17.878049</td>
      <td>42.878049</td>
      <td>89.000000</td>
      <td>10.792683</td>
      <td>31.195122</td>
      <td>20.621951</td>
      <td>26.609756</td>
      <td>48.177583</td>
      <td>34.597342</td>
      <td>77.497709</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Memphis Grizzlies</td>
      <td>116.914634</td>
      <td>12.048780</td>
      <td>34.573171</td>
      <td>46.621951</td>
      <td>26.036585</td>
      <td>8.292683</td>
      <td>5.768293</td>
      <td>13.609756</td>
      <td>20.036585</td>
      <td>43.719512</td>
      <td>92.085366</td>
      <td>12.012195</td>
      <td>34.231707</td>
      <td>17.463415</td>
      <td>23.829268</td>
      <td>47.477155</td>
      <td>35.090844</td>
      <td>73.285568</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Miami Heat</td>
      <td>109.475610</td>
      <td>9.707317</td>
      <td>30.890244</td>
      <td>40.597561</td>
      <td>23.841463</td>
      <td>7.987805</td>
      <td>2.963415</td>
      <td>13.487805</td>
      <td>18.487805</td>
      <td>39.207317</td>
      <td>85.256098</td>
      <td>11.951220</td>
      <td>34.780488</td>
      <td>19.109756</td>
      <td>22.987805</td>
      <td>45.987698</td>
      <td>34.361851</td>
      <td>83.129973</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Milwaukee Bucks</td>
      <td>116.939024</td>
      <td>11.146341</td>
      <td>37.487805</td>
      <td>48.634146</td>
      <td>25.792683</td>
      <td>6.353659</td>
      <td>4.914634</td>
      <td>14.621951</td>
      <td>18.060976</td>
      <td>42.731707</td>
      <td>90.378049</td>
      <td>14.841463</td>
      <td>40.317073</td>
      <td>16.634146</td>
      <td>22.402439</td>
      <td>47.281069</td>
      <td>36.811857</td>
      <td>74.251497</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Minnesota Timberwolves</td>
      <td>115.780488</td>
      <td>9.134146</td>
      <td>32.756098</td>
      <td>41.890244</td>
      <td>26.158537</td>
      <td>8.012195</td>
      <td>5.414634</td>
      <td>15.341463</td>
      <td>21.560976</td>
      <td>42.865854</td>
      <td>87.402439</td>
      <td>12.158537</td>
      <td>33.304878</td>
      <td>17.890244</td>
      <td>23.682927</td>
      <td>49.044231</td>
      <td>36.506774</td>
      <td>75.540680</td>
    </tr>
    <tr>
      <th>18</th>
      <td>New Orleans Pelicans</td>
      <td>114.365854</td>
      <td>10.560976</td>
      <td>33.134146</td>
      <td>43.695122</td>
      <td>25.878049</td>
      <td>8.304878</td>
      <td>4.109756</td>
      <td>14.585366</td>
      <td>20.463415</td>
      <td>42.036585</td>
      <td>87.560976</td>
      <td>10.963415</td>
      <td>30.097561</td>
      <td>19.329268</td>
      <td>24.390244</td>
      <td>48.008357</td>
      <td>36.426256</td>
      <td>79.250000</td>
    </tr>
    <tr>
      <th>19</th>
      <td>New York Knicks</td>
      <td>116.024390</td>
      <td>12.573171</td>
      <td>34.024390</td>
      <td>46.597561</td>
      <td>22.926829</td>
      <td>6.426829</td>
      <td>4.146341</td>
      <td>12.987805</td>
      <td>20.317073</td>
      <td>42.000000</td>
      <td>89.365854</td>
      <td>12.646341</td>
      <td>35.731707</td>
      <td>19.378049</td>
      <td>25.451220</td>
      <td>46.997817</td>
      <td>35.392491</td>
      <td>76.137997</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Oklahoma City Thunder</td>
      <td>117.475610</td>
      <td>11.390244</td>
      <td>32.256098</td>
      <td>43.646341</td>
      <td>24.414634</td>
      <td>8.243902</td>
      <td>4.158537</td>
      <td>13.036585</td>
      <td>21.000000</td>
      <td>43.085366</td>
      <td>92.560976</td>
      <td>12.134146</td>
      <td>34.109756</td>
      <td>19.170732</td>
      <td>23.707317</td>
      <td>46.548090</td>
      <td>35.573829</td>
      <td>80.864198</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Orlando Magic</td>
      <td>111.414634</td>
      <td>10.158537</td>
      <td>33.085366</td>
      <td>43.243902</td>
      <td>23.243902</td>
      <td>7.353659</td>
      <td>4.658537</td>
      <td>15.073171</td>
      <td>20.146341</td>
      <td>40.524390</td>
      <td>86.268293</td>
      <td>10.768293</td>
      <td>31.109756</td>
      <td>19.597561</td>
      <td>25.000000</td>
      <td>46.974837</td>
      <td>34.613877</td>
      <td>78.390244</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Philadelphia 76ers</td>
      <td>115.219512</td>
      <td>8.719512</td>
      <td>32.207317</td>
      <td>40.926829</td>
      <td>25.158537</td>
      <td>7.743902</td>
      <td>4.743902</td>
      <td>13.670732</td>
      <td>20.426829</td>
      <td>40.817073</td>
      <td>83.780488</td>
      <td>12.621951</td>
      <td>32.621951</td>
      <td>20.963415</td>
      <td>25.097561</td>
      <td>48.719068</td>
      <td>38.691589</td>
      <td>83.527697</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Phoenix Suns</td>
      <td>113.646341</td>
      <td>11.841463</td>
      <td>32.402439</td>
      <td>44.243902</td>
      <td>27.256098</td>
      <td>7.134146</td>
      <td>5.268293</td>
      <td>13.536585</td>
      <td>21.207317</td>
      <td>42.109756</td>
      <td>90.097561</td>
      <td>12.207317</td>
      <td>32.609756</td>
      <td>17.219512</td>
      <td>21.719512</td>
      <td>46.737953</td>
      <td>37.434555</td>
      <td>79.281303</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Portland Trail Blazers</td>
      <td>113.402439</td>
      <td>9.439024</td>
      <td>31.109756</td>
      <td>40.548780</td>
      <td>24.158537</td>
      <td>6.743902</td>
      <td>4.585366</td>
      <td>14.451220</td>
      <td>20.036585</td>
      <td>40.451220</td>
      <td>85.378049</td>
      <td>12.878049</td>
      <td>35.280488</td>
      <td>19.621951</td>
      <td>24.646341</td>
      <td>47.378946</td>
      <td>36.501901</td>
      <td>79.614052</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Sacramento Kings</td>
      <td>120.707317</td>
      <td>9.536585</td>
      <td>32.914634</td>
      <td>42.451220</td>
      <td>27.280488</td>
      <td>7.000000</td>
      <td>3.353659</td>
      <td>13.487805</td>
      <td>19.707317</td>
      <td>43.573171</td>
      <td>88.195122</td>
      <td>13.756098</td>
      <td>37.317073</td>
      <td>19.804878</td>
      <td>25.060976</td>
      <td>49.405420</td>
      <td>36.862745</td>
      <td>79.026764</td>
    </tr>
    <tr>
      <th>26</th>
      <td>San Antonio Spurs</td>
      <td>113.036585</td>
      <td>11.768293</td>
      <td>31.939024</td>
      <td>43.707317</td>
      <td>27.219512</td>
      <td>6.975610</td>
      <td>3.926829</td>
      <td>15.280488</td>
      <td>19.878049</td>
      <td>43.085366</td>
      <td>92.597561</td>
      <td>11.109756</td>
      <td>32.195122</td>
      <td>15.756098</td>
      <td>21.207317</td>
      <td>46.529698</td>
      <td>34.507576</td>
      <td>74.295572</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Toronto Raptors</td>
      <td>112.853659</td>
      <td>12.719512</td>
      <td>30.304878</td>
      <td>43.024390</td>
      <td>23.914634</td>
      <td>9.414634</td>
      <td>5.170732</td>
      <td>11.658537</td>
      <td>20.012195</td>
      <td>41.878049</td>
      <td>91.329268</td>
      <td>10.731707</td>
      <td>32.024390</td>
      <td>18.365854</td>
      <td>23.439024</td>
      <td>45.853919</td>
      <td>33.511043</td>
      <td>78.355879</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Utah Jazz</td>
      <td>117.073171</td>
      <td>11.804878</td>
      <td>34.073171</td>
      <td>45.878049</td>
      <td>25.963415</td>
      <td>6.097561</td>
      <td>5.231707</td>
      <td>15.353659</td>
      <td>20.475610</td>
      <td>42.500000</td>
      <td>89.817073</td>
      <td>13.341463</td>
      <td>37.792683</td>
      <td>18.731707</td>
      <td>23.841463</td>
      <td>47.318398</td>
      <td>35.301710</td>
      <td>78.567775</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Washington Wizards</td>
      <td>113.158537</td>
      <td>9.439024</td>
      <td>34.195122</td>
      <td>43.634146</td>
      <td>25.402439</td>
      <td>6.841463</td>
      <td>5.170732</td>
      <td>14.121951</td>
      <td>18.768293</td>
      <td>42.146341</td>
      <td>86.914634</td>
      <td>11.280488</td>
      <td>31.719512</td>
      <td>17.585366</td>
      <td>22.414634</td>
      <td>48.491651</td>
      <td>35.563245</td>
      <td>78.454842</td>
    </tr>
  </tbody>
</table>
</div>



Esta es toda la informacion promedio de cada equipo. Con esto podemos hacer analisis y tener insights de un punto donde podemos ver cual equipo es mas defensivo o cual es mas ofensivo y asi, poder identificar la necesidad de cada equipo (Si es en rebotes, triples, etc)
