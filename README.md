# Europa 26 — QG da viagem

Aplicativo estático responsivo em português: agenda por dia, clima Open-Meteo, mala por viajante, fotos de peças, looks vinculados a datas, checklist de documentos, endereços com mapas, backup JSON e exportação ICS.

## Abrir online

No GitHub, abra **Settings → Pages → Deploy from a branch → main → /(root) → Save**. O endereço público será informado pelo próprio GitHub. Não é necessário instalar dependências. A publicação não foi habilitada pelo aplicativo.

No Safari do iPhone, use Compartilhar → Adicionar à Tela de Início. O cache offline é preparado após a primeira visita em HTTPS. As fontes externas podem ser substituídas pelas fontes do aparelho quando offline.

## Importar a viagem confirmada

No rodapé do aplicativo, escolha **Importar contexto da viagem** e selecione o arquivo `CONTEXTO-BASE — EUROPA-2026.txt` fornecido no planejamento. A importação lê o arquivo localmente e cadastra viajantes, partidas e chegadas, corrida, hospedagens e horários de check-in e checkout. Não envia o arquivo para nenhum servidor. Confirme os participantes da corrida após a importação.

Os checkouts são horários limites, não horários sugeridos de saída. Cadastre deslocamentos e antecedências conforme o voo. Eventos de chegada são separados das partidas para respeitar mudanças de data e de fuso.

Planilhas XLSX do roteiro mestre, listas de mala e versões HTML anteriores não são importadas automaticamente nesta versão. Acrescente essas informações pela interface. Nenhum passeio ou previsão foi inventado.

## Uso

- **Hoje:** dia selecionado, cidade, clima, agenda, pendências e look.
- **Agenda:** criar e editar eventos com horário local, status, endereço e observações. Sinaliza sobreposições no mesmo dia.
- **Mala e looks:** adicionar peças, fotos, quantidades, preparação, limpeza e bagagem; montar combinações para cada dia. Peças ausentes da mala ou para lavar aparecem nos looks.
- **Documentos:** checklist por viajante. É revisão de preparação, não validação jurídica de entrada.
- **Guia rápido:** endereços, copiar e abrir mapas.
- **Backup:** exporta todos os dados e fotos em JSON. Importar substitui o estado atual após confirmação. Faça backup antes de importar.
- **Exportar agenda:** arquivo ICS com fusos de cada cidade para importar no calendário.

## Dados e privacidade

O repositório é público e contém apenas o aplicativo, cidades e a estrutura de datas. Não contém nomes completos, reservas, endereços privados, documentos ou fotos. Os dados cadastrados ficam em IndexedDB no navegador. Não há login, backend ou sincronização automática entre aparelhos. Exportações contêm seus dados pessoais: guarde-as em local privado. O navegador pode apagar dados locais; mantenha backups.

O clima consulta Open-Meteo com coordenadas públicas da cidade, sem enviar os dados da viagem. Mostra mínimas, máximas, probabilidade de chuva e vento, com data da consulta. Não há previsão quando a data está fora da janela recebida. Atualizações falhas preservam o último resultado. Não há acompanhamento de voo ao vivo, notificações externas, provador virtual ou reconhecimento de peças por IA.

## Desenvolvimento

Sirva a pasta raiz com qualquer servidor HTTP estático. JavaScript sem dependências ou compilação. PWA exige HTTPS ou localhost. Verificação de sintaxe: `node --check app.js` e `node --check sw.js`.

Validação realizada: sintaxe, abertura no navegador, cadastro de atividade e persistência ao recarregar. Upload, calendário em aplicativos externos, modo offline no Safari e instalação no iPhone precisam de validação nos dispositivos de destino.

## Edição temática

Madri: terracota, dourado e arcos. Porto: azul, padrões de azulejos e ponte sobre o rio. Berlim: concreto, verde ácido e tipografia geométrica. Ilustrações vetoriais autorais estilizadas. O tema acompanha a cidade da data selecionada; os botões no topo permitem experimentar cada cidade. Volte a Pelo roteiro para restaurar a troca automática. Dados e backups da versão anterior continuam compatíveis no mesmo endereço.
