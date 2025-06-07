Larissa De Freitas Moura -RM555136
João Victor Rebello de Santis -RM555287
Guilherme Francisco Silva Pereira -RM557843


# 🚨 EmergencyIoT - Sistema de Comunicação para Desastres

## 📋 Sobre o Projeto

O **EmergencyIoT** é um sistema completo de Internet das Coisas (IoT) desenvolvido para comunicação em situações de emergência e desastres climáticos. O projeto utiliza Arduino para detecção automática de emergências e Node-RED para processamento e comunicação via protocolo MQTT.

### 🎯 Problema Resolvido
Durante desastres naturais como enchentes, terremotos ou incêndios, a comunicação entre equipes de resgate e coordenação de recursos é fundamental para salvar vidas. Este sistema automatiza a detecção de emergências e facilita a comunicação em tempo real.

## ✨ Funcionalidades

- 🚨 **Detecção Automática de Emergências** - Arduino monitora sensores e detecta situações críticas
- 📡 **Comunicação MQTT** - Protocolo eficiente para transmissão de dados em tempo real
- 💡 **Sistema de LEDs Indicadores** - Visualização imediata do status da emergência
- 🌐 **Interface Node-RED** - Dashboard intuitivo para monitoramento e controle
- 📊 **Monitoramento de Recursos** - Acompanhamento de abrigos e recursos disponíveis
- ⚡ **Simulação Completa** - Teste o sistema sem hardware físico usando Wokwi
- 🔄 **Funcionamento 24/7** - Sistema projetado para operar continuamente

## 🛠️ Tecnologias Utilizadas

### Hardware
- **Arduino Uno** - Microcontrolador principal
- **LEDs RGB** - Indicadores visuais de status
- **Sensores** (simulados) - Detecção de condições ambientais

### Software
- **Arduino IDE** - Desenvolvimento do firmware
- **Node-RED** - Processamento de dados e interface
- **MQTT Broker** - test.mosquitto.org para comunicação
- **Wokwi** - Simulação online do hardware

### Linguagens
- **C++** - Programação Arduino
- **JavaScript** - Lógica Node-RED
- **JSON** - Formato de dados

## 🚀 Como Executar o Projeto

### 📱 Opção 1: Simulação Online (Recomendado)
1. **Acesse a simulação:** [EmergencyIoT no Wokwi](https://wokwi.com/projects/433131824681029633)
2. **Clique em "Start Simulation"**
3. **Observe os LEDs** mudando conforme os estados de emergência
4. **Monitore o Serial** para ver os dados JSON sendo transmitidos

### 💻 Opção 2: Node-RED Local
1. **Instale o Node-RED:**
   ```bash
   npm install -g node-red
   ```

2. **Execute o Node-RED:**
   ```bash
   node-red
   ```

3. **Acesse:** http://localhost:1880

4. **Importe o fluxo:**
   - Menu hambúrguer → Import
   - Cole o conteúdo de `node-red/flow.json`
   - Deploy

### 🔧 Opção 3: Arduino Físico
1. **Abra o Arduino IDE**
2. **Carregue o arquivo:** `arduino/emergencynet.ino`
3. **Conecte o Arduino via USB**
4. **Monte o circuito** conforme o diagrama
5. **Faça upload** do código

## 📊 Estados do Sistema

| Estado | Significado | LED | Cor | Ação |
|--------|-------------|-----|-----|------|
| **0** | STANDBY | Pino 2 | 🟢 Verde | Sistema em espera |
| **1** | EMERGÊNCIA | Pino 3 | 🔴 Vermelho | Enviar socorro imediatamente |
| **2** | COMUNICANDO | Pino 4 | 🟡 Amarelo | Equipes sendo acionadas |
| **3** | CONTROLADO | Pino 5 | 🔵 Azul | Situação sob controle |

## 📁 Estrutura do Projeto

```
EmergencyIoT/
├── 📁 arduino/              # Código e circuitos Arduino
│   ├── emergencynet.ino     # Firmware principal
│   └── diagram.json         # Circuito Wokwi
├── 📁 node-red/             # Fluxos e configurações
│   └── flow.json            # Fluxo completo Node-RED
├── 📁 wokwi/                # Simulações e links
│   └── projeto_link.txt     # Link da simulação
├── 📁 docs/                 # Documentação adicional
├── 📄 README.md             # Este arquivo
└── 📄 LICENSE               # Licença MIT
```

## 🎮 Demonstração

### Arduino em Funcionamento
```
State: 0 | Emergencies: 1  | Time: 429ms
State: 1 | Emergencies: 2  | Time: 432ms  
State: 2 | Emergencies: 3  | Time: 435ms
State: 3 | Emergencies: 4  | Time: 438ms
```

### Dados JSON Transmitidos
```json
{
  "timestamp": "2025-06-07T21:06:39.338Z",
  "state": 1,
  "count": 35,
  "device_id": "arduino_emergencia_01",
  "local": "Zona Norte SP",
  "tipo": "enchente",
  "prioridade": "ALTA",
  "status": "EMERGENCIA_ATIVA"
}
```

## 🔗 Links Importantes

- 🌐 **Simulação Wokwi:** [Ver projeto funcionando](https://wokwi.com/projects/433131824681029633)
- 🔧 **Node-RED Local:** http://localhost:1880
- 📡 **MQTT Broker:** test.mosquitto.org:1883
- 👩‍💻 **Perfil GitHub:** [LarissaMouraDev](https://github.com/LarissaMouraDev)

## 🏗️ Arquitetura do Sistema

**Fluxo de Dados:**
1. Arduino + Sensores detectam emergência
2. Dados são enviados para Node-RED via Serial/WiFi
3. Node-RED processa e publica via MQTT
4. MQTT Broker distribui para sistemas de monitoramento
5. Equipes de resgate e coordenação recebem alertas
6. LEDs indicam status visual do sistema

## 🎯 Casos de Uso

### 🌊 Enchentes
- Sensores de nível d'água detectam elevação crítica
- Sistema automaticamente alerta as autoridades
- Coordenação de abrigos e recursos de emergência

### 🔥 Incêndios
- Detecção de fumaça e temperatura elevada
- Acionamento imediato do corpo de bombeiros
- Monitoramento da evolução do incidente

### 🏠 Emergências Urbanas
- Acidentes em edificações
- Quedas de energia em hospitais
- Situações que requerem resposta rápida

## 📈 Métricas do Projeto

- ⚡ **Tempo de resposta:** < 3 segundos
- 🔄 **Ciclo de monitoramento:** 3 segundos
- 📡 **Protocolo:** MQTT (baixo overhead)
- 🌐 **Conectividade:** WiFi/Ethernet
- 🔋 **Eficiência energética:** Otimizado para operação contínua

## 🛣️ Roadmap

### Versão 2.0 (Planejada)
- [ ] Interface web responsiva
- [ ] Integração com WhatsApp/SMS
- [ ] Geolocalização GPS
- [ ] Banco de dados histórico
- [ ] Machine Learning para predição

### Versão 3.0 (Futura)
- [ ] Aplicativo mobile
- [ ] Integração com drones
- [ ] Rede mesh para comunicação offline
- [ ] API para terceiros

## 🤝 Como Contribuir

1. **Faça um Fork** do projeto
2. **Crie uma branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3. **Commit suas mudanças** (`git commit -m 'Add some AmazingFeature'`)
4. **Push para a branch** (`git push origin feature/AmazingFeature`)
5. **Abra um Pull Request**

### 🐛 Reportando Bugs
- Use as [Issues](https://github.com/LarissaMouraDev/EmergencyIoT/issues) para reportar bugs
- Descreva o problema detalhadamente
- Inclua passos para reproduzir

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👩‍💻 Autora
**Larissa Moura**
- 💼 LinkedIn: [LarissaMouraDev](https://www.linkedin.com/in/larissa-moura-2015a3285/)
- 🐙 GitHub: [@LarissaMouraDev](https://github.com/LarissaMouraDev)
- 
## 🙏 Agradecimentos

- **Arduino Community** - Pelo excelente ecossistema de desenvolvimento
- **Node-RED Team** - Pela ferramenta visual incrível
- **Wokwi** - Pela plataforma de simulação fantástica
- **MQTT Community** - Pelo protocolo eficiente e confiável

## 🌟 Se este projeto te ajudou, deixe uma ⭐!

---

**EmergencyIoT - Tecnologia a serviço da vida**

*Desenvolvido com ❤️ para tornar o mundo mais seguro*
