# G-code

O G-code é o arquivo que a impressora executa. É uma linguagem de programação que controla todos os aspectos da impressão 3D, desde o movimento da extrusora até a temperatura do bico.

## 🧠 O que é?

É uma linguagem de comandos que diz à impressora:

- **Onde se mover** - Posicionamento dos eixos X, Y, Z
- **Quanto extrudar** - Quantidade de material a ser depositado
- **Qual temperatura usar** - Controle da temperatura do bico e base
- **Velocidade de impressão** - Quão rápido se mover
- **Controle de ferramentas** - Ativar/desativar ventilador, etc.

## 📄 Estrutura Básica do G-code

### Comandos Iniciais (Setup)
```gcode
G21 ; Unidades em milímetros
G90 ; Coordenadas absolutas
M82 ; Extrusor em modo absoluto
G28 ; Home de todos os eixos
G1 Z0.2 ; Levantar bico 0.2mm
G1 X0 Y0 ; Mover para origem
```

### Calibração e Teste
```gcode
M106 S255 ; Ligar ventilador máximo
G1 X100 Y100 F3000 ; Movimento rápido
G1 X0 Y0 F3000 ; Retornar ao início
M107 ; Desligar ventilador
```

### Impressão Principal
```gcode
M190 S60 ; Esperar base atingir 60°C
M109 T0 S210 ; Esperar extrusor T0 atingir 210°C
G1 X0 Y0 F3000 ; Posicionar
G1 Z0.3 F900 ; Descer bico
G92 E0 ; Resetar extrusor
G1 Z0.2 F900 ; Descer para altura correta
G1 E10 F300 ; Extruir 10mm
G1 X50 Y50 F1800 ; Mover enquanto extrude
```

### Comandos Finais (Cleanup)
```gcode
M104 S0 ; Desligar extrusor
M140 S0 ; Desligar base
M107 ; Desligar ventilador
G1 X0 Y300 F3000 ; Mover para área de limpeza
G1 Z10 ; Levantar bico
M84 ; Desligar motores
```

## 🔧 Comandos Principais

### Movimento
```gcode
G0 X10 Y10 Z10 ; Movimento rápido (sem extrusão)
G1 X10 Y10 Z10 F1800 ; Movimento linear com velocidade
G2 X10 Y10 I5 J5 ; Movimento circular horário
G3 X10 Y10 I5 J5 ; Movimento circular anti-horário
```

### Extrusão
```gcode
G1 E10 F300 ; Extruir 10mm a 300mm/min
G1 E-5 F1800 ; Retrair 5mm
G92 E0 ; Resetar posição do extrusor
```

### Controle de Temperatura
```gcode
M109 S210 ; Esperar extrusor atingir 210°C
M190 S60 ; Esperar base atingir 60°C
M104 S210 ; Definir temperatura extrusor (sem esperar)
M140 S60 ; Definir temperatura base (sem esperar)
```

### Ventilação
```gcode
M106 S255 ; Ligar ventilador (0-255)
M107 ; Desligar ventilador
```

### Controle de Motores
```gcode
M84 ; Desligar motores
M17 ; Ligar motores
M18 ; Desligar motores (alternativa)
```

### Configuração
```gcode
G21 ; Unidades em milímetros
G20 ; Unidades em polegadas
G90 ; Coordenadas absolutas
G91 ; Coordenadas relativas
M82 ; Extrusor modo absoluto
M83 ; Extrusor modo relativo
```

## 📊 Parâmetros Importantes

### Velocidade (F)
- Unidade: mm/min
- Exemplos:
  - F3000: Movimento rápido (sem impressão)
  - F1800: Movimento normal
  - F600: Impressão lenta (detalhes)
  - F3000: Preenchimento rápido

### Temperatura (S)
- Unidade: °C
- Exemplos:
  - M109 S210: Extrusor PLA
  - M109 S240: Extrusor PETG
  - M190 S60: Base PLA

### Extrusão (E)
- Unidade: mm de filamento
- Exemplos:
  - G1 E10 F300: Extruir 10mm
  - G1 E-5 F1800: Retrair 5mm

### Posicionamento (X, Y, Z)
- Unidade: mm
- Exemplos:
  - G1 X100 Y100 Z0.2
  - G0 X0 Y0 Z10

## 🎯 Comandos Específicos

### Suportes
```gcode
; Gerar suporte
G1 X50 Y50 Z0.1 F600 ; Posicionar para suporte
G1 E5 F300 ; Extruir início
G1 X55 Y55 Z0.2 F600 ; Mover enquanto extrude
```

### Início de Impressão
```gcode
; Primeira camada
G1 Z0.1 F300 ; Descer bico
G1 E5 F300 ; Extruir 5mm
G1 X10 Y10 F1800 ; Mover para início
G1 Z0.2 F300 ; Subir para altura correta
```

### Mudança de Material (Multi-material)
```gcode
T1 ; Trocar para extrusor 1
M109 T1 S220 ; Esperar extrusor 1 atingir 220°C
G1 E10 F300 ; Purgar extrusor
```

## 📋 G-code Comum por Material

### PLA
```gcode
M109 S210 ; Temperatura extrusor
M190 S60 ; Temperatura base
G1 Z0.2 F300 ; Primeira camada
G1 E5 F300 ; Extrusão inicial
```

### PETG
```gcode
M109 S230 ; Temperatura extrusor
M190 S80 ; Temperatura base
G1 Z0.2 F300 ; Primeira camada
G1 E5 F300 ; Extrusão inicial
```

### ABS
```gcode
M109 S250 ; Temperatura extrusor
M190 S110 ; Temperatura base
G1 Z0.2 F300 ; Primeira camada
G1 E5 F300 ; Extrusão inicial
```

## 🔍 Otimização de G-code

### Reduzir Movimentos
- Agrupar áreas próximas
- Minimizar movimentos sem extrusão
- Usar caminhos eficientes

### Melhorar Qualidade
- Reduzir velocidade em detalhes
- Aumentar número de perímetros
- Otimizar retractions

### Economizar Tempo
- Aumentar velocidade de preenchimento
- Reduzir altura de camada para áreas simples
- Usar suportes inteligentes

## 🛠️ Ferramentas de G-code

### Visualizadores
- Pronterface
- OctoPrint
- GCode Viewer
- SuperSlicer (visualização integrada)

### Editores
- Notepad++ (com syntax highlight)
- VS Code (com extensão G-code)
- GCode Editor

### Análise
- GCode Analyzer
- Print Time Estimator
- Material Calculator

## 📊 Dicas de G-code

1. **Sempre verificar** - Visualizar antes de imprimir
2. **Testar pequenos** - Fatiar e imprimir amostras
3. **Documentar** - Salvar presets para materiais
4. **Backup** - Manter versões de G-code
5. **Otimizar** - Ajustar para cada impressora
6. **Monitorar** - Usar OctoPrint para controle remoto