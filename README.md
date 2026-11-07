# B1–B10 Lab — protótipo independente

Aplicação didática experimental de broncoscopia virtual com TC e EBUS-TBNA. **Este repositório é independente do B1–B10 original**, que permanece em https://github.com/henriquemmafra/b1-b10.

## Abrir
Quando GitHub Pages estiver ativado em **Settings → Pages → Deploy from a branch → main / (root)**:

https://henriquemmafra.github.io/b1-b10-lab/

## Recursos disponíveis nesta primeira versão

- Carregamento **local** de uma série DICOM CT monocromática de 16 bits, Little Endian, sem compressão e de frame único.
- Visualizador axial, seleção manual de uma semente aérea e crescimento de região tridimensional por limiar de atenuação (resultado **não validado**).
- Visualização 3D da superfície e câmera exploratória com colisão simples.
- Volume sintético de vias aéreas para demonstração sem upload de exame.
- EBUS-TBNA **sintético**, com estações 2R, 2L, 4R, 4L, 7, 10R, 10L, 11R e 11L; ajuste de ângulo/profundidade da agulha e simulação esquemática de vaso/Doppler.
- Todo o processamento DICOM acontece no próprio navegador; este protótipo não possui backend de upload.

## Limitações e cuidados

**Não é ferramenta clínica.** A segmentação por limiar pode invadir parênquima ou falhar na identificação de brônquios; é necessário verificar manualmente a máscara. A anatomia não é rotulada automaticamente B1–B10. O EBUS não é derivado do exame do paciente, a imagem de ultrassom é apenas ilustrativa, e a colisão/risco vascular é simulada. Não utilize este protótipo para planejar ou executar procedimentos.

Séries DICOM comprimidas, multiframe, oblíquas, com variação de geometria ou misturas de séries não são suportadas. Recomenda-se trabalhar somente com dados desidentificados, inclusive ao compartilhar prints.

## Teste

1. Abra a página.
2. Em “TC → árvore brônquica”, selecione **Exemplo sintético** e clique em **Segmentar a partir do ponto**.
3. Explore **Visão 3D** e **Visão interna**.
4. Abra **EBUS + punção linfonodal**, selecione a estação e ajuste a agulha.

## Infraestrutura

A interface é um arquivo HTML estático com JavaScript e Three.js 0.170.0 carregado via jsDelivr; não requer build. O código da interface é independente do repositório original.

**Status:** MVP de interface e processamento exploratório; teste automatizado de navegador e validação clínica ainda pendentes.
