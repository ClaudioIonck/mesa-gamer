# Mesa Gamer 1400

Modelo 3D interativo e parametrizado da mesa gamer, feito em HTML + [Three.js](https://threejs.org/) (r128), para visualizar o projeto e passar as medidas ao marceneiro e à serralheria.

Para usar, abra o `index.html` no navegador. Não há build nem dependências locais: o Three.js é carregado por CDN.

## Especificações

| Item | Medida |
|---|---|
| Tampo (C × L × E) | 1400 × 770 × 35 mm |
| Altura total | 750 mm (base 715 + tampo 35) |
| Recuo dos quadros da base | 50 mm em relação às 4 bordas do tampo |
| Vão da base (C × L) | 1300 × 670 mm |
| Perfil metálico (metalon) | 50 × 30 mm |
| Travessas sob o tampo | frente a 50 mm da borda · trás a 240 mm do fundo |
| Organizador de cabos | 1000 × 150 × 110 mm, chapa perfurada, a 60 mm do fundo |
| Passa-cabos no tampo | 3 × (80 × 40 mm), centros a 200 · 700 · 1200 mm da borda esquerda e 135 mm do fundo |
| Boleado das arestas e dos furos | raio 5 mm |
| Cantos do tampo | raio 25 mm |

**Materiais**

- **Tampo:** madeira maciça em tom nogueira médio-escuro, com verniz brilhante e acabamento liso.
- **Base e organizador:** aço com pintura eletrostática grafite quase preto. A referência de tela é `#2B2E2F`; confirme com amostra ou catálogo RAL na hora de encomendar.

## Recursos do modelo

- **Navegação:** girar 360°, zoom e mover a câmera com mouse ou toque (OrbitControls).
- **Vistas rápidas:** Perspectiva, Traseira, Frontal, Lateral e Superior.
- **Cotas:** cotas desenhadas no modelo, com chave **mm / cm**.
- **Travessas:** compare "frente + trás" com "uma central".
- **Organizador e passa-cabos:** podem ser mostrados ou ocultados no modelo.
- **Avisos:** o modelo avisa quando há conflito entre o organizador e a travessa, ou entre os furos e o quadro da base.

## Ajustes no código

Todas as medidas ficam no objeto `P`, no início do script do `index.html`, sempre em milímetros. Para mudar uma dimensão, edite o valor; a geometria se recalcula sozinha. Os principais campos são estes:

```js
const P = {
  topL:1400, topW:770, topT:35,   // tampo
  inset:50, baseH:715,            // recuo e altura da base
  tubeA:50, tubeB:30,             // perfil metalon
  rearSetback:240,                // recuo da travessa traseira
  trayL:1000, trayD:150, trayH:110,
  slotW:80, slotH:40, slotR:8,    // passa-cabos
  edgeR:5, cornerR:25             // boleado e cantos
};
```

## Licença

[MIT](LICENSE)
