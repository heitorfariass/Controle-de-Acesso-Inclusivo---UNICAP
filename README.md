# ♿ Sistema Robótico de Destravamento com RFID - Acessibilidade UNICAP

[![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)](https://www.arduino.cc/)
[![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://cplusplus.com/)

## 📋 Sobre o Projeto
[span_0](start_span)Projeto acadêmico desenvolvido com o objetivo de promover a autonomia no acesso de alunos com mobilidade reduzida (como cadeirantes) às instalações da universidade[span_0](end_span). [span_1](start_span)[span_2](start_span)Atualmente, o acesso requer que os estudantes dependam da abertura manual da porta de acessibilidade por terceiros, gerando constrangimento e redução de autonomia[span_1](end_span)[span_2](end_span). 

[span_3](start_span)A solução proposta é um **Sistema Robótico de Destravamento com RFID**[span_3](end_span). [span_4](start_span)[span_5](start_span)Ao aproximar um cartão autorizado, um mecanismo controlado por Arduino aciona um servo motor para abrir e fechar uma trava de forma automática, garantindo um acesso digno, independente e inclusivo[span_4](end_span)[span_5](end_span).

---

## 👥 Equipe
* [span_6](start_span)João da Fonte[span_6](end_span)
* [span_7](start_span)Heitor Farias Santos[span_7](end_span)
* [span_8](start_span)Nina Lira[span_8](end_span)
* [span_9](start_span)Marcelo Caldas[span_9](end_span)
* [span_10](start_span)João Gabriel[span_10](end_span)

---

## ⚙️ Funcionalidades Principais
* **[span_11](start_span)Controle de Acesso Físico:** Destravamento de porta automatizado via leitura de tags RFID[span_11](end_span).
* **Acionamento em Alternância (Toggle):** Ao ler um cartão válido, a porta abre. [span_12](start_span)Ao ler novamente, a porta fecha[span_12](end_span).
* **[span_13](start_span)Gestão via Master Card:** Cadastro e remoção de usuários feitos fisicamente aproximando um "Cartão Mestre", sem necessidade de plugar o Arduino no computador[span_13](end_span).
* **[span_14](start_span)Armazenamento Não-Volátil:** Os UIDs dos cartões cadastrados são salvos na memória EEPROM nativa do Arduino (suporta até 10 cartões no código atual, expansível)[span_14](end_span).
* **[span_15](start_span)100% Offline:** O sistema não depende de internet, servidores externos ou banco de dados em nuvem para funcionar[span_15](end_span).

---

## 🛠️ Hardware e Componentes
* **[span_16](start_span)Microcontrolador:** Arduino Uno[span_16](end_span)
* **[span_17](start_span)Módulo de Leitura:** Leitor RFID RC522 (Frequência 13.56 MHz)[span_17](end_span)
* **[span_18](start_span)Atuador:** Servo Motor de Rotação Contínua (SG90 modificado / 360º)[span_18](end_span)
* **[span_19](start_span)[span_20](start_span)Mecânica:** Mecanismo de trava impresso em 3D (Cremalheira e Pinhão)[span_19](end_span)[span_20](end_span) e Estrutura do portão cortada a laser em MDF.

### 🔌 Esquema de Ligação (Pinagem)

| Componente | Pino do Componente | Pino do Arduino |
| :--- | :--- | :--- |
| **RFID RC522** | SDA (SS) | Pino Digital 10 |
| **RFID RC522** | SCK | Pino Digital 13 |
| **RFID RC522** | MOSI | Pino Digital 11 |
| **RFID RC522** | MISO | Pino Digital 12 |
| **RFID RC522** | IRQ | *Não conectado* |
| **RFID RC522** | GND | GND |
| **RFID RC522** | RST | Pino Digital 9 |
| **RFID RC522** | 3.3V | 3.3V *(Atenção: Risco de queima no 5V)* |
| **Servo Motor**| Sinal (Laranja/Amarelo) | Pino Digital 7 |
| **Servo Motor**| VCC (Vermelho) | 5V (Recomendado Fonte Externa) |
| **Servo Motor**| GND (Marrom/Preto) | GND |

---

## 🚀 Como instalar e usar

1. **Dependências:** Instale as seguintes bibliotecas na IDE do Arduino:
   * `MFRC522` (Por GithubCommunity)
   * `Servo` (Nativa)
   * `EEPROM` (Nativa)
   * `SPI` (Nativa)

2. **Configuração do Cartão Mestre:** No arquivo `.ino`, localize a variável `masterID` e insira o UID do cartão que será usado como administrador. Exemplo:
   ```cpp
   String masterID = "63:13:ED:1B"; 
