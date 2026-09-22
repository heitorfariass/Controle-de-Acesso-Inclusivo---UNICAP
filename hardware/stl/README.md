# 🖨️ Mecânica — Peças Impressas em 3D

Mecanismo de trava **cremalheira e pinhão** do Sistema Robótico de Destravamento com RFID (UNICAP).

> 📖 Contexto: a primeira versão mecânica, em MDF cortado a laser, não funcionou como esperado — o mecanismo foi redesenhado para impressão 3D. Os arquivos abaixo são os **utilizados na versão final do protótipo**.

## Peças

| Arquivo | Peça | Função |
| :--- | :--- | :--- |
| [`gear.stl`](gear.stl) | Pinhão (engrenagem) | Acoplado ao servo de rotação contínua; converte rotação em movimento linear |
| [`gear_rack.stl`](gear_rack.stl) | Cremalheira | Trava linear acionada pelo pinhão |
| [`motor_holder.stl`](motor_holder.stl) | Suporte do motor | Fixa o servo à estrutura do portão |
| [`rack_holder.stl`](rack_holder.stl) | Suporte da cremalheira | Guiamento e fixação da cremalheira |

## Parâmetros de impressão utilizados

> ✏️ **A ajustar pela equipe** — confirme os valores da impressão real (a tabela já é referenciada no README).

| Parâmetro | Valor |
| :--- | :--- |
| Material | PLA |
| Altura de camada | 0,2 mm |
| Preenchimento (infill) | — % |
| Suportes | Sim / Não |
| Bordas (brim) | — |
| Tempo aproximado de impressão | — |

## Dica

Se as peças foram modeladas em Tinkercad, Fusion 360 ou similar, considere subir também
o arquivo de origem (`.f3d`, `.step`, link do projeto) para facilitar a reprodução por
outros estudantes.
