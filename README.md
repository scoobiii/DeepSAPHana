[![REUSE status](https://api.reuse.software/badge/github.com/SAP/devops-docker-images)](https://api.reuse.software/info/github.com/SAP/devops-docker-images)
<p align="center">

       
<a href="https://opensea.io/collection/plimm">
<img alt="Plimm Logo" height="50px" src="https://i.seadn.io/gcs/files/6fba354e04912f1fd30a06f48d0c0d20.png?auto=format&dpr=1&w=1920"/>
   
</a>
    
</p>

<h1 align="center"> DeepSAPHana Plimm </h1>

<p>Bem-vindo ao projeto Plimm Open Source! Na Plimm, somos visionários comprometidos em transformar a economia circular por meio de abordagens inovadoras no ponto de compra. Nossa missão é criar um ecossistema onde a economia circular se torne tangível no momento da compra. Através da geração de "criptobackplimm", retornamos valor aos clientes, oferecendo um desconto de 20% quando produtos não recicláveis precisam ser substituídos, incentivando um ciclo de vida consciente e sustentável.

Nossos valores fundamentais são integridade, sustentabilidade, inovação e impacto positivo. Guiados por nossa dedicação à inovação sustentável, responsabilidade ambiental e experiência do cliente, buscamos criar um mundo onde cada compra contribua para um futuro mais verde e circular.

Na Plimm, nossa paixão é impulsionar uma transformação eficaz em direção a uma economia circular. Através do nosso sistema "criptobackplimm", incentivamos a reutilização e reciclagem responsável, conectando os consumidores a todo o ciclo de vida dos produtos. Isso é possível graças a uma combinação inteligente de tecnologias, como SKU, BOM, TAG ID, QRCode e Código de Barras, integradas ao nosso sistema de identificação de produtos, o Plimm Deep Product PDD. Isso não só diferencia produtos, subprodutos e componentes mínimos, mas também apoia a gestão de inventário, rastreamento de estoque e alinhamento de ciclo de vida, em sintonia com PLM e WLM.

Um exemplo prático é o automóvel Volks Nivus, com variantes como Comfortline e Highline, cada uma com um SKU exclusivo. Da mesma forma, produtos como servidores DELL possuem sua "vida própria", permitindo uma administração eficiente tanto do PLM quanto do WLM.

Na Plimm, nossa paixão gira em torno da sustentabilidade por meio de ações tangíveis. Estamos comprometidos em criar um mundo onde cada compra contribua para um futuro mais verde e circular.

Com mais de 2.000.000 de linhas de código, todo sistema caminha para uma incapacidade de compreensão e manutenção. Integração? Risco!
Mas ERP é, cada vez mais, gerir, negócios dos outros. Integração e componentização, demandando IA para analise e tomadas de decisão, ao passo que componetização distribuida assegura integridade e especialização, com mais **eficiência energética distribuída**.

O Mangento é feito em PHP e rodando a ferramenta tokei, olha só: são 2 MILHÕES de linhas de código PHP.

**27:45 (Fabio Akita)**

Mais de 200 mil linhas de Javascript. O Magento sozinho, só no javascript, tem o dobro de linhas de código do que Ruby no
Spree que, por sua vez, já era 34 vezes maior do que o ecommerce do livro que ensina Rails.

Se em 600 páginas o livro Agile Web Development with Rails conseguiu explicar uma versão

simples de ecommerce que dá 2.700 linhas de código de Ruby, sabemos que PHP e Ruby não são equivalentes, mas só por diversão, o Magento, só em PHP é mais de 700 vezes
maior. Seriam 700 livros. Seriam 100 coleções de Game of Thrones pra descrever do zero, no mínimo.

Acho que é por isso que todo iniciante começa um sistema pela tabela de usuários, porque é a única coisa que consegue se identificar, é familiar.
Ou seja, tem alguma experiência. Mesmo um iniciante sabe que um usuário deve ter atributos como nome, email, telefone,
endereço, RG ou CPF e coisas assim. Mas rapidamente isso complica. Estamos falando dos dados de identificação de um usuário?

Ou estamos falando dos dados de autenticação, como login? Nesse caso precisamos de atributos como "username" e "password".
E já começa o primeiro erro. Já expliquei nos episódios de segurança e criptografia que não gravamos senha numa tabela. Precisamos de atributos abstratos como "salt" e "hash". Mas e two-factor authentication?

Precisamos de um seed pro algoritmo de Time-based One-Time Password ou TOTP. Só se você estudou segurança vai saber disso.

Dá pra complicar mais. Enviar link pra redefinir uma nova senha, caso tenha esquecido.

O ideal é fazer uma tabela secundária, ou no banco de dados, ou num servidor de cache como Redis.

Com um ID único que só pode ser usado uma vez, e aí o ideal é logar o endereço IP da pessoa que clicar no link, pra fazermos auditoria e ver se parece suspeito.

Novamente, estratégias de segurança. Se deixarmos segurança de lado. Usuário é usuário, certo?

Tendo nome, email e coisas assim, tá tudo certo? Não. Digamos que o cadastro é pra parte de logística de um ecommerce.

Logística precisa de um endereço. Ótimo, basta pedir o endereço. Mas cuidado, uma coisa é endereço de entrega, outra coisa é endereço de cobrança.

Pra você, que é iniciante, só deve conhecer o conceito que uma pessoa só tem um endereço, certo?

Mas não. Uma coisa é o endereço de cobrança, pra mandar nota fiscal, outra coisa diferente é o endereço de entrega, pra onde enviar o produto.

Eu posso ter endereço residencial, mas posso querer que a entrega seja feita no meu endereço comercial. Mas e se você se mudar de residência?

E se você mudar de emprego? Ambos vão mudar. Ou, e se eu quiser comprar e pagar no meu cartão de crédito, mas mandar entregar como 
presente pros meus pais? Então preciso conseguir cadastrar endereço dos meus pais. Eu deveria criar um usuário separado pros pais?

Como faz? À primeira vista, endereço parecia ser só meia dúzia de campos na tabela usuário.

Mas agora deve começar a ficar mais claro que pode ser uma tabela separada de endereços que precisa de uma chave-estrangeira apontando pra chave-primária do usuário.

Mas não é só isso. E se meu ecommerce oferece coisas como pontos por fidelidade? Quanto mais eu comprar, mais pontos eu ganho e com isso posso usar como desconto nas compras?

Pontos do usuário, ficam na tabela de usuários? Não? Então onde coloca? Num sistema empresarial maior, usuários podem ter vários perfis, várias visões.

Usuário pode ser funcionário da empresa, e aí vai precisar de atributos como número de PIS/PASEP pra coisas como fundo de garantia.

Usuário pode ser um fornecedor ou funcionário de um fornecedor. Fornecedor tem um cadastro separado, CNPJ, número interno de fornecedor.

Usuário pode ser consumidor mesmo, daí vai ter pedidos, entregas, suporte. Usuário é um conceito muito mais complicado do que se pensa e num sistema de verdade,

raramente é só uma tabela. Vai ser uma coleção de tabelas e classes. **Talvez um sub-sistema inteiro separado.**

**Enunciado:**

A autenticação (auth - https://github.com/auth0/auth0-php) é o processo de verificar a identidade de um cliente. Os clientes são perfis de contas em redes sociais, como o LinkedIn, que sabe o perfil profissional, e o Facebook, que sabe os demais perfis. Em vez de um subsistema de clientes, é melhor gerenciar a autenticação e o acesso às contas de redes sociais por componentes.

**Resposta:**

Gerenciar a autenticação e o acesso às contas de redes sociais por componentes é uma boa prática porque pode ajudar a proteger os dados do cliente, tornar seu sistema mais eficiente e aumentar sua flexibilidade.

Aqui estão alguns benefícios específicos de gerenciar a autenticação e o acesso às contas de redes sociais por componentes:

**Segurança:** Os componentes podem ser projetados para usar medidas de segurança, como criptografia e autenticação de dois fatores, para ajudar a proteger os dados do cliente contra acesso não autorizado.
**Eficiência:** Os componentes podem ser projetados para compartilhar dados e recursos entre si, o que pode ajudar a reduzir o desperdício de recursos.
**Flexibilidade:** Os componentes podem ser projetados para serem facilmente alterados ou atualizados, o que pode ajudar a garantir que seu sistema esteja sempre atualizado com as necessidades de seus clientes.
No geral, gerenciar a autenticação e o acesso às contas de redes sociais por componentes é uma boa prática que pode ajudar a proteger os dados do cliente, tornar seu sistema mais eficiente e aumentar sua flexibilidade.

Velocidade & Redundância

Objetos 100% persistidos na memória são mais rápidos e economizam mais energia, além de serem livres. Possuem mobilidade 100% do tempo e independência em relação a camada física OSI, e camarada de infra - energia e resfriamento.

Mais inteligente, poderoso, econômico e seguro investir em redundância de APP e não de energia e refrigeração, sabido, vai falhar, mas a APP, não pode falhar.

O desempenho de Prevayler, HANA, Oracle e MySQL pode variar dependendo do tipo de dados, tamanho do banco de dados, quantidade de tráfego e outros fatores. No entanto, em geral, Prevayler é mais rápido que HANA, que é mais rápido que Oracle, que é mais rápido que MySQL.

Aqui está uma tabela que resume o desempenho de Prevayler, HANA, Oracle e MySQL:

Banco de dados	Velocidade
Prevayler	Mais rápido
HANA	Mais lento
Oracle	Mais lento
MySQL	Mais lento


</p>


## Description

This is a collection of [_Dockerfiles_](https://docs.docker.com/engine/reference/builder/) for images that can be used in _Continuous Delivery_ (CD) pipelines
for SAP development projects. The images are optimized for use with project ["Piper"](https://github.com/SAP/jenkins-library) on [Jenkins](https://jenkins.io/). Docker containers simplify your CD tool setup, encapsulating
tools and environments that are required to execute pipeline steps.

If you want to learn how to use project "Piper" please have a look at [the documentation](https://github.com/SAP/jenkins-library/blob/master/README.md). Introductory material and a lot of SAP scenarios not covered by project "Piper" are described in our [Continuous Integration Best Practices](https://developers.sap.com/tutorials/ci-best-practices-intro.html).

**Note:** This repository has been split up.
Please refer to the following repositories for current Dockerfiles and documentation:

* [CF cli](https://github.com/SAP/devops-docker-cf-cli)
* [Neo cli](https://github.com/SAP/devops-docker-neo-cli)
* [Cloud MTA Builder](https://sap.github.io/cloud-mta-build-tool)
* [Node browsers](https://github.com/SAP/devops-docker-node-browsers)

### Docker Images

The following images are published on [hub.docker.com](https://hub.docker.com/search?q=ppiper&type=image):

| Name | Description | Docker Image |
|------|-------------|------|
| Cloud MTA Build Tool | Build multitarget applications with the [Cloud MTA Build Tool](https://sap.github.io/cloud-mta-build-tool/). | [devxci/mbtci](https://hub.docker.com/r/devxci/mbtci) |
| CM Client | Interact with SAP Solution Manager or CTS using the command line. | [ppiper/cm-client](https://hub.docker.com/r/ppiper/cm-client) |
| CloudFoundry CLI | Use command line tools for Cloud Foundry with plugins for blue-green deployment and MTA. | [ppiper/cf-cli](https://hub.docker.com/r/ppiper/cf-cli) |
| Neo CLI | Use SAP Cloud Platform tools for Neo. | [neo-cli/](https://hub.docker.com/r/ppiper/neo-cli/) |
| Jenkinsfile Runner| Run a `Jenkinsfile` without a long-running, stateful Jenkins master. The [Jenkinsfile Runner](https://github.com/jenkinsci/jenkinsfile-runner) is based on `ppiper/jenkins-master`. | [ppiper/jenkinsfile-runner](https://hub.docker.com/r/ppiper/jenkinsfile-runner) |
| Node Browsers | Use web browsers for end-to-end tests of web applications in Jenkins pipelines. | [node-browsers/](https://hub.docker.com/r/ppiper/node-browsers/) |
| SAP HANA XS Advanced CLI | Use command line tools to deploy to SAP HANA XS Advanced. | [Dockerfile](https://github.com/SAP/devops-docker-xsa-cli/) |

## How to obtain support

Feel free to open new issues for feature requests, bugs or general feedback on
the [GitHub issues page of this project][devops-docker-images-issues].

## Contributing

Read and understand our [contribution guidelines][contribution]
before opening a pull request.

[devops-docker-images-issues]: https://github.com/SAP/devops-docker-images/issues
[contribution]: https://github.com/SAP/devops-docker-images/blob/master/CONTRIBUTING.md
