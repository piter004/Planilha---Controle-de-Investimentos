# Simulador de Investimentos em FIIs

Ferramenta desenvolvida no Excel para simulação de investimentos em Fondos Imobiliários (FIIs), planejamento de patrimônio a longo prazo e alocação estratégica por perfil de investidor.

---

## Perguntas que a ferramenta responde (e onde encontrar)

A planilha foi desenhada para responder a 5 perguntas centrais de planeamento financeiro:

1. Quanto investir por mês? 
   Onde aparece: Na aba `APP`, no bloco INVESTIMENTO MENSAL (Célula `D17`).
2. Em quanto tempo pretendo investir (anos)?  
   Onde aparece: Na aba `APP`, no bloco INVESTIMENTO MENSAL (Célula `D18`).
3. Qual a taxa de rendimento mensal estimada? 
   Onde aparece: Na aba `APP`, no bloco INVESTIMENTO MENSAL (Célula `D19`).
4. Qual será o meu património acumulado?
   Onde aparece: Na aba `APP`, no bloco INVESTIMENTO MENSAL (Célula `D20`) e detalhado por prazos na tabela de **Cenários** (Linhas 24 a 28, Coluna `C`).
5. Quanto receberei de dividendos mensais?  
   Onde aparece: Na aba `APP`, no bloco INVESTIMENTO MENSAL (Célula `D21`) e na tabela de Cenários (Linhas 24 a 28, Coluna `D`).

---

## Como o `VF` e o `PROCV` entram nos cálculos

* Função `VF` (Valor Futuro):
  Utilizada para calcular o património acumulado ao longo do tempo com base em aportes mensais recorrentes e numa taxa de juro composta.
  Sintaxe aplicada: `=VF(taxa_mensal; anos * 12; -aporte_mensal)`
  Exemplo na célula `D20`: `=VF(D19; D18*12; -D17)`

  Função `PROCV` (ou `ÍNDICE`/`CORRESP`): 
  Utilizada para procurar dinamicamente a percentagem de alocação de cada tipo de FII (Papel, Tijolo, Híbridos, FOFs, Desenvolvimento, Hotelarias) de acordo com o perfil selecionado (`Conservador`, `Moderado` ou `Agressivo`).
  Funcionamento: A fórmula consulta a tabela usando a combinação do perfil selecionado com o tipo de FII para retornar a percentagem exata de alocação na tabela principal.
