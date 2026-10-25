# Fase 6 - Protótipo interativo V2

Versão corrigida do protótipo da Fase 5. Mantém as sete telas da Fase 4 e os fluxos de consulta de cursos/prazos, entrega e substituição de PDF, calendário e início de questionário, com as mudanças C01–C07 descritas em [MUDANCAS.md](MUDANCAS.md).

Versão anterior (V1, Fase 5): código em https://github.com/oGusta-Campos/ihc-ava-prototipo e protótipo em https://ihc-ava-prototipo.vercel.app.

## Protótipo online

[Link do V2 a definir após publicar no Vercel]

Abra o link no navegador para realizar os testes. A sessão fictícia de estudante já está disponível e não exige matrícula ou senha do AVA.

## Uso local

Extraia o pacote completo. Abra `index.html` no Edge, Chrome ou outro navegador moderno. Mantenha `app.js`, `styles.css` e `Roteiro_Fase5.pdf` na mesma pasta do HTML. Não é necessária uma conta do AVA ou conexão com o Moodle.

Se baixar pelo GitHub, use **Code > Download ZIP**, extraia e abra `index.html` na raiz da pasta do repositório. Não há instalação de dependências nem compilação.

Se o navegador restringir o uso de arquivos locais, o grupo pode servir essa pasta por um servidor HTTP local e abrir a URL fornecida por ele.

## Preparação

1. Abra **Preparação de testes**, no rodapé.
2. Baixe os PDFs original e corrigido para a pasta Downloads.
3. Selecione **Inicial** e clique **Preparar cenário**.
4. Abra a tela do participante e aplique as seis tarefas do roteiro.
5. Registre sucesso, tempo e comentários. Exporte o CSV ao final.

O roteiro `Roteiro_Fase5.pdf` continua valendo; veja em MUDANCAS.md os dois critérios do moderador (T5 e T6) que mudam de texto.

Use **Entrega existente** para preparar T5 quando T4 não tiver sido concluída. O cenário **Falha no primeiro envio** está disponível para o piloto de recuperação; ele não integra as seis tarefas principais.

## Dados e limites

Os dados são fictícios e a data de referência é 13/10/2026. O primeiro vencimento é 14/10/2026 às 23h59. Envios e notas são simulados. O estado e os resultados de teste ficam no navegador, sem sincronização entre dispositivos. O conteúdo de um PDF enviado fica disponível na aba atual; após recarregar, a visualização pode apresentar um PDF de demonstração com o nome registrado. Não utilize credenciais ou documentos reais.

Não foram coletados resultados de estudantes. O registro começa vazio.
