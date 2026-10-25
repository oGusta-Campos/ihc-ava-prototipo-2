# Mudanças do protótipo v1 → v2

O v2 parte do código do v1 (Fase 5, [ihc-ava-prototipo](https://github.com/oGusta-Campos/ihc-ava-prototipo), online em https://ihc-ava-prototipo.vercel.app) e implementa as sete mudanças C01–C07 listadas no modelo do relatório da Fase 6.

> **Atenção:** os problemas U01–U06 que motivam estas mudanças vêm do *modelo* da Fase 6, que usa dados simulados. As mudanças se apoiam também nos achados das Fases 3 e 4 (P01–P11, V01–V07), mas a tabela abaixo precisa ser revista quando os testes reais forem feitos: um problema pode não se confirmar e outros podem aparecer.

As capturas estão em [`docs/antes-depois/`](docs/antes-depois/), sempre no mesmo recorte de tela (`v1_…` e `v2_…`).

## Resumo

| ID | Origem | Telas | Antes (v1) | Depois (v2) |
|----|--------|-------|-----------|-------------|
| C01 | U04 · P08, V06 | S3, S4, S5 | "Substituir envio" só aparecia na confirmação, dentro de um aviso no fim do recibo. Na lista, a tarefa entregue mostrava apenas "Ver envio". | A linha da tarefa entregue (lista da disciplina e agenda) tem o botão **Substituir envio** ao lado de "Ver envio". Na confirmação, o botão fica na linha de ações principais. A tela de substituição avisa que **o arquivo atual será descartado** e só o novo vale. |
| C02 | U01 · P01 | S1 (e S2, S6) | Seletor "Período" pequeno no cabeçalho, à direita, sem indicação do período no título. | Seletor **Período letivo** em destaque no topo de Meus cursos, e o título mostra o período ativo (**Meus cursos · 2026/2**). O mesmo seletor aparece como primeiro filtro na Agenda e no Calendário; trocar o período mantém o aluno na tela atual. |
| C03 | U02 · P06, P10, P11, V07 | S2, S6 | Calendário diferenciava tipos só pelos símbolos □ ○ △; a aula aparecia misturada aos prazos. Agenda sem rótulo de tipo de data. | Cada item tem rótulo com texto e ícone: **Vencimento** (relógio, fundo escuro) ou **Evento** (calendário, borda tracejada). Agenda e calendário abrem com **Mostrar: Somente prazos**; "Prazos e eventos" inclui aulas. Legenda explica a diferença. |
| C04 | U03 · V02 | S2, S3, S4 | Grupo "Sem prazo cadastrado" no fim da agenda; na disciplina a tarefa sem data ficava por último. | Grupo **Aberta — sem data limite · N** no topo da agenda, em caixa destacada, com o texto "isso não significa que a atividade foi encerrada". Na disciplina a tarefa sem data vem primeiro, com situação "Pendente · aberta, sem data limite". |
| C05 | U05 · P09 | S7, S3 | Lista mostrava só "Tentativa em andamento"; ao sair, nenhuma confirmação de que dava para voltar. | Lista, tela do questionário e tela da tentativa mostram **Tentativa em andamento (1 de 2) — você pode continuar depois**. "Sair e continuar depois" volta à lista com aviso de que a tentativa foi salva. |
| C06 | U06 · P07, V04 | S5 | Recibo mostrava "Versão da entrega: 2 · o arquivo anterior foi substituído". | Recibo mostra **Arquivo substituído em 13 out 2026, 19hMM; o anterior não vale mais**, o nome do arquivo que vale e o anterior riscado como "descartado". O horário avança a cada envio (relógio simulado). |
| C07 | U02 | S1, S2 | Próximo vencimento só com data e hora absolutas. | Prazo relativo (**vence amanhã**, **vence em 3 dias**) no resumo, nos cartões, na agenda, na lista da disciplina e no detalhe. **Lembrete** no topo de Meus cursos e da Agenda com o próximo vencimento pendente e atalho para a atividade (pode ser dispensado). |

No modelo da Fase 6, C07 estava como "Fase 7" (esforço alto). Ela foi feita agora porque, no protótipo com data fixa, o custo foi baixo. Se o grupo preferir manter a matriz impacto × esforço do relatório, basta mudar o status de C07 para "Feito na v2".

## Detalhe por mudança

### C01 · Substituir envio onde o erro é percebido
- Capturas: `v1_S3_apos_envio.png` × `v2_S3_apos_envio.png`; `v1_S5_confirmacao.png` × `v2_S5_confirmacao.png`; `v1_S4_substituir.png` × `v2_S4_substituir.png`.
- O botão só aparece enquanto o prazo está aberto (a Lista EB03, vencida, não oferece substituição).

### C02 · Período letivo no topo
- Capturas: `v1_S1_meus_cursos.png` × `v2_S1_meus_cursos.png`.
- O seletor saiu do cabeçalho global.

### C03 · Vencimento × evento
- Capturas: `v1_S6_calendario.png` × `v2_S6_calendario.png` e `v2_S6_calendario_eventos.png`; `v1_S2_agenda.png` × `v2_S2_agenda.png` e `v2_S2_agenda_eventos.png`.
- O filtro "Tipo" (Tarefa/Questionário/Evento) do calendário foi trocado por "Mostrar"; na agenda, "Tipo" continua para separar tarefas de questionários.

### C04 · "Aberta — sem data limite"
- Capturas: `v1_S2_agenda.png` × `v2_S2_agenda.png`; `v1_S4_tarefa_sem_data.png` × `v2_S4_tarefa_sem_data.png`.

### C05 · Estado da tentativa
- Capturas: `v1_S3_tentativa_em_andamento.png` × `v2_S3_tentativa_em_andamento.png`; `v1_S7_tentativa.png` × `v2_S7_tentativa.png`; `v1_S7_quiz_apos_iniciar.png` × `v2_S7_quiz_apos_iniciar.png`.

### C06 · Rótulo da substituição
- Capturas: `v1_S5_substituido.png` × `v2_S5_substituido.png`.

### C07 · Prazo relativo e lembrete
- Capturas: `v1_S1_meus_cursos.png` × `v2_S1_meus_cursos.png`; `v1_S2_agenda.png` × `v2_S2_agenda.png`.

## Outras alterações técnicas
- Estado salvo com outra chave (`ihc-fase6-v2`), para v1 e v2 não se misturarem no mesmo navegador.
- Rodapé e faixa de demonstração identificam a versão V2.
- Telas no celular (390 px) conferidas sem rolagem horizontal da página: `v2_mobile_S1.png`, `v2_mobile_S2.png`.

## Efeito no roteiro de testes (T1–T6)
As instruções lidas ao participante não mudam. Dois critérios do moderador precisam de ajuste de texto:
- **T5:** "Confirma o novo nome e a versão 2 da entrega" → "Confirma o novo nome e a mensagem de que o arquivo anterior foi substituído e não vale mais".
- **T6:** "identifica Tentativa em andamento" → "identifica Tentativa em andamento (1 de 2)".

O lembrete de C07 mostra o próximo vencimento direto em Meus cursos, então T2 tende a ficar mais rápida no v2. Isso é o efeito esperado da mudança e deve ser comentado ao comparar v1 e v2 na Fase 7.
