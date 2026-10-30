<div align="center">

# 📄 sql2docx

**Transforme suas consultas do MySQL Workbench em um relatório Word pronto para entregar.**

![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?logo=javascript&logoColor=black)
![Formato](https://img.shields.io/badge/sa%C3%ADda-.docx%20A4-2B579A?logo=microsoftword&logoColor=white)
![Offline](https://img.shields.io/badge/funciona-offline-0B6E8A)
![Dependências](https://img.shields.io/badge/depend%C3%AAncias-zero-2EA44F)

[✨ Recursos](#-recursos) · [🚀 Como usar](#-como-usar) · [🧩 Formatos](#-formatos-aceitos-para-a-tabela-de-resultado)

</div>

---

## 🎯 Para que serve

Em atividades de banco de dados, o professor costuma pedir a **consulta** e o **resultado** de cada exercício em um documento Word. Montar isso na mão é repetitivo: copiar a query, tirar print, redimensionar, formatar.

O **sql2docx** faz essa montagem por você e entrega um documento padronizado, em **A4**, pronto para enviar.

> 💡 É um único arquivo HTML. Sem servidor, sem instalação, sem internet. Abra no navegador e use.

---

## ✨ Recursos

| | Recurso | Descrição |
|---|---|---|
| 🔍 | **Extração automática** | Separa o script `.sql` em exercícios, usando os comentários como enunciado |
| 🖼️ | **Prints do resultado** | Cole com `Ctrl+V`, arraste ou escolha o arquivo |
| 📊 | **Tabelas editáveis** | Cole o grid do Workbench ou valores separados por vírgula |
| 🧑‍💻 | **Código formatado** | Consulta em fonte monoespaçada com fundo cinza |
| 📐 | **Página A4** | Margens de 2 cm e imagens ajustadas à largura |
| 🔒 | **Privado** | Nada sai do seu computador |
| ⚡ | **Zero dependências** | HTML, CSS e JavaScript puros |

---

## 🚀 Como usar

1. 📂 Abra o `index.html` no navegador.
2. 📝 Preencha o **cabeçalho**: título, aluno, professor, disciplina e data. Esses dados ficam salvos para a próxima vez.
3. 📋 Cole o conteúdo do seu `.sql` (ou use **Abrir arquivo .sql**) e clique em **Separar em exercícios**.
4. 🖼️ Em cada exercício, adicione o resultado:
   - **Imagem:** tire um print no Workbench e cole com `Ctrl+V` na caixa tracejada.
   - **Tabela:** copie o grid de resultado (`Ctrl+C`) e cole no campo de tabela, ou digite os valores separados por vírgula.
5. ↕️ Reordene ou exclua exercícios, se precisar.
6. ⬇️ Clique em **Baixar .docx (A4)**.

---

## 🧠 Como o script é separado

- 💬 Cada comentário `-- ...` antes de uma consulta vira o **enunciado** do exercício.
- 🔚 Cada consulta termina em `;` e vira **um exercício**.

```sql
-- Qual é o comando para encontrar produtos com nome "Croissant" e que tenham mais de 30 unidades no estoque
SELECT nome, quantidade_estoque
FROM padaria_produtos
WHERE nome LIKE '%Croissant%' AND quantidade_estoque > 30;
```

---

## 🧩 Formatos aceitos para a tabela de resultado

| Formato | Exemplo |
|---|---|
| 📋 Copiado do Workbench (colunas separadas por tab) | `nome⇥quantidade_estoque` |
| 🔤 Valores separados por vírgula, com ou sem aspas | `'Croissant','40.000'` |
| ␣ Colunas separadas por dois ou mais espaços | `Croissant   40.000` |

- Use **uma linha por registro**.
- Vírgulas dentro de aspas **não** separam colunas: `'Pão, integral','12'` tem duas colunas.
- A caixa **"Primeira linha das tabelas de resultado é o cabeçalho"** controla se a primeira linha aparece destacada como nome das colunas. Desmarque quando colar só os dados.

---

## 📑 O que sai no documento

```
┌──────────────────────────────────────┐
│  Atividade de SQL                    │
│  Aluno · Professor · Disciplina · Data│
│                                      │
│  Exercício 1                         │
│  Enunciado                           │
│  ┌────────────────────────────────┐  │
│  │ SELECT ... FROM ... WHERE ...; │  │
│  └────────────────────────────────┘  │
│  Resultado                           │
│  [ imagem e/ou tabela ]              │
│                                      │
│  Exercício 2 ...                     │
└──────────────────────────────────────┘
```

- ✅ Página **A4**, margens de 2 cm
- ✅ Imagens redimensionadas automaticamente
- ✅ Tabelas editáveis no Word

---

## 🛠️ Detalhes técnicos

<details>
<summary>Clique para expandir</summary>

<br>

- HTML, CSS e JavaScript puros, **sem bibliotecas**.
- O `.docx` é montado direto no navegador (pacote ZIP com XML do Office Open).
- Nenhum dado é enviado para servidor algum.
- Apenas os campos do cabeçalho são guardados no `localStorage`.

</details>
---

<div align="center">

Feito para facilitar a entrega de atividades de SQL

</div>
