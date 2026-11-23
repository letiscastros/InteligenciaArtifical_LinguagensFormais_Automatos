# DataShare-SE: Classificador de risco e controle de acesso no compartilhamento de arquivos

Sistema especialista com aprendizado supervisionado (Árvore de Decisão + regras SE…ENTÃO) para as classes
`baixo`, `moderado` e `alto` risco em solicitações de compartilhamento corporativo.

**Fonte única de políticas e controles de segurança:** Boas práticas de governança e proteção de dados baseadas na
*Lei Geral de Proteção de Dados Pessoais* (Lei nº 13.709/2018 - LGPD) e na norma *ABNT NBR ISO/IEC 27001:2022*
(controles de transferência de informações e autenticação multifator). Fora do escopo: inspeção de conteúdo/OCR
dos arquivos, bloqueio em tempo real no servidor de e-mail e logs de rede externa.

## Como rodar

## Opção 1: Google Colab (recomendado)
1. Acesse o [Google Colab](https://colab.research.google.com/drive/1O552mT0AqMniH4_vJPCGvVXX8j4glpBp?usp=sharing)
2. Clique em **Arquivo > Abrir notebook > GitHub** e cole o link deste repositório (ou abra o arquivo `datashare_se.ipynb` diretamente).
3. No menu superior, clique em **Ambiente de execução > Executar tudo**.

## Opção 2: Ambiente local
pip install -r requirements.txt
jupyter notebook datashare_se.ipynb

### Arquivos
- `datashare_se.ipynb`: notebook completo (autocontido, com treinamento, matriz de confusão, motor de inferência e análise ética).
- `dados/dataset_risco_compartilhamento.csv`: base com 150 casos históricos de solicitações de compartilhamento (`baixo`, `moderado`, `alto`).
- `dados/regras_seguranca.csv`: base de conhecimento com as 5 regras de produção (`R1` a `R5`), condições e justificativas.
- `tests/casos_teste.csv`: 5 cenários sintéticos para validar o disparo das regras.
- `tests/resultados_esperados.csv`: gabarito esperado (`regra_esperada` e `acao_esperada`) para conferência automática.
- `Ética e Impactos da IA DataShare_SE.pdf`: avaliação ética completa, dilema prático, referências e declaração de uso de IA.

### Regras de decisão (Base de Conhecimento)
- **R1:** `SE` `nivel_sensibilidade == 4` (restrito) `E` `pct_externos > 0`, `ENTÃO` bloquear compartilhamento.
- **R2:** `SE` `risco == 'alto'` `E` `autenticacao_forte == False`, `ENTÃO` bloquear e exigir MFA.
- **R3:** `SE` `risco == 'alto'` `E` `autenticacao_forte == True`, `ENTÃO` revisar permissões e aprovar com prazo.
- **R4:** `SE` `risco == 'moderado'` `E` `autenticacao_forte == False`, `ENTÃO` solicitar MFA antes de liberar.
- **R5:** `SE` `risco == 'baixo'` `OU` (`risco == 'moderado'` `E` `autenticacao_forte == True`), `ENTÃO` liberar compartilhamento.

## Conferência e validação
Os 5 cenários de `tests/casos_teste.csv` foram conferidos contra `tests/rotulos_ouro.csv`, validando 100% do
encadeamento para frente (`R1` a `R5`). O modelo de Árvore de Decisão obteve **76,3% de acurácia** na classificação
do risco inerente antes da aplicação das regras de segurança, registrando os passos da decisão (*"Como?"* e *"Por quê?"*).

## Limitações conhecidas
O sistema avalia apenas os metadados declarados na solicitação (`nivel_sensibilidade`, `nivel_permissao`,
`qtd_destinatarios`, `pct_externos` e `autenticacao_forte`). Se um arquivo confidencial for classificado
incorretamente como público pelo usuário, a regra `R1` não será disparada. Os 150 casos de treinamento são
sintéticos (princípio da minimização de dados) e casos de alto risco com MFA ativo (`R3`) exigem revisão humana
pela equipe de Segurança da Informação / TI.

## Autoria
- **Aluno 1:** Letícia Castro de Souza
- **RGM:** 38214245

- **Aluno 2:** Lucas Eduardo Barreto de Oliveira
- **RGM:** 42751969

- **Disciplina:** Inteligência Artificial, Linguagens Formais e Autômatos - UDF
- **Professora:** Profa. Kadidja Valéria

## Licença
Este projeto está licenciado sob a **Licença MIT**, conforme especificado no arquivo `LICENSE` na raiz deste repositório.
