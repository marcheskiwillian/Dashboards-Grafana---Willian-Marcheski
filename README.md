Sobre este projeto

Sempre acreditei que conhecimento deve ser compartilhado.

Ao longo do tempo, desenvolvi diversos dashboards no Grafana para monitoramento de redes, infraestrutura, equipamentos, links e ambientes de NOC. Muitos deles foram criados para resolver necessidades reais do dia a dia e acabaram se tornando ferramentas importantes para facilitar análises e acompanhar informações de forma mais clara.

Por isso, decidi disponibilizar alguns desses dashboards gratuitamente para a comunidade.

A ideia é ajudar quem está começando, quem deseja aprender mais sobre Grafana e Zabbix ou quem procura referências para criar e adaptar seus próprios projetos.

Os dashboards podem ser utilizados para estudo e ajustados conforme a necessidade de cada ambiente. Como foram desenvolvidos em estruturas específicas, algumas configurações, consultas, fontes de dados e variáveis provavelmente precisarão ser alteradas.

Espero que este conteúdo ajude outros profissionais e também incentive mais pessoas a compartilharem conhecimento com a comunidade.


## Plugins utilizados

Os dashboards disponibilizados neste repositório foram desenvolvidos utilizando, em sua maioria, dois plugins adicionais para o Grafana:

### HTML Graphics

O HTML Graphics permite criar painéis personalizados utilizando HTML, CSS, SVG e JavaScript, possibilitando a construção de interfaces e visualizações mais avançadas.

Documentação e instalação:

https://gapit-htmlgraphics-panel.gapit.io/docs/installation/

Página no catálogo do Grafana:

https://grafana.com/grafana/plugins/gapit-htmlgraphics-panel/

Instalação pelo terminal:

```bash
grafana-cli plugins install gapit-htmlgraphics-panel
