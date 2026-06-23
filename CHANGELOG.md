# Changelog

Convencao de versao: `x.yz`

- `x`: grandes atualizacoes/fases estruturais.
- `y`: pequenas mecanicas adicionadas, removidas ou alteradas.
- `z`: bug fixes, balanceamento pontual e correcoes de integridade.

## 3.51 - Auditoria de Fluxos da Etapa 17

- Calendario, agenda, selecao e mercado foram ligados ao shell lateral e ao sistema de saves.
- Mantido adaptador `passarSemana()` para eventos antigos, agora avançando um dia sem duplicar pagamentos semanais.
- Saves da versao 11 migram para datas reais preservando rodada, resultados e tabela.

## 3.50 - Datas FIFA e Amistosos

- Datas FIFA entram no calendario regional e podem gerar convocacao por OVR, fama, idade e nacionalidade.
- Convocados desbloqueiam a aba Selecao, grupo procedural e amistoso internacional agendado.
- Jogos internacionais nao alteram a tabela do clube e concedem bonus proprio de fama.

## 3.40 - Energia, Lesoes e Intervalo

- Escalacao usa faixas graduais de energia; atletas abaixo de 30 raramente iniciam.
- Risco de lesao em partida agora varia de 2% a 70% conforme a energia.
- Intervalo recupera 15 pontos para quem esta em campo e 20 para o banco, com trocas de titulares cansados.

## 3.30 - Sondagens e Metricas Avancadas

- Pedidos ao agente levam tres dias e dependem de OVR, fama, idade, agente, xG e xA recentes.
- Sondagens oferecem objetivos facil, medio e dificil, individuais ou combinados.
- Acordos fora da janela aguardam a abertura; passes livres podem negociar imediatamente.

## 3.20 - Agenda Pessoal

- Dias livres aceitam viagem, festa, familia e fisioterapia com custos e efeitos proprios.
- Compromissos nao podem ocupar dias de partida e sao processados no avanço diario.

## 3.10 - Calendario Interativo

- Nova aba mensal mostra partidas, janelas, Datas FIFA, feriados e compromissos pessoais.
- Dias de jogo abrem previa com mando, OVR, forma, baixas e probabilidades.

## 3.00 - Motor Diario e Calendarios Regionais

- O tempo passa por dias reais, encerrando a sequencia artificial de uma partida por passo.
- Brasil usa temporada anual; ligas europeias usam ciclo julho-junho.
- Salarios, custos, patrocinios, cursos e limites semanais continuam processados uma vez por semana.

## 2.31 - Etapa 16.3: Fechamento do Mercado

- Corrigida a sidebar retraida que mantinha uma hitbox invisivel sobre o conteudo e bloqueava cliques no Mercado.
- Calendarios agora reconhecem nomes de clubes com ou sem acentos e saves sem partidas sao reparados ao carregar.
- Transferencias expiram sondagens antigas, regeneram tabela/calendario e limpam o adversario visual anterior.
- Modal de negociacao ganhou rolagem propria em ecras mobile menores e o texto da janela foi corrigido.
- Gestão de plantel atualiza o Mercado imediatamente, nao oferece compras com elenco cheio e gera nomes coerentes para candidatos.
- Passe livre remove partidas futuras do ex-clube; aposentadoria inicia a carreira de treinador num clube real da liga de acesso.
- Demissao e troca de emprego do treinador agora regeneram o calendario do novo clube.

## 2.30 - Etapa 16.2: Negociacao de Contratos v2

- Propostas agora incluem luvas de assinatura e paciencia maxima do clube.
- Modal de negociacao ganhou ajustes diretos de salario, luvas, duracao e clausula.
- Contrapropostas agora calculam exigencia, risco, chance aproximada e consumo de paciencia.
- Clubes podem aceitar, contraofertar ou encerrar a negociacao conforme a dureza do pedido.
- Ao assinar, luvas entram no saldo e a comissao do agente sai na assinatura, evitando bloqueios injustos quando as luvas cobrem a comissao.

## 2.21 - Hotfix de Atualizacao da Sidebar

- Energia, moral, fama e dinheiro da sidebar agora atualizam imediatamente quando `updateTopBar()` roda.
- Eventos que usam apenas `updateEnergiaBar()` tambem atualizam a energia compacta da sidebar.
- `updateEnergiaBar()` ficou protegido para chamadas fora de telas que tenham barra visual de energia.

## 2.20 - Etapa 16.1: Mercado Central

- A tela `Mercado` ganhou subabas separadas para jogador e treinador.
- Jogador agora navega por `Contrato`, `Sondagens` e `Agente` sem a tela antiga empilhada.
- Treinador ganhou abas `Plantel`, `Busca` e `Empregos`, com resumo de orcamento, janela, movimentos e diretoria.
- A busca de jogadores do treinador agora aparece como lista pesquisavel na tela, reaproveitando limite de janela e orcamento existentes.
- Adicionadas vagas de emprego procedurais para treinadores, com requisito de reputacao, salario, duracao e chance de candidatura.

## 2.11 - Hotfix de Tooltips da Sidebar

- Tooltips da barra lateral retraida agora usam caixa flutuante fora do drawer, evitando corte pelo `overflow`.
- Status compactos funcionam com hover, foco e toque, mostrando nome e valor atual.
- Removida a bolinha amarela de clima/hora do topo da barra retraida.

## 2.10 - Etapa 16.0: Shell Lateral Mobile

- Adicionado shell lateral recolhivel dentro da largura mobile, sem expandir o tamanho do jogo.
- Barra fechada mostra status compactos por letras, com tooltip no hover.
- Barra aberta mostra personagem, fundo da moradia, status, menu e atalhos de save/simulacao.
- Navegacao foi renomeada para preparar a nova arquitetura: `Casa` virou `Painel` e `Agente` virou `Mercado`.
- A tela de criacao continua fora do shell para nao ficar deslocada em desktop.

## 2.03 - Preview da Sidebar de Moradia

- Avatares do topo e do perfil agora usam um `character-stage` reutilizavel para a futura sidebar.
- O fundo do palco do personagem passa a usar a moradia atual do jogador/treinador.
- Variantes de imagem da moradia sao escolhidas de forma estavel por save para evitar flicker.
- Mantido placeholder esportivo no personagem, preparando o espaco para o paper-doll da Etapa 18.

## 2.02 - Hotfix de Calendario e Liga de Acesso

- Criada a liga `Brasileirao Acesso` para carreiras iniciais em clubes brasileiros pequenos.
- Clubes pequenos agora usam apenas times brasileiros de acesso, removendo Lugo, Huesca, Barnsley, Burton Albion e Sandhausen desse fluxo.
- Saves antigos em clubes de acesso migram para a nova liga e regeneram calendarios contaminados.
- Calendario e registro de resultados normalizam clubes de base, como `Figueirense (Base)`, para o clube competitivo correto.

## 2.01 - Hotfix de Integridade da Liga

- Tabelas de liga agora saneiam saves/states antigos e removem clubes fora da competicao correta.
- Registro de resultados passou a rejeitar partidas com clubes que nao pertencem ao state da liga.
- Configuracao de simulacao global agora destaca visualmente o modo ativo e as ligas selecionadas.
- Resumo pos-jogo diferencia energia ao apito final da recuperacao aplicada ao voltar para a Home.

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
