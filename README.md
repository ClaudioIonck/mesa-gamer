# Mesa Gamer

Modelo 3D interativo e parametrizado da mesa gamer, feito em HTML + [Three.js](https://threejs.org/) (r128), para visualizar o projeto e passar as medidas ao marceneiro e à serralheria.

Para usar, abra o `index.html` no navegador. Não há build nem dependências locais: o Three.js é carregado por CDN.

## Especificações

| Item | Medida |
|---|---|
| Tampo (C × L × E) | 1400 × 770 × 35 mm |
| Altura total | 750 mm (base 715 + tampo 35) |
| Recuo dos quadros da base | 50 mm em relação às 4 bordas do tampo |
| Vão da base (C × L) | 1300 × 670 mm |
| Base | quadro em aço carbono, metalon 60 × 40 mm, chapa 16 (1,5 mm), 715 mm de altura |
| Abas de fixação | 10 abas superiores 60 × 40 × 3 mm, furo oblongo 18 × 7 mm no sentido da largura do tampo |
| Travessas sob o tampo | frente a 50 mm da borda · trás a 240 mm do fundo |
| Travessa central | transversal no eixo (700 mm de cada lado), 400 mm entre as travessas, metalon 60 × 40 mm |
| Organizador de cabos | 1000 × 150 × 110 mm, chapa perfurada, a 60 mm do fundo |
| Passa-cabos no tampo | 3 × (80 × 40 mm), centros a 200 · 700 · 1200 mm da borda esquerda e 135 mm do fundo |
| Boleado das arestas e dos furos | raio 5 mm |
| Cantos do tampo | raio 25 mm |

**Materiais**

- **Tampo:** madeira maciça em tom nogueira médio-escuro, com verniz brilhante e acabamento liso.
- **Base e organizador:** aço carbono com pintura eletrostática preto fosco.

## Recursos do modelo

- **Navegação:** girar 360°, zoom e mover a câmera com mouse ou toque (OrbitControls).
- **Vistas rápidas:** Perspectiva, Traseira, Frontal, Lateral, Superior e Inferior (a câmera também pode girar por baixo da mesa).
- **Cotas:** cotas desenhadas no modelo, com chave **mm / cm**.
- **Prancha técnica 2D:** botão **SVG** no canto inferior direito alterna entre o modelo 3D e a prancha (vistas frontal, lateral, planta, isométrica, detalhes e ficha técnica), com zoom, cotas em mm / cm e botão **Download** para baixar em SVG ou PNG.
- **Folgas:** o painel mostra a folga entre o organizador e a travessa traseira e a distância dos furos das pontas até o quadro da base.

## Prancha técnica

A prancha também está salva em [`prancha/`](prancha/), pronta para enviar ao marceneiro e à serralheria:

- `mesa-gamer-prancha-tecnica.svg` · desenho vetorial (abre em programas de CAD ou de desenho)
- `mesa-gamer-prancha-tecnica.png` · imagem A3 em alta resolução (~420 dpi), para imprimir ou mandar por mensagem

## Ajustes no código

Todas as medidas ficam no objeto `P`, no início do script do `index.html`, sempre em milímetros. Para mudar uma dimensão, edite o valor; a geometria se recalcula sozinha. Os principais campos são estes:

```js
const P = {
  topL:1400, topW:770, topT:35,   // tampo
  inset:50, baseH:715,            // recuo e altura da base
  tubeA:60, tubeB:40,             // perfil metalon
  rearSetback:240,                // recuo da travessa traseira
  trayL:1000, trayD:150, trayH:110,
  slotW:80, slotH:40, slotR:8,    // passa-cabos
  edgeR:5, cornerR:25             // boleado e cantos
};
```

## Licença

[MIT](LICENSE)
