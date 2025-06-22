![Group 545.png](attachment:8365f940-9017-428e-9e9f-5f676fea80f3:Group_545.png)

![Group 546.png](attachment:4ffcecec-9c6f-48eb-a7f1-227627642452:Group_546.png)

![Group 547.png](attachment:d7dccfcd-8725-4dd4-a902-dad70c3b7d05:Group_547.png)

![Group 548.png](attachment:2549a10f-1555-42cc-8125-8c1d1c3bf2f6:Group_548.png)

## Nearest_neighbor

separa um grupo dos 6000 entre 1000 para treino (dados usados para classificar os outros 5000 que não conhecemos) e 5000 para teste, nisso ele calcula a distancia entre cada ponto, pois por exeplo, para numeros ele pega um 768x768 e divide a iamgem em uma array contendo todos esses valores de cor (pixels), e classifca essse como X valor ou seja, numero 7 ou 8 por exemplo, 

![image.png](attachment:471a4da0-b732-42b1-8e6c-efbddf1616d5:image.png)

aqui as funções onde calcula a distancia Euclidiana, em que para simplificar computacionalmente, somamos apenas o quadrado, de forma que as grandezas das distancias permaneçam as mesmas, o `np.argmin`  ele retorna o menor valor, ou seja, o valor mais próximo de X, em relação aos dados de treino

![image.png](attachment:566baf64-501e-4fa7-9251-b0e9bd133817:image.png)

para o K do KNN, podemos utilizar valores diferentes, o K retorna uma quantidade a priori de valores que ele considera com menor distancia, nisso ele faz uma moda para ver qual resultado final se repete, ao final ele retorna o melhor

![image.png](attachment:bb63b958-7521-4df8-ac6d-06704e4730ee:image.png)

**Manhattan Distance = |x1 - x2| + |y1 - y2|**

![image.png](attachment:b3296e54-9051-42bb-a98a-f726e8f2c334:image.png)

## **2. L2 – Distância Euclidiana (“como o corvo voa”)**

### **Fórmula:**

L2: x2+y2=1\text{L2: } \sqrt{x^2 + y^2} = 1

L2: x2+y2

=1

### **Forma resultante:**

**Círculo**

### **Por quê?**

- A equação x2+y2=1\sqrt{x^2 + y^2} = 1x2+y2=1 é exatamente a **fórmula de um círculo** com raio 1 e centro na origem.
- A L2 considera todos os eixos de forma "balanceada" — todos os pontos ao redor da origem são tratados igualmente, não importa a direção.

---

## **3. L1 – Distância de Manhattan (ruas em grade)**

### **Fórmula:**

L1: ∣x∣+∣y∣=1\text{L1: } |x| + |y| = 1

L1: ∣x∣+∣y∣=1

### **Forma resultante:**

**Losango**

### **Por quê?**

- A soma das distâncias absolutas ao longo dos eixos x e y deve ser 1.
- Exemplos de pontos:
    - (1, 0), (0, 1), (-1, 0), (0, -1) → nas pontas do losango
    - (0.5, 0.5), (-0.5, 0.5), etc. → nos cantos inclinados
- Isso forma uma figura com 4 lados inclinados a 45°, criando um **losango**.

> Intuição: você só pode andar em linhas retas horizontais ou verticais, como num tabuleiro de xadrez ou numa cidade em blocos.
> 

---

## **4. L∞ – Distância do maior eixo (máximo absoluto)**

### **Fórmula:**

L∞: max⁡(∣x∣,∣y∣)=1\text{L∞: } \max(|x|, |y|) = 1

L∞: max(∣x∣,∣y∣)=1

### **Forma resultante:**

**Quadrado (eixos alinhados)**

### **Por quê?**

- A distância é definida como o **maior valor absoluto entre x e y**.
- Exemplo:
    - (1, 0), (0, 1), (-1, 0), (0, -1) → todos a distância 1
    - (1, 1) também está a distância 1 (pois max(1,1) = 1)
- O resultado é um **quadrado com lados paralelos aos eixos**, com vértices nos pontos (±1, ±1).

> Intuição: o que importa é o maior passo em qualquer direção. Você mede a distância com base no eixo mais distante.
> 

---

## **Resumo visual em 2D:**

| Norma | Equação | Forma |
| --- | --- | --- |
| **L2** | √(x² + y²) = 1 | Círculo |
| **L1** | x+y | x |
| **L∞** | max(x||y) | x |
