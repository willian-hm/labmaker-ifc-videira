# Fatiador (Slicer)

O fatiador transforma o modelo 3D em instruções para a impressora. É um software crucial que determina a qualidade, tempo e sucesso da impressão.

## 🧠 O que ele faz?

- **Divide o modelo em camadas** - Converte geometria 3D em camadas 2D
- **Define percurso do bico** - Calcula o caminho da extrusora
- **Ajusta velocidade e temperatura** - Otimiza para cada material
- **Gera o .gcode** - Cria instruções para a impressora
- **Adiciona suportes** - Estruturas temporárias para áreas penduradas
- **Otimiza o uso de material** - Calcula infill e wall thickness

## 🧰 Softwares de Fatiamento

### Bambu Studio
- **Ideal para**: Impressoras Bambu Lab
- **Vantagens**: Interface intuitiva, otimizado para impressoras Bambu
- **Recursos**: Perfil de impressão pré-configurado, simulação 3D
- **Preço**: Gratuito

### Ultimaker Cura
- **Ideal para**: Impressoras FDM em geral
- **Vantagens**: Grande comunidade, muitos plugins
- **Recursos**: Visualização em camadas, estimativa de tempo
- **Preço**: Gratuito
- ⚠️ **Observação**: Não é totalmente compatível com impressoras Bambu

### PrusaSlicer
- **Ideal para**: Impressoras Prusa e outras FDM
- **Vantagens**: Código aberto, altamente configurável
- **Recursos**: Suporte a múltiplos materiais, calibração avançada
- **Preço**: Gratuito

### Simplify3D
- **Ideal para**: Uso profissional
- **Vantagens**: Controle total sobre parâmetros
- **Recursos**: Animação do processo, otimização avançada
- **Preço**: Pago

### SuperSlicer
- **Ideal para**: Usuários avançados
- **Vantagens**: Interface moderna, recursos avançados
- **Recursos**: Suporte a múltiplas impressoras, presets
- **Preço**: Gratuito

## 📊 Função do slicer

![Slicer processo](https://iamrapid.com/knowledge-hub/images/how-to-slice-for-3D-printing/introduction-to-slicing-image.png)

## ⚙️ Principais configurações

### Parâmetros de Qualidade

#### Layer Height (Altura da Camada)
- **Padrão**: 0.2mm
- **Alta qualidade**: 0.1mm (mais lento)
- **Rápido**: 0.3-0.4mm (menos detalhe)
- **Impacto**: Afecta detalhe e tempo de impressão

#### Line Width (Largura da Linha)
- **Padrão**: 100% do diâmetro do bico
- **Fino**: 80% (para detalhes)
- **Grosso**: 120% (para força)
- **Impacto**: Afecta força e tempo

#### Wall Thickness (Espessura da Parede)
- **Mínimo**: 2x nozzle diameter
- **Comum**: 1.2-2.4mm
- **Impacto**: Força e tempo de impressão

### Parâmetros de Estrutura

#### Infill (Preenchimento)
- **Density**: 10-100% (20% padrão)
- **Pattern**: 
  - Grid (rápido)
  - Honeycomb (equilibrado)
  - Gyroid (forte, lento)
  - 3D (muito forte)
- **Impacto**: Força, peso e tempo

#### Top/Bottom Layers
- **Padrão**: 3-5 camadas
- **Impacto**: Acabamento superior e resistência

#### Support (Suportes)
- **Type**: Tree (ótimo), Grid (forte)
- **Density**: 10-20%
- **Z Distance**: 0.1-0.3mm
- **Angle**: 45-60°
- **Impacto**: Necessidade para overhangs

### Parâmetros de Impressão

#### Print Speed (Velocidade)
- **Padrão**: 50mm/s
- **Detalhes**: 30-40mm/s
- **Preenchimento**: 60-80mm/s
- **Impacto**: Qualidade vs tempo

#### Temperature (Temperatura)
- **PLA**: 190-210°C
- **PETG**: 220-240°C
- **ABS**: 240-260°C
- **Bed**: 50-70°C (PLA/PETG)
- **Impacto**: Qualidade e adesão

#### Retraction (Retração)
- **Distance**: 4-6mm
- **Speed**: 30-60mm/s
- **Prime**: 1-2mm
- **Impacto**: Stringing e oozing

### Avançado

#### Cooling (Resfriamento)
- **Fan Speed**: 0-100%
- **Min Layer Time**: 5-15s
- **Impacto**: Detalhe e qualidade

#### Adhesion (Adesão)
- **Brim**: 2-5mm (para pequenas peças)
- **Raft**: Para base irregular
- **Skirt**: Para teste de extrusão
- **Impacto**: Adesão à base

#### Travel (Movimento)
- **Speed**: 150mm/s
- **Retraction**: Minimizar oozing
- **Impacto**: Tempo e qualidade

## 🎯 Configurações por Material

### PLA
- **Temperatura**: 190-210°C
- **Bed**: 50-60°C
- **Speed**: 50-60mm/s
- **Cooling**: Alto (100%)
- **Infill**: 15-20%

### PETG
- **Temperatura**: 220-240°C
- **Bed**: 70-80°C
- **Speed**: 40-50mm/s
- **Cooling**: Médio (50%)
- **Infill**: 20-25%

### ABS
- **Temperatura**: 240-260°C
- **Bed**: 90-110°C
- **Speed**: 40-50mm/s
- **Cooling**: Baixo (0-30%)
- **Infill**: 25-30%

## 📊 Dicas de Otimização

1. **Balancear qualidade e tempo** - Menos camadas = mais rápido
2. **Testar com brim** - Evita warping
3. **Ajustar temperatura** - Para cada material específico
4. **Usar suportes inteligentes** - Tree supports para menos material
5. **Calibrar retração** - Minimizar stringing
6. **Otimizar infill** - Usar gyroid para força e peso
7. **Ajustar velocidade** - Mais lento para detalhes