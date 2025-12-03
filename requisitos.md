# 📄 Compras PCP - Regras de Negócio


* **Recebimento de e-mail**

  * O robô deve processar apenas e-mails com assunto padronizado contendo “Placas Overcasting TxBr”.
  * O anexo processado deve ser um arquivo Excel contendo a palavra “Lista” no nome.
  * Caso não seja encontrado, notificar os usuários responsáveis.

* **Processamento da planilha**

  * Comparar colunas do arquivo recebido com o arquivo base (`Dados_de_saída`) usando o mapeamento de nomes idênticos.
  * Capturar somente colunas que tenham nomes iguais entre origem e destino.

* **Parâmetros químicos**

  * Comparar elementos químicos com os limites definidos no arquivo `Parametro_químico`.
  * Destacar (negrito e cor) valores acima dos limites estabelecidos.

* **Cálculos químicos**

  * Colunas como “Ceq (1)”, “Mn/Si”, “Nb+V+Ti” e “C + Mn/6” devem ser calculadas conforme fórmulas definidas.
  * Condições específicas, como %SI = 0, devem ser tratadas com valores padrões (ex.: 99).

* **Classificação de eventos**

  * Aplicar filtros específicos (ex.: final “250” ou “750”) e preencher campos conforme mapeamento.
  * Eventos “1”, “2” e “3” devem seguir as regras das abas correspondentes no `Parametro_químico`.

* **Normas e aço**

  * Comparar composição química com parâmetros mínimos e máximos definidos.
  * Capturar e preencher normas e aço para placas dentro dos parâmetros.

* **Corte de placa**

  * Determinar “Sim” ou “Não” conforme enquadramento nos parâmetros da aba “Corte”.

* **Encerramento**

  * Enviar relatório `Dados_de_saída` por e-mail aos destinatários pré-definidos.
  * Salvar arquivos processados nos diretórios definidos no mapeamento.

---

## - Validações Necessárias

* **Validação de entrada**

  * Confirmar se o e-mail segue o padrão de assunto.
  * Confirmar existência do anexo e se está no formato esperado (Excel).
  * Confirmar presença da palavra “Lista” no nome do arquivo.

* **Validação de dados**

  * Checar se todas as colunas necessárias estão presentes no arquivo recebido.
  * Validar se os dados numéricos estão no formato correto e não apresentam valores nulos onde não permitido.
  * Verificar se o arquivo `Parametro_químico` está disponível e atualizado.

* **Validação de processamento**

  * Garantir que todos os cálculos sejam executados sem erro (evitar divisões por zero).
  * Garantir que todas as regras de comparação sejam aplicadas célula a célula.
  * Confirmar que todos os campos obrigatórios no `Dados_de_saída` foram preenchidos.

* **Validação de saída**

  * Conferir se o relatório final contém todos os registros processados.
  * Conferir se campos destacados em negrito correspondem corretamente a valores fora do parâmetro.
  * Confirmar se todos os e-mails de saída foram enviados com sucesso.

---

## - Saídas Esperadas

* **Relatório consolidado** (`Dados_de_saída`) contendo:

  * Dados originais enriquecidos com cálculos e classificações.
  * Valores químicos destacados quando fora do parâmetro.
  * Campos de eventos, normas, aço e corte preenchidos conforme regras.
* **Arquivo de análise final** (se aplicável) pronto para revisão pela equipe.
* **E-mails enviados** para todos os destinatários definidos.
* **Arquivos salvos** nos diretórios determinados para histórico.

---

## - Critérios de Sucesso

* **Cobertura completa do processo**: 100% dos e-mails e anexos recebidos dentro do padrão processados corretamente.
* **Precisão nos cálculos**: 100% das fórmulas aplicadas sem erro e de acordo com as regras de negócio.
* **Integridade dos dados**: todos os registros processados sem perda ou alteração indevida.
* **Classificação correta**: todos os eventos, normas, aço e corte aplicados corretamente conforme parâmetros definidos.
* **Envio bem-sucedido**: 100% dos relatórios finais enviados para os destinatários previstos.
* **Tempo de execução**: redução significativa do tempo em comparação ao processo manual (meta mínima de 80% de ganho).
* **Ausência de falhas críticas** durante a execução do robô.

---



