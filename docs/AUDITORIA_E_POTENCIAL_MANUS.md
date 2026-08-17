# Leitura estratégica — rede-artistas-bahia-2025

**Data:** 17 de agosto de 2026  |  **Repositório:** [rede-artistas-bahia-2025](https://github.com/viniburilux/rede-artistas-bahia-2025)  |  **Autor:** Manus AI

> Este documento é uma auditoria de inventário e potencial. Ele não altera o código existente e não afirma que funcionalidades foram executadas ou validadas quando isso não aparece na evidência observada.

## Síntese executiva

Repositório mínimo contendo uma página estática (index.html) com estilos e estruturas para uma visualização interativa de rede chamada "Rede de Contratações Artísticas — Bahia 2025". É um protótipo front-end sem documentação, dados nem infraestrutura de apoio observáveis no dossiê.

## Domínio e propósito aparente

Visualização de rede social/contratações artísticas no estado da Bahia (contexto: 2025). Domínio: visualização de dados culturais / mapeamento de artistas e municípios.

## Indicadores do snapshot

| Indicador | Valor |
|---|---:|
| Arquivos contabilizados | 1 |
| Tamanho no snapshot | 33203 bytes |
| Último commit observado | 2ad7237feaafb90e90004d773f370d32e07d8d0b	2026-04-24T01:15:59-04:00	Initial commit |
| Prioridade sugerida | média |

## Evidências observadas

- Repositório contém exatamente 1 arquivo: index.html (33.203 bytes).
- metadata do GitHub: descrição 'Visualização da Rede de Contratações Artísticas — Bahia 2025', criado em 2026-04-24, branch default 'master', último commit 'Initial commit'.
- index.html referenciar bibliotecas externas: <script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.8.5/d3.min.js"></script> e Google Fonts (Space Grotesk, JetBrains Mono).
- index.html contém CSS com classes e estilos detalhados para elementos de gráfico (p.ex. .node-artista, .node-municipio, .link, .label-artista, #tooltip, #legend, #controls, #filter-bar).
- Existência de elementos de UI textuais no CSS e no início do body: header com título 'Rede de Contratações Artísticas — Bahia 2025', estatísticas, legenda, tooltip e controles.
- Não há outros arquivos no repositório (sem README, sem dados, sem scripts de servidor, sem package.json, sem CI/CD, sem licença aparente).

## Ativos e capacidades

- evidência: página estática index.html com estilos CSS prontos para visualização de grafo e UI (header, legend, tooltip, controles, filtro).
- evidência: uso de D3.js via CDN indica intenção de renderizar visualização dinâmica no cliente (mas o código JS de renderização não está visível no trecho do dossiê).
- inferência: a presença de classes .node-artista, .node-municipio e .link sugere que a visualização deve distinguir nós por tipo (artista vs município) e suportar interações como hover, destaque de arestas e tooltips.
- inferência: controles, filtros e estatísticas no layout indicam funcionalidades interativas (zoom / reset / filtros por categoria) — requerem JS não listado no dossiê.
- evidência: uso de fontes externas e efeitos visuais (glow, drop-shadow) preparados para uma apresentação visual sofisticada no front-end.
- observável/ausente: não há dados embarcados listados no dossiê (CSV/JSON) nem endpoints para consumo dinâmico; portanto a capacidade de renderizar uma rede a partir de dados reais não está confirmada.
- observável/ausente: não há artefatos de build, testes ou deploy automatizado no repositório fornecido.

## Maturidade observável

Protótipo visual / artefato de demonstração. O repositório contém apenas uma página estática com estilos e indicações de interação; não há evidência de dados, testes, documentação, licenciamento ou pipeline de deploy. Não está pronto para produção e não há sinais de uso ou validação. Maturidade técnica observável: baixa (prova de conceito visual).

## Potencial de aproveitamento

- Integração visual com o ecossistema LuxVerso/GhostWorks como componente front-end para exibição de redes artísticas — potencial alto desde que completado com backend/dados.
- Fonte de UI/UX estilística reaproveitável para dashboards culturais e apresentações de rede (legendas, tooltips, controles).
- Conector para pipelines de dados: se for formalizado formato de entrada (nodes/edges JSON/CSV) pode ser acoplado a APIs ou infra de dados do GhostWorks para visualização em tempo real ou periódica.
- Suporte a análises de IA/dados: a visualização pode ser utilizada para expor resultados de modelos (p.ex. detecção de comunidades, centralidade) quando enriquecida com atributos e metadados.
- Material útil para prototipagem rápida em projetos de mapeamento cultural com stakeholders locais (secretarias, fundações, coletivos).

## Riscos e lacunas

- Ausência de dados: não foram encontrados arquivos de dados (JSON/CSV) ou referências a fontes, portanto não é possível reproduzir a visualização com dados reais a partir do repositório.
- Falta de documentação: sem README, sem instruções de instalação/uso, sem especificação do formato dos dados nem do contrato da API.
- Governança de dados não tratada: não há indicações sobre proveniência, consentimento, anonimização ou classificação de informações sensíveis/PII.
- Segurança: uso de bibliotecas via CDN sem Subresource Integrity (SRI) e sem políticas de Content Security Policy observadas; não há revisão de dependências nem políticas de segurança.
- Reprodutibilidade e automação ausentes: não há scripts de build, package manager, testes automatizados, nem CI/CD configurado.
- Licenciamento e governança de código ausentes: nenhum arquivo LICENSE detectado — restrição para reuso legal incerta.
- Acessibilidade e usabilidade: apesar do design visual, não há evidência de considerações de acessibilidade (ARIA, leitura por leitores de tela, contraste além do visual).
- Escalabilidade limitada: estrutura atual é puramente client-side; sem backend ou paginação, visualizações grandes podem sofrer em performance sem processamento/servidor.

## Próximos passos recomendados

- Adicionar README detalhado explicando objetivo da visualização, formato esperado dos dados (ex.: nodes/edges JSON schema), instruções locais para executar o arquivo (abrir index.html ou servir via HTTP) e captura de tela/demo.
- Incluir um ou mais exemplos de dataset (JSON/CSV minimal) com schema documentado para permitir reprodução imediata da visualização.
- Separar dados da view: alterar index.html para buscar dados externos (ex.: data/nodes.json, data/edges.json) e documentar o contrato — facilita integração com pipelines do GhostWorks/LuxVerso.
- Adicionar LICENSE apropriada ao repositório para clareza de reuso (p.ex. MIT ou outra compatível com políticas da organização).
- Adicionar validação de esquema: fornecer JSON Schema para nodes/edges e incluir código de validação (no cliente ou preferencialmente em pipeline backend) para garantir qualidade dos dados antes da renderização.
- Implementar controles de segurança: pinagem de versões, Subresource Integrity (SRI) para scripts externos ou migrar dependências para pacote gerenciado (npm/PNPM) e bundle via build (esbuild/webpack).
- Criar um pequeno backend ou mock API (por exemplo um endpoint /api/graph) para demonstrar integração com pipelines de dados e facilitar atualização dinâmica dos dados; documentar endpoints e formatos.
- Adicionar um arquivo de governança de dados mínimo cobrindo proveniência, anonymização/mascaramento de PII, consentimento e política de retenção para quaisquer dados pessoais usados.
- Incluir testes básicos e CI: scripts que validem o formato dos dados de entrada, lint do HTML/CSS/JS, e um workflow de GitHub Actions para build/preview (páginas GitHub Pages ou deploy estático).
- Adicionar mecanismos de exportação/impressão (exportar SVG/PNG, exportar subset de dados) e métricas de uso (instrumentação minimal para medir volume de visualizações / tamanho do grafo).
- Melhorar acessibilidade: adicionar atributos ARIA a controles interativos, garantir navegação por teclado e fornecer alternativa textual para a visualização.
- Criar roadmap de integração com LuxVerso/GhostWorks: definir API de ingestão de dados (formatos, autenticação), pontos de extensão para ML (campos para scores de centralidade, comunidade), e forma de embutir o componente em portais existentes.
- Realizar revisão de performance para grafos grandes: considerar processamento server-side (agregação, amostragem), usar WebGL (p.ex. via regl/fireworks libs) ou técnicas de level-of-detail antes de suportar grandes volumes.

## Método e limites

A leitura foi feita sobre um snapshot de profundidade 1 e sobre arquivos textuais selecionados por relevância estrutural, incluindo README, manifests e amostras de código. Dependências, notebooks, binários, dados grandes e integrações externas podem exigir uma rodada posterior de execução controlada. Nenhum código do repositório foi executado durante a auditoria.

**Fonte primária:** [rede-artistas-bahia-2025](https://github.com/viniburilux/rede-artistas-bahia-2025)
