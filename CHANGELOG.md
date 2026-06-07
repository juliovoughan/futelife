# Changelog

Convencao de versao: `x.yz`

- `x`: grandes atualizacoes/fases estruturais.
- `y`: pequenas mecanicas adicionadas, removidas ou alteradas.
- `z`: bug fixes, balanceamento pontual e correcoes de integridade.

## 2.00 - Fase 15: Database Mundial Base/State

- Criada a estrutura normalizada em `data/` com jogadores por nacionalidade, clubes, staff, ligas, copas e `world_manifest.json`.
- IndexedDB agora separa stores base imutaveis de stores state modificaveis da carreira.
- Loader mundial compara versoes do manifest e importa/reimporta apenas dados base alterados.
- Adicionado adaptador que hidrata ligas normalizadas para o formato atual usado por `GLOBAL_BASES`.
- Export/import agora suporta pacote v15 com save, configuracao e states por store sem exportar a base.
- Reset normal preserva dados base e apaga apenas save/config/states.

## 1.20 - Fase 14: Polimento de Liga e Midia

- Tabela da liga agora abre em formato visual, com colunas de campanha e proximo adversario.
- Card de tabela na Home mostra posicao e proximo adversario com mais clareza.
- Arquivo de Midia categoriza noticias como Rumor, Midia, Clube, Jogador ou Noticia.

## 1.12 - Fundo de Tunel e Layout da Noticia

- Registrada a imagem `backgrounds/tunnel.png` como fundo da reuniao pre-jogo.
- Reuniao pre-jogo agora aplica o fundo do tunel com overlay escuro para preservar legibilidade.
- Reposicionado o texto do destaque de midia para a area interna correta da moldura `News.png`.

## 1.11 - Ajuste de Assets de Midia, Treino e Partida

- Removida a arte vazia de midia do registro recente da Home.
- Home agora trata a lista como registro recente, enquanto a tela Midia concentra noticias e rumores.
- Midia ganhou destaque clicavel com manchete sobreposta em `News.png` e arquivo de noticias.
- Partidas agora escolhem variantes de campo por contexto de rodada.
- Tela de treino ganhou banner visual proprio para tornar a imagem mais legivel.

## 1.10 - Etapa 13.0: Registro de Assets Existentes

- Preenchido `assets/assets_manifest.json` com as imagens reais ja geradas.
- Adicionado fallback interno de manifesto para o HTML continuar funcionando sem a pasta `assets/`.
- Telas de criacao, home, treino, midia e partida agora usam fundos opcionais quando as imagens existem.
- Vida Pessoal agora mostra a imagem da moradia atual quando o asset estiver disponivel.
- Partidas agora escolhem variantes de campo por contexto de rodada: dia, entardecer ou noite.
- Treino ganhou um banner visual proprio no topo da tela, em vez de depender apenas de fundo escuro.
- A arte de midia virou destaque clicavel com manchete sobreposta e arquivo de noticias na tela Midia.
- Atualizado `IMAGENS_NECESSARIAS.md` com status de imagens prontas, fallback e pendentes.

## 1.01 - Hotfix de Simulacao, Salarios e Assets Opcionais

- Corrigida a configuracao de simulacao global com acoes explicitas para selecionar todas e limpar selecao.
- Modo "Todas as 6 ligas" agora tambem preenche a lista de ligas ativas para evitar estado visual vazio.
- Salarios foram padronizados como valores semanais internos e exibidos tambem como estimativa mensal.
- Pagamento semanal e imposto foram alinhados com a nova unidade salarial.
- Salarios iniciais, propostas e database estimada foram rebalanceados.
- Criada a estrutura opcional `assets/` e o documento `IMAGENS_NECESSARIAS.md` para preparar a Etapa 13.

## 1.00 - Fase 12: Simulacao Global de Ligas

- Adicionado wrapper IndexedDB `futelife_db` com stores para save, configuracao, ligas base e ligas state.
- Adicionada migracao hibrida: saves antigos em localStorage continuam carregando e passam a ser copiados para IndexedDB.
- Adicionados arquivos JSON externos em `outputs/data/` para as 6 ligas iniciais em tamanho real.
- Calendario de liga agora usa round-robin realista conforme o tamanho da competicao.
- Tabelas e resultados passam a usar state global persistido por liga.
- Perfil ganhou configuracao de simulacao: so minha liga, ligas selecionadas ou todas.
- Export/import agora suporta pacote v12 com save, configuracao e states das ligas.

## 0.42 - Correcoes de Plantel e Licencas

- Corrigida substituicao manual no intervalo: agora escolhe primeiro quem sai e depois quem entra.
- Gestao de plantel agora mostra a proxima janela de transferencia quando a janela atual esta fechada.
- Pedido de licenca nao mostra mais "fama 0" como requisito falso e exibe o estado atual dos requisitos.
- Ajustada recuperacao de energia pos-jogo do treinador para tornar derrotas e sequencias tensas menos generosas.

## 0.41 - Fase 11 v2 Final

- Adicionada gestao simples de plantel no modo treinador, com contratacoes e dispensas durante janelas.
- Adicionado orcamento do clube separado do dinheiro pessoal do treinador.
- Adicionados mercado de candidatos, limite de 3 movimentos por janela e reset por janela.
- Jogadores do elenco agora possuem ego, jogos, banco e insatisfacao.
- Ambiente do clube agora mostra alertas de moral/ego e afeta grupo, torcida e diretoria.
- Plantel persistente registra participacao em partida e pode gerar crise semanal.

## 0.40 - Treino do Time, Elenco Persistente e Licencas

- Modo treinador agora usa treino coletivo do time em vez de evoluir atributos pessoais.
- Adicionado elenco persistente simples do clube, com onze inicial e banco.
- Partidas do treinador passam a usar o elenco persistente do clube.
- Adicionado sistema de licencas C/B/A/Pro com cursos aprovados pela diretoria.
- Cursos de treinador avancam semanalmente e melhoram reputacao/OVR ao concluir.
- Treinos coletivos aplicam ganhos de 1 a 6 ao elenco, influenciados por moral, energia, idade, potencial e licenca.

## 0.32 - Bugfix de Treinador, Midia e Estado

- Corrigido estado de passe livre para resetar status do clube e liga.
- Protegidas noticias contra texto indefinido.
- Corrigido popup de tatica para atualizar selecoes sem prender o jogador.
- Mini-card da diretoria agora mostra objetivo em andamento durante a temporada.
- Midia manual agora mostra bloqueio visual e feedback quando o limite semanal ja foi usado.
- Corrigida criacao de treinador para inicializar elenco, licenca e noticia sem formacao indefinida.

## 0.31 - Correcoes do Modo Treinador e Liga

- Corrigido exploit da promessa "Evitar rebaixamento", que agora e avaliada no fim da temporada.
- Corrigido OVR inicial do treinador e recalculo do OVR apos treinos.
- Adicionada a formacao `5-3-2` ao menu de taticas do treinador.
- Resetado estado de liga, tabela, rodada simulada e status do clube ao trocar de clube.
- Mini-card da home agora mostra objetivo da diretoria para treinadores.
- Sincronizada `G.rodada` durante semanas/partidas.
- Calendario agora mostra janela de transferencia mesmo em semanas de partida.
- Ajustados botao de tatica e ordinal de posicao na tabela/home.

## 0.30 - Modo Treinador, Liga e Calendario

- Adicionada tabela de liga local com simulacao das outras partidas da rodada.
- Resultados do jogador/treinador agora entram na classificacao e afetam status do clube.
- Adicionados status abstratos de confianca do grupo, torcida e diretoria.
- Adicionadas taticas do treinador com formacao, estilo e modificadores de partida.
- Calendario da home agora mostra mando de campo e janela de transferencia.
- Objetivos da diretoria agora sao avaliados no fim da temporada, com risco de demissao.
- Saves antigos agora recebem defaults seguros para tabela, status do clube e tatica.

## 0.21 - Correcoes de Midia e Intervalo

- Corrigido reset de `G.palestraUsada` ao preparar nova partida.
- Bloqueada abertura de popup manual de midia quando o limite semanal ja foi atingido.
- Adicionado `famaReq` explicito nas entrevistas de midia.

## 0.20 - Midia, Fama e Patrocinios

- Implementada a tela de Midia com resumo de imagem publica, seguidores, entrevistas e patrocinios.
- Adicionadas entrevistas com escolhas que afetam fama, moral, entrosamento e seguidores.
- Adicionados eventos de redes sociais com consequencias e historico recente.
- Adicionados patrocinios desbloqueados por fama, com premio inicial e renda semanal.
- Adicionada migracao segura para saves antigos com o novo estado `midia`.
- Limitadas acoes manuais de midia a uma por semana para evitar farm infinito.

## 0.10 - Intervalo v2 e Notas de Partida

- Adicionado intervalo automatico aos 45 minutos com pausa real da partida.
- Adicionado sistema temporario de notas de partida para player e NPCs.
- Popup de intervalo agora mostra placar, energia, nota do player, destaques e jogadores cansados.
- Player recebe fala/instrucao automatica do tecnico no intervalo.
- Treinador pode escolher instrucao da segunda parte: pressao, motivacao ou ajuste tatico.
- Substituicoes manuais no intervalo foram adicionadas ao painel de elenco para treinador.
- Popup final da partida agora mostra nota final e melhor em campo.

## 0.01 - Correcoes de Playtest

- Travado o exploit de reroll infinito na reuniao pre-jogo com `G.reuniaoFeita`.
- Rebalanceada a formula do D20 da reuniao pre-jogo para reduzir sucesso quase garantido.
- Melhorada a conversao de assistencias: companheiro recebe bonus de finalizacao quando o jogador acerta o passe.
- Bloqueado descanso/vida fora de campo como forma de pular semana de partida.
- Protegido clique duplo em popups de confirmacao para reduzir risco de compra duplicada ou saldo inconsistente.
- Mantida a fila de popups existente para evitar sobreposicao de eventos na virada da semana.
