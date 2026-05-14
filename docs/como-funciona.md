# Como Funciona

A impressão 3D segue um fluxo bem definido que transforma um modelo digital em um objeto físico.

## 🔄 Fluxo completo

1. **Criar/obter modelo 3D** - Design no computador ou download de modelo existente
2. **Exportar arquivo (.STL/.3MF)** - Formato compatível com impressoras 3D
3. **Fatiar o modelo (slicer)** - Preparar o modelo para impressão
4. **Gerar G-code** - Criar instruções para a impressora
5. **Impressão camada por camada** - A impressora constrói o objeto

## 📊 Diagrama do processo

![Fluxo STL → Slicer → Impressora](https://cdn.shopify.com/s/files/1/0311/1180/7114/articles/slicer13-1_600x.png)

## 🧪 Detalhe técnico - FDM/FFF

Na tecnologia FDM (Fused Deposition Modeling):

- O filamento é aquecido até derreter (geralmente 180-230°C)
- É extrudado por um bico (nozzle) com precisão
- Deposita material em camadas sobre a base ou camadas anteriores
- Cada camada é solidificada antes da próxima ser adicionada

👉 Funciona como uma "cola quente controlada por computador"

## 🏭 Tecnologias de impressão 3D

### FDM/FFF (Fused Deposition Modeling)
- **Material**: Filamentos plásticos (PLA, ABS, PETG, etc.)
- **Processo**: Extrusão de material derretido
- **Vantagens**: Custo baixo, fácil operação
- **Desvantagens**: Menor precisão, linhas visíveis

### SLA (Stereolithography)
- **Material**: Resinas fotopolímeras
- **Processo**: Cura por luz UV
- **Vantagens**: Alta precisão, detalhes finos
- **Desvantagens**: Material frágil, processo mais caro

### SLS (Selective Laser Sintering)
- **Material**: Pó de polímero
- **Processo**: Fusão por laser
- **Vantagens**: Sem suportes, peças fortes
- **Desvantagens**: Custo elevado, pós tóxicos

### DLP (Digital Light Processing)
- **Material**: Resinas fotopolímeras
- **Processo**: Cura por projeção de luz
- **Vantagens**: Rápido, boa precisão
- **Desvantagens**: Limitações de tamanho

## ⚙️ Componentes básicos de uma impressora FDM

### Estrutura
- Chassi rígido para evitar vibrações
- Base aquecida (heated bed) para adesão
- Guias para movimento preciso

### Sistema de extrusão
- Extrusor (hotend) - aquece e extrude o material
- Filamento - material de impressão
- Motor de passo - controla o avanço do filamento

### Sistema de movimento
- Motores de passo - movem os eixos X, Y, Z
- Correias e polias - transmitem movimento
- Limites de fim de curso (endstops) - definem os limites

### Eletrônica
- Controlador (mainboard) - processa os comandos
- Firmware - software que controla a impressora
- Display - interface do usuário

## 📐 Parâmetros importantes

### Resolução
- **Layer height** - altura da camada (0.1mm a 0.4mm)
- **Nozzle diameter** - diâmetro do bico (0.4mm comum)
- **Infill** - densidade interna do objeto (10-100%)

### Velocidades
- **Print speed** - velocidade de impressão (40-100mm/s)
- **Travel speed** - velocidade de movimento sem impressão
- **Retraction speed** - velocidade de retração do filamento

### Temperaturas
- **Extrusion temperature** - temperatura de extrusão
- **Bed temperature** - temperatura da base
- **Enclosure temperature** - temperatura ambiente (para materiais especiais)