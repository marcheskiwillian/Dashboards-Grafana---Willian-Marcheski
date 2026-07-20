<div align="center">

# Dashboards Grafana — Willian Marcheski

Dashboards gratuitos para monitoramento de redes, equipamentos, links, BGP e infraestrutura de provedores.

![Grafana](https://img.shields.io/badge/Grafana-Dashboards-F46800?logo=grafana&logoColor=white)
![Zabbix](https://img.shields.io/badge/Zabbix-Monitoramento-D40000?logo=zabbix&logoColor=white)
![Community](https://img.shields.io/badge/Comunidade-Gratuito-2ea44f)
![Status](https://img.shields.io/badge/Status-Em%20evolução-1688f0)

</div>

---

## Sobre este projeto

Sempre acreditei que conhecimento deve ser compartilhado.

Ao longo do tempo, desenvolvi diversos dashboards no Grafana para monitoramento de redes, infraestrutura, equipamentos, links e ambientes de NOC. Muitos deles nasceram de necessidades reais do dia a dia e se tornaram ferramentas importantes para facilitar análises, identificar falhas e acompanhar o ambiente de forma mais clara.

Por isso, decidi disponibilizar gratuitamente alguns desses dashboards para a comunidade.

A ideia é ajudar quem está começando, quem deseja aprender mais sobre Grafana e Zabbix ou quem procura referências para criar e adaptar seus próprios projetos.

Os dashboards podem ser utilizados para estudo e adaptados conforme a necessidade de cada ambiente. Como foram desenvolvidos em estruturas específicas, algumas fontes de dados, consultas, variáveis, grupos, hosts e itens do Zabbix precisarão ser ajustados.

Espero que este conteúdo ajude outros profissionais e também incentive mais pessoas a compartilharem conhecimento com a comunidade.

---

## Dashboards disponíveis

### Monitoramento de equipamentos Ciena

Dashboard desenvolvido para monitoramento de equipamentos Ciena, reunindo informações como:

- Uptime e disponibilidade;
- Nome e estado do equipamento;
- Q-Factor por canal;
- Potência óptica RX/TX;
- Estado das portas;
- Incidentes;
- Tráfego por interface;
- Interfaces com maior quantidade de erros.

<p align="center">
  <img
    src="./Captura%20de%20tela%202026-07-20%20115137.png"
    alt="Dashboard Grafana para monitoramento de equipamentos Ciena"
    width="100%"
  />
</p>

**Plugins utilizados:** Zabbix, HTML Graphics e Business Charts.

**[Baixar o dashboard Ciena](./Grafana%20Labs%20-%20CIENAS%20-Willian%20Marcheski.json)**

---

### Monitoramento de sessões BGP

Dashboard desenvolvido para acompanhamento detalhado das sessões BGP, incluindo:

- Quantidade total de sessões;
- Sessões estabelecidas;
- Alertas;
- Sessões IPv4 e IPv6;
- Clientes e sistemas autônomos;
- Prefixos recebidos;
- Histórico de quedas;
- Pesquisa e filtros;
- Uptime do equipamento.

<p align="center">
  <img
    src="./Captura%20de%20tela%202026-07-20%20115237.png"
    alt="Dashboard Grafana para monitoramento de sessões BGP"
    width="100%"
  />
</p>

**Plugins utilizados:** Zabbix e HTML Graphics.

**[Baixar o dashboard BGP](./Grafana%20Labs%20-%20BGP%20-Willian%20Marcheski.json)**

---

### Monitoramento de equipamentos Huawei

Dashboard desenvolvido para monitoramento de switches e roteadores Huawei, reunindo:

- Nome e disponibilidade do equipamento;
- Utilização de CPU e memória;
- Tempo de resposta;
- Estado do SNMP;
- Potência óptica RX/TX;
- Temperatura das interfaces;
- Estado das portas;
- Incidentes;
- Tráfego e desempenho das interfaces.

<p align="center">
  <img
    src="./Captura%20de%20tela%202026-07-20%20115515.png"
    alt="Dashboard Grafana para monitoramento de equipamentos Huawei"
    width="100%"
  />
</p>

**Plugins utilizados:** Zabbix, HTML Graphics e Business Charts.

**[Baixar o dashboard Huawei](./Grafana%20Labs%20-%20HUAWEI%20-Willian%20Marcheski.json)**

---

## Requisitos

Antes de importar os dashboards, instale e configure a fonte de dados do Zabbix.

### Zabbix para Grafana

Página oficial:

https://grafana.com/grafana/plugins/alexanderzobnin-zabbix-app/

Instalação:

```bash
grafana-cli plugins install alexanderzobnin-zabbix-app
```

### HTML Graphics

Utilizado na construção das áreas personalizadas em HTML, CSS, SVG e JavaScript.

Documentação:

https://gapit-htmlgraphics-panel.gapit.io/docs/installation/

Página no catálogo do Grafana:

https://grafana.com/grafana/plugins/gapit-htmlgraphics-panel/

Instalação:

```bash
grafana-cli plugins install gapit-htmlgraphics-panel
```

### Business Charts

Os dashboards Ciena e Huawei também possuem painéis criados com o Business Charts, baseado em Apache ECharts.

Página no catálogo do Grafana:

https://grafana.com/grafana/plugins/volkovlabs-echarts-panel/

Repositório:

https://github.com/grafana/business-charts

Instalação:

```bash
grafana-cli plugins install volkovlabs-echarts-panel
```

Depois da instalação dos plugins, reinicie o serviço do Grafana.

Exemplo no Linux:

```bash
sudo systemctl restart grafana-server
```

---

## Como importar

1. Baixe o arquivo JSON do dashboard desejado.
2. Acesse o Grafana.
3. Vá em **Dashboards**.
4. Clique em **New** e depois em **Import**.
5. Envie o arquivo JSON.
6. Escolha a fonte de dados do Zabbix.
7. Clique em **Import**.

---

## Ajustes necessários

Os dashboards não são totalmente plug-and-play, pois cada ambiente possui sua própria estrutura.

Após a importação, poderá ser necessário ajustar:

- Fonte de dados e UID do Zabbix;
- Variável `Hosts`;
- Grupos de hosts;
- Nomes dos equipamentos;
- Nomes e padrões dos itens;
- Interfaces;
- Consultas e expressões regulares;
- Limites e thresholds;
- Versões dos plugins;
- Compatibilidade com a versão do Grafana.

Os arquivos foram disponibilizados principalmente para estudo, referência e adaptação.

---

## Problemas após a importação

### Painel aparece como “Plugin not found”

Instale o plugin indicado na seção **Requisitos** e reinicie o Grafana.

### Painel aparece sem dados

Confira:

1. Se a fonte de dados do Zabbix foi selecionada;
2. Se a variável de host encontrou equipamentos;
3. Se os nomes dos itens existem no seu Zabbix;
4. Se os padrões e expressões regulares correspondem ao seu ambiente;
5. Se o usuário da API do Zabbix possui as permissões necessárias.

### Dashboard importou, mas algumas áreas ficaram vazias

Verifique principalmente a instalação do **HTML Graphics** e do **Business Charts**.

---

## Comunidade

Novos dashboards, atualizações e conteúdos serão compartilhados no grupo do Telegram:

**[Entrar no grupo do Telegram](COLOQUE_AQUI_O_LINK_DO_TELEGRAM)**

---

## Contribuições

Sugestões, correções e melhorias são bem-vindas.

Você pode:

- Abrir uma **Issue**;
- Enviar um **Pull Request**;
- Compartilhar como o dashboard ficou no seu ambiente;
- Sugerir novos equipamentos e indicadores.

---

## Créditos

Desenvolvido e compartilhado por **Willian Marcheski**.

GitHub: [@marcheskiwillian](https://github.com/marcheskiwillian)

Se este projeto ajudar você, considere deixar uma ⭐ no repositorio.
