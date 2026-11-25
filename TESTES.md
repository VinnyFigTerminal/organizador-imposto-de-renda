# Roteiro de testes

Use uma cópia do modelo e selecione **2025** como ano-calendário. Os dados abaixo são fictícios.

| Grupo | Pessoa | Descrição | Data | Valor | Comprovante | Local ou referência | Resultado esperado |
|---|---|---|---|---:|---|---|---|
| Rendimentos | Titular | Informe de rendimentos | 31/12/2025 | R$ 800 | Pendente | Em branco | Falta comprovante |
| Bens e direitos | Titular | Saldo anual | 31/12/2025 | R$ 100 | Recebido | Pasta 2025 | Completo |
| Pagamentos e doações | Titular | Recibo | 01/01/2026 | R$ 300 | Recebido | Pasta 2025 | Revisar data |

O recálculo com essas três linhas apresentou **3 registros lançados**, **2 a revisar** e **1 comprovante pendente**. As linhas vazias ficaram sem status.

## Verificações manuais adicionais

- Tente inserir uma situação de comprovante fora da lista.
- Remova a referência do segundo registro. A conferência deve exibir **Indicar local**.
- Filtre a coluna **Conferência** para localizar apenas as linhas com pendência.
- Use **Abrir registros** no painel e **Voltar ao painel** no cadastro.
