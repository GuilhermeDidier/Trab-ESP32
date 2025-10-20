# 🌱 Sistema de Irrigação Inteligente - FarmTech Solutions

## 📋 Descrição do Projeto

Este projeto implementa um sistema de irrigação automatizado e inteligente para agricultura digital, desenvolvido como parte da Fase 2 do curso FIAP. O sistema monitora a umidade do solo em tempo real e os níveis de nutrientes NPK (Nitrogênio, Fósforo e Potássio), integrando-se com dados meteorológicos para otimizar a irrigação agrícola.

## 🎯 Objetivos

- Desenvolver um sistema IoT para monitoramento agrícola
- Automatizar o processo de irrigação baseado em dados de sensores
- Integrar dados meteorológicos externos via API
- Analisar estatisticamente os dados coletados
- Otimizar o uso de recursos hídricos na agricultura

## 🛠️ Tecnologias Utilizadas

### Hardware
- **ESP32**: Microcontrolador principal
- **DHT22**: Sensor de umidade e temperatura
- **Sensor LDR**: Medição de intensidade luminosa
- **Relé**: Controle da bomba d'água
- **LED Verde**: Indicador de bomba ligada

### Software
- **C/C++**: Programação do ESP32
- **Python 3.x**: Integração com APIs e processamento de dados
- **R**: Análise estatística dos dados
- **Wokwi**: Simulação do circuito
- **OpenWeather API**: Dados meteorológicos em tempo real

## 📐 Arquitetura do Sistema

```
┌─────────────────┐     ┌──────────────┐     ┌─────────────┐
│   Sensores      │────▶│    ESP32     │────▶│   Atuadores │
│  DHT22 + LDR    │     │              │     │  Relé/Bomba │
└─────────────────┘     └──────────────┘     └─────────────┘
                              │
                              ▼
                    ┌──────────────────┐
                    │   Python Script  │
                    │  (OpenWeather)   │
                    └──────────────────┘
                              │
                              ▼
                    ┌──────────────────┐
                    │   Análise em R   │
                    │   (Estatística)  │
                    └──────────────────┘
```

## 📊 Funcionamento do Sistema

### 1. Coleta de Dados
- O sensor DHT22 monitora umidade do solo e temperatura
- O sensor LDR mede a intensidade luminosa
- Dados são processados pelo ESP32

### 2. Lógica de Irrigação
- **Umidade < 30%**: Solo seco - irrigação ativada
- **Umidade 30-70%**: Solo adequado - sem irrigação
- **Umidade > 70%**: Solo úmido - sem irrigação

### 3. Integração com API
- Script Python consulta OpenWeather API
- Dados meteorológicos influenciam decisões de irrigação
- Previsão de chuva suspende irrigação automaticamente

## 🔧 Configuração e Instalação

### Pré-requisitos
```bash
# Python
pip install requests
pip install pandas
pip install matplotlib

# R
install.packages("tidyverse")
install.packages("forecast")
install.packages("ggplot2")
```

### Simulação no Wokwi
1. Acesse o projeto: [Link do Wokwi](https://wokwi.com/projects/443910118628313089)
2. Clique em "Start Simulation"
3. Ajuste os valores do sensor DHT22 para testar diferentes cenários

### Configuração da API
1. Chave API em [OpenWeather] = b1a068f7daf64c487a29fa43acd081c6

## 📈 Análise de Dados

### Métricas Monitoradas
- Umidade do solo (%)
- Temperatura ambiente (°C)
- Intensidade luminosa (lux)
- Precipitação prevista (mm)
- Tempo de irrigação diário (minutos)

### Análises Estatísticas em R
- Correlação entre variáveis climáticas
- Previsão de demanda hídrica
- Otimização de horários de irrigação
- Análise de tendências sazonais

## 🌍 Integração com Dados Públicos

O projeto utiliza dados de:
- **EMBRAPA**: Informações sobre culturas agrícolas
- **CONAB**: Dados de produtividade
- **IBGE**: Estatísticas agrícolas
- **CEPEA**: Preços e mercado agrícola
- **MAPA**: Políticas e regulamentações

## 📹 Demonstração

Assista ao vídeo demonstrativo: [Link YouTube](https://youtube.com/seu_video)

## 👥 Equipe

- [GuilhermePaesBarretoDidierGarcia] - RM: 568457

## 📝 Licença

Este projeto está sob licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

**Desenvolvido para FIAP - Fase 2 - Agricultura Digital** 🚜🌾
