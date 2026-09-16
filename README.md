# Atividade Integradora - Relatório Operacional de Pré-Decolagem

## Objetivo
Simular um sistema de decisão de pré-decolagem a partir de dados de telemetria, verificando parâmetros operacionais, calculando a condição energética e apresentando uma decisão final.

## Arquivos
- `pre_decolagem.ipynb`: notebook Python com a implementação.
- `Relatorio_Operacional_Pre_Decolagem.pdf`: relatório completo.

## Dados e premissas
- A atividade mostra os requisitos, mas não apresenta uma tabela numérica completa. Por isso, este projeto usa dados simulados para demonstrar a solução:
- Temperatura interna: 22,4 °C
- Temperatura externa: 18,7 °C
- Integridade estrutural: 1
- Energia: 86%
- Pressão dos tanques: 310 kPa
- Módulos críticos: OK

Faixas didáticas adotadas:
- Temperatura interna: 18 a 27 °C
- Temperatura externa: -20 a 45 °C
- Integridade estrutural: 1
- Energia mínima: 70%
- Pressão dos tanques: 280 a 340 kPa
- Módulos críticos: OK

## Execução

1. Acesse o Google Colab.
2. Clique em **Arquivo > Fazer upload de notebook**.
3. Selecione o arquivo `pre_decolagem.ipynb`.
4. Execute as células na ordem.
5. Confira os resultados apresentados pelo programa.

## Print da execução

Abaixo está o resultado da execução do código no Google Colab:

![Execução do projeto no Google Colab](execucao.png)

## Resultado do cenário
Todos os parâmetros simulados estão dentro das faixas adotadas. O resultado é `PRONTO PARA DECOLAR`.

