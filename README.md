# ♿ Sistema Robótico de Destravamento com RFID - Acessibilidade UNICAP

[![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)](https://www.arduino.cc/)
[![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://cplusplus.com/)

## 📋 Sobre o Projeto
Projeto acadêmico desenvolvido com o objetivo de promover a autonomia no acesso de alunos com mobilidade reduzida (como cadeirantes) às instalações da universidade. Atualmente, o acesso requer que os estudantes dependam da abertura manual da porta de acessibilidade por terceiros, gerando constrangimento e redução de autonomia. 

A solução proposta é um **Sistema Robótico de Destravamento com RFID**. Ao aproximar um cartão autorizado, um mecanismo controlado por Arduino aciona um servo motor para abrir e fechar uma trava de forma automática, garantindo um acesso digno, independente e inclusivo.

---

## 👥 Equipe
* João da Fonte
* Heitor Farias Santos
* Nina Lira
* Marcelo Caldas
* João Gabriel

---

## ⚙️ Funcionalidades Principais
* **Controle de Acesso Físico:** Destravamento de porta automatizado via leitura de tags RFID.
* **Acionamento em Alternância (Toggle):** Ao ler um cartão válido, a porta abre. Ao ler novamente, a porta fecha.
* **Gestão via Master Card:** Cadastro e remoção de usuários feitos fisicamente aproximando um "Cartão Mestre", sem necessidade de plugar o Arduino no computador.
* **Armazenamento Não-Volátil:** Os UIDs dos cartões cadastrados são salvos na memória EEPROM nativa do Arduino (suporta até 10 cartões no código atual, expansível).
* **100% Offline:** O sistema não depende de internet, servidores externos ou banco de dados em nuvem para funcionar.

---

## 🛠️ Hardware e Componentes
* **Microcontrolador:** Arduino Uno
* **Módulo de Leitura:** Leitor RFID RC522 (Frequência 13.56 MHz).
* **Atuador:** Servo Motor de Rotação Contínua (SG90 modificado / 360º).
* **Mecânica:** Mecanismo de trava impresso em 3D (Cremalheira e Pinhão) e Estrutura do portão cortada a laser em MDF.

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
