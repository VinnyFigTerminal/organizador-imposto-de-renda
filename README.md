# Organizador de Imposto de Renda

Planilha Excel para reunir informações e acompanhar comprovantes antes de preencher a declaração de Imposto de Renda da Pessoa Física (IRPF).

[Baixar a planilha modelo](./Organizador_Imposto_de_Renda.xlsx) · [Consultar o roteiro de testes](./TESTES.md)

## O que a ferramenta resolve

- Centraliza informações de rendimentos, pagamentos e doações, bens e direitos, dívidas e ônus, imposto retido ou pago e outras informações.
- Mostra quantos itens foram lançados, quantos precisam de revisão e quantos comprovantes ainda estão pendentes.
- Permite filtrar os registros por grupo, pessoa, situação do comprovante ou resultado da conferência.
- Oferece atalhos entre as abas e para os serviços do e-CAC.

## Como usar

1. Abra a planilha no Excel e salve uma cópia local para cada ano-calendário.
2. Na aba **Painel**, informe o ano das informações a reunir e clique em **Abrir registros**.
3. Na aba **Registros**, preencha uma linha por item. Escolha o grupo, informe a pessoa vinculada e identifique a fonte ou descreva o item. Preencha CPF/CNPJ, data e valor quando couber.
4. Em **Comprovante**, selecione **Pendente**, **Recebido** ou **Não se aplica**. Se estiver recebido, preencha **Local ou referência** com uma indicação que permita encontrá-lo.
5. Filtre a coluna **Conferência** para revisar as linhas sinalizadas e volte ao **Painel** para acompanhar os totais.

## Como a planilha funciona

| Recurso | Implementação |
|---|---|
| Painel | A célula B6 define o ano-calendário. As fórmulas contam registros, itens a revisar e comprovantes pendentes. O resumo também mostra a contagem por grupo. |
| Cadastro | A tabela `RegistrosIR` tem 300 linhas preparadas, com filtros e cabeçalho congelado. |
| Validação de entrada | Listas suspensas padronizam grupo e situação do comprovante. Há validação numérica para ano e valor. |
| Conferência | A coluna J analisa cada linha preenchida. Aponta grupo inválido, cadastro incompleto, data fora do ano-calendário, valor não numérico, comprovante pendente ou indicação de local ausente. Exibe o primeiro problema encontrado na linha. |
| Navegação | Hiperlinks permitem abrir os registros, voltar ao painel e acessar o e-CAC. |

O contador **Registros a revisar** inclui todas as linhas preenchidas cujo status difere de **Completo**. O contador **Comprovantes pendentes** considera as linhas marcadas como **Pendente** na coluna de comprovante. Uma mesma linha pode aparecer nos dois contadores.

## Decisões do projeto

O cadastro único mantém todos os grupos no mesmo formato e permite filtrar informações sem percorrer várias tabelas. A coluna de conferência indica o próximo ajuste de cada linha, enquanto o painel mostra o que ainda precisa de revisão no conjunto. O projeto usa recursos nativos do Excel, incluindo tabelas, validação de dados, formatação condicional e fórmulas. Funciona sem macros.

O arquivo publicado contém o modelo em branco. Mantenha cópias preenchidas e comprovantes fora do repositório público. A conferência cobre o preenchimento do modelo. A apuração e a transmissão da declaração são feitas nos canais da Receita Federal.
