Segue a análise formatada para você copiar e colar no GitHub:

---

## - Fluxo TO BE

**Visão geral:**
O processo inicia com o recebimento, via e-mail, de planilha enviada pelo fornecedor contendo a lista de placas disponíveis para leilão. O robô executa as seguintes etapas de forma automatizada:

 **Recebimento e abertura de e-mail**

   * Localizar e-mail com assunto padronizado.
   * Abrir arquivo em anexo que contenha “Lista” no nome.
   * Notificar o usuário caso não encontre o arquivo.

 **Captura e comparação de dados**

   * Abrir planilha base (`Dados_de_saída`) e comparar colunas com arquivo recebido.
   * Capturar dados correspondentes e preencher a planilha base.

 **Marcação de parâmetros químicos**

   * Abrir planilha `Parametro_químico` e comparar parâmetros químicos.
   * Destacar valores fora dos parâmetros com negrito e cor.

**Preenchimento de composição química**

   * Calcular e preencher colunas “Ceq (1)”, “Mn/Si”, “Nb+V+Ti” e “C + Mn/6”.
   * Alterar campo “PLACA COM CABEÇA E/OU CAUDA” conforme regra definida.

**Análises de eventos (Etapas 4, 5, 6 e 7)**

   * Aplicar filtros e comparar dados de eventos nas abas específicas de `Parametro_químico`.
   * Preencher colunas “Parecer CI”, “QSP” e “QSP Máx” conforme regras.

**Análises de normas e aço**

   * Comparar composição química com parâmetros definidos nas abas “Normas” e “Aços”.
   * Preencher campos correspondentes no arquivo base.

**Análise de corte**

   * Comparar composição química com parâmetros da aba “Corte”.
   * Preencher campo “Corte de Placa?” com “Sim” ou “Não” conforme enquadramento.

**Envio de resultados**

   * Enviar relatório final (`Dados_de_saída`) por e-mail para os responsáveis.

---

- Melhorias implementadas no processo

* **Automatização completa do fluxo manual** de análise de placas, reduzindo tempo e eliminando erros de digitação.
* **Integração direta com e-mail corporativo** para captura automática de arquivos recebidos.
* **Comparação de dados parametrizada** com regras de negócio pré-definidas.
* **Preenchimento automático de cálculos complexos**, como índices químicos e lógicas condicionais.
* **Filtragem e classificação de eventos** em múltiplas etapas com registros organizados.
* **Geração automática de relatório consolidado** e envio para stakeholders.

---

## Tratativas em caso de exceções

* **Arquivo não localizado no e-mail**: robô notifica o usuário responsável.
* **Documento de parâmetros ausente**: notificação enviada aos usuários designados.
* **Inconsistência nos nomes de colunas**: processo interrompido e alerta emitido.
* **Valores fora do padrão esperado**: registros destacados para revisão manual.
* **Falha no acesso a diretórios**: mensagem de erro enviada ao time de suporte.

---

## KPI sugeridos

* **Tempo de processamento por execução** (meta: redução mínima de 80% em relação ao processo manual).
* **Número de placas processadas por execução**.
* **Percentual de registros fora do parâmetro** (qualidade da matéria-prima).
* **Taxa de retrabalho** (quantidade de análises manuais após execução do robô).
* **Disponibilidade do robô** (uptime em relação à programação mensal).
* **Tempo médio de resposta para exceções**.

---

## Observações ou destaques

* O fluxo é altamente dependente da **padronização dos arquivos recebidos**. Qualquer mudança de layout pode impactar a execução.
* É recomendável **manter um controle de versão** das planilhas `Parametro_químico` e `Dados_de_saída` para garantir a rastreabilidade.
* As regras de negócio contemplam **valores mínimos, máximos e condições específicas**, exigindo atualização periódica para refletir alterações técnicas.
* A execução é planejada para ocorrer **1 a 2 vezes por mês**, mas pode ser ajustada conforme demanda.
* O processo já está **estruturado para integração futura com sistemas ERP**, o que pode eliminar ainda mais etapas de manipulação de arquivos.

---


