# 📘 Miniguia de Estudos com NotebookLM: Princípios da Arquitetura REST

---

## 🎯 Contexto e Objetivo

Este guia foi desenvolvido como parte de um desafio prático com o objetivo de explorar o uso da Inteligência Artificial como ferramenta de aprendizagem ativa.

O tema escolhido foi **"Princípios da Arquitetura REST e sua Aplicação em APIs Web"**, com o objetivo de:
 - Compreender os conceitos e princípios fundamentais do REST;
 - Explorar aplicações práticas;
 - Consolidar o conhecimento por meio de resumos e experimentação com IA.

---

## 📚 Curadoria de Fontes

As seguintes fontes foram selecionadas considerando sua relevância técnica e confiabilidade:
 1. [Estilos arquitetônicos e o projeto de arquiteturas de software baseadas em rede - Dissertação de Roy Thomas Fielding](https://roy.gbiv.com/pubs/dissertation/top.htm)
 2. [O que é uma API REST (API RESTful)? | IBM](https://www.ibm.com/think/topics/rest-apis)
 3. [O que é a API RESTful? – Explicação sobre a API RESTful – AWS](https://aws.amazon.com/pt/what-is/restful-api/)
 4. [Práticas recomendadas de design de API Web - Azure Architecture Center | Microsoft Learn](https://learn.microsoft.com/pt-br/azure/architecture/best-practices/api-design)

### Critérios de escolha
 - Autoridade (criador do REST);
 - Documentação oficial;
 - Aplicação prática no mercado;
 - Clareza conceitual.

Todas as fontes foram inseridas no NotebookLM para análise e geração de respostas contextualizadas.

---

## 🤖 Engenharia de Prompts e Testes

### Primeiro prompt

> ##
>Explique os conceitos fundamentais de uma API, incluindo o que são endpoints, recursos e representações. Em seguida, descreva como esses conceitos se relacionam com a arquitetura REST e com o protocolo HTTP. Organize a resposta em tópicos e inclua exemplos práticos.
> ##

#### Resposta resumida
Uma API (Interface de Programação de Aplicações) funciona como intermediária  entre clientes e recursos na Web, definindo as regras para que diferentes sistemas de software se comuniquem programaticamente.

##### Conceitos Fundamentais de uma API

| Elemento       | Descrição                          |
|----------------|----------------------------------|
| Recursos       | São a unidade básica de dados em uma API e representam qualquer informação que possa ser nomeada, como uma imagem, um vídeo, uma pessoa ou um pedido de compra.  |
| Endpoints      | São os endereços (URIs) utilizados para alcançar um recurso específico.        |
| Representação  |  Como um recurso é um conceito abstrato, o cliente interage com ele através de uma representação, que captura o estado atual ou pretendido desse recurso. Formatos comuns incluem JSON, XML, HTML e CSV.              |

##### Relação com a Arquitetura REST
A arquitetura REST (Representational State Transfer) é um estilo de software que impõe restrições para garantir escalabilidade e eficiência em sistemas distribuídos.
 - Interface uniforme: padronização da comunicação
 - Client-Server: separação entre cliente e servidor
 - Stateless: cada requisição é independente
 - HATEOAS: navegação guiada por links da API

> [!IMPORTANT]
> REST não é um protocolo, mas um estilo arquitetural. 

##### Relação com o Protocolo HTTP
Embora o REST seja independente de protocolo, o HTTP é sua implementação mais comum e bem-sucedida.

 - Métodos: 
   - GET: Recupera a representação de um recurso
   - POST: Cria um novo recurso
   - PUT: Atualiza ou substitui um recurso existente
   - DELETE: Remove um recurso
 - Status codes: indicam o resultado da requisição
   - 200: Sucesso
   - 201: Criado
   - 404: Não encontrado
   - 500: Erro no servidor
 - Headers: metadados sobre a comunicação

Na prática, uma **API REST** permite acessar e manipular recursos por meio de endpoints, usando métodos **HTTP** e retornando representações estruturadas, geralmente em JSON.

##### Exemplo prático

```json
GET /usuarios/123

Resposta JSON:
{
  "id": 123,
  "nome": "João"
}
```

**Observações:**

- Boa explicação conceitual
- Os elementos básicos de cada assunto foram bem sintetizados
- Faltou clareza na relação entre os conceitos de API e arquitetura REST

> [!TIP]
> Prefira respostas organizadas em tópicos ao usar IA.

---

### Prompt refinado

> ##
>Explique os conceitos fundamentais de uma API, incluindo recursos, endpoints e representações.  
> 
>Em seguida, relacione esses conceitos com a arquitetura REST e com o protocolo HTTP, detalhando o papel de cada um em uma requisição web.  
>  
>Apresente também as 6 restrições fundamentais da arquitetura REST definidas por Roy Fielding e descreva como elas influenciam o design de APIs.  
>  
>Ao final, inclua uma conclusão clara explicando como API, REST e HTTP se relacionam.  
>  
>Organize a resposta em tópicos e inclua exemplos práticos.
> ##

#### Resposta resumida

Uma API (Interface de Programação de Aplicações) é uma interface que permite a comunicação programática entre diferentes sistemas, funcionando como um intermediário entre clientes e recursos na Web.

- **Recurso (Resource):** Representa uma entidade ou informação (ex: usuário, pedido, clima). Não é o dado em si, mas um conceito abstrato que mapeia para um conjunto de dados.
- **Endpoint (Identificador):**  É o endereço único (URI/URL) utilizado para acessar um recurso específico.
- **Representação (Representation):** Forma como o recurso é transferido entre cliente e servidor, geralmente em formatos como JSON, XML ou HTML.

---

##### Relação entre API, REST e HTTP

A arquitetura REST define um conjunto de princípios para o desenvolvimento de APIs, enquanto o HTTP é o protocolo mais utilizado para implementá-los.

Em uma requisição web:

| Elemento            | Papel na requisição                                 |
|---------------------|-----------------------------------------------------|
|Endpoint (Onde)      |Define o recurso acessado (ex: `/users/123`)         |
|Método HTTP (Ação)   |Define a operação (GET, POST, PUT...)                |
|Representação (O quê)|Define o formato dos dados trocados (JSON, XML, etc.)|

O REST exige uma **interface uniforme**, garantindo que essas interações sejam padronizadas e compreensíveis por clientes e intermediários.

---

##### As 6 Restrições do REST

Para uma API ser considerada RESTful, ela deve seguir as restrições definidas por Roy Fielding:

| Restrição             | Descrição                                               | Impacto no Design da API                               |
|-----------------------|---------------------------------------------------------|--------------------------------------------------------|
| Client-Server         | Separa interface do usuário e armazenamento de dados    | Permite evolução independente entre cliente e servidor |
| Stateless             | Cada requisição contém todas as informações necessárias | Aumenta escalabilidade e confiabilidade                |
| Cache                 | Respostas podem ser armazenadas                         | Reduz latência e carga no servidor                     |
| Interface Uniforme    | Comunicação padronizada baseada em recursos             | Facilita integração e desacoplamento                   |
| Sistema em Camadas    | Uso de intermediários (proxies, gateways)               | Melhora segurança e performance                        |
| Código sob Demanda    | Envio opcional de código executável ao cliente          | Aumenta flexibilidade                                  |  

---

##### Exemplos Práticos

1. **Consulta de usuário (GET)**  
    - Endpoint: `/users/123`  
    - Ação: recuperar dados  
    - Resposta: JSON com informações do usuário  
    - Pode incluir links (HATEOAS) para outros recursos  

###

2. **Criação de pedido (POST)**  
    - Endpoint: `/orders`  
    - Ação: envio de dados no corpo da requisição  
    - Resposta: `201 Created` + URI do novo recurso  

---



##### Conclusão

Uma API é a interface que define como sistemas se comunicam.  
A arquitetura REST é o conjunto de princípios que orienta o design dessa API, promovendo padronização, organização e escalabilidade.  
O HTTP é o protocolo utilizado para implementar essa comunicação.

Em resumo:
- **API → o que é exposto**
- **REST → como é estruturado**
- **HTTP → como é transmitido**

**Observações:**

- Melhor clareza  
- Comparação mais prática  

---

### Dificuldades encontradas

As respostas iniciais estavam tecnicamente corretas, entretanto, não houve relação clara entre os conceitos, tornando o entendimento do papel de cada elemento mais difícil. Com o refinamento do prompt, esse problema foi solucionado, permitindo uma explicação mais coesa e uma melhor conexão entre **API**, **REST** e **HTTP**. Embora mais claro em termos conceituais, alguns termos citados na última resposta foram pouco desenvolvidos, como **HATEOAS** e **Status Code**.

---

## 📖 Miniguia de Estudo (Resultado Final)

### Resumo do Tema

#### 1. Conceito de API
Uma API atua como uma interface de comunicação que permite a troca segura de dados entre diferentes aplicações programaticamente. 

#### 2. REST (Arquitetura)
No contexto da Web, o REST (Representational State Transfer) não é um protocolo, mas um estilo arquitetural definido por Roy Fielding que impõe um conjunto de restrições para garantir escalabilidade, confiabilidade e a evolução independente de componentes em sistemas distribuídos. 

#### 3. HTTP (Protocolo)
O HTTP é o protocolo de transferência mais utilizado para implementar essa arquitetura, fornecendo os métodos (como GET, POST, PUT e DELETE) e códigos de status necessários para a interação entre cliente e servidor

#### 4. Recursos e Representações
O pilar dessa arquitetura é o recurso, que representa qualquer conceito nomeável (como um usuário ou um pedido) mapeado conceitualmente e identificado de forma única através de URIs (Uniform Resource Identifiers). 

Como os recursos são abstrações, os clientes interagem com eles por meio de representações — documentos em formatos como JSON, XML ou HTML que capturam o estado atual ou pretendido do recurso em um momento específico.

#### 5. Restrições REST
Para que um sistema seja verdadeiramente RESTful, ele deve aderir a seis restrições fundamentais:

- Separação cliente-servidor  
- Comunicação stateless (cada requisição contém todas as informações necessárias sem depender de  contexto no servidor)  
- Uso de cache  
- Sistema em camadas (invisíveis ao cliente)  
- Código sob demanda (opcional)  
- Interface uniforme  

#### 5.1. Interface Uniforme e HATEOAS
Esta interface uniforme exige que as mensagens sejam autodescritivas e que o estado da aplicação seja guiado por links, conceito conhecido como HATEOAS. 

O "Hipertexto como Motor do Estado da Aplicação" determina que as representações enviadas pelo servidor devem conter links que guiam o cliente sobre quais ações e transições de estado são possíveis a seguir.

#### 6. Relação entre API, REST e HTTP
De forma direta:

- Uma API é o conceito geral de uma interface de comunicação  
- O REST é o conjunto de regras e princípios arquiteturais (o "estilo") que define como essa API deve ser projetada para ser eficiente e escalável em larga escala  
- O HTTP é a ferramenta (o protocolo) utilizada para implementar esses princípios na prática  

Em sistemas web:
- A API define o que é oferecido  
- O REST define como a arquitetura é estruturada  
- O HTTP define a linguagem usada para a troca de informações  

---

### Principais Conceitos

- **Client-Server:** separação entre interface e dados  
- **Stateless:** cada requisição é independente e não depende de contexto do servidor  
- **Cacheable:** respostas podem ser armazenadas para otimização  
- **Uniform Interface:** padronização da comunicação entre sistemas  
- **HATEOAS:** navegação da aplicação baseada em links presentes nas respostas  

---

### Glossário

- **Recurso:** entidade conceitual representada na arquitetura  
- **URI:** identificador único de um recurso na Web  
- **Representação:** forma como o estado de um recurso é transferido (ex: JSON, XML, HTML)  
- **HATEOAS:** mecanismo de navegação baseado em links entre recursos  

---

### Prompts Reutilizáveis

#### Prompt 1 — Exploração inicial

> ##
>Explique os conceitos fundamentais de uma API, incluindo o que são endpoints, recursos e representações. Em seguida, descreva como esses conceitos se relacionam com a arquitetura REST e com o protocolo HTTP. Organize a resposta em tópicos e inclua exemplos práticos.
> ##

#### Prompt 2 — Refinamento conceitual

> ##
>Explique os conceitos fundamentais de uma API, incluindo recursos, endpoints e representações.  
> 
>Em seguida, relacione esses conceitos com a arquitetura REST e com o protocolo HTTP, detalhando o papel de cada um em uma requisição web.  
>  
>Apresente também as 6 restrições fundamentais da arquitetura REST definidas por Roy Fielding e descreva como elas influenciam o design de APIs.  
>  
>Ao final, inclua uma conclusão clara explicando como API, REST e HTTP se relacionam.  
>  
>Organize a resposta em tópicos e inclua exemplos práticos.
> ##

#### Prompt 3 — Resumo geral das fontes fornecidas ao NotebookLM

> ##
>Elabore um documento de resumo abrangente que sintetize os principais temas e ideias das fontes.
>
>Comece com um Sumário Executivo conciso que apresente os pontos mais importantes logo de início.
>
>O corpo do documento deve fornecer uma análise detalhada e completa dos principais temas, evidências e conclusões encontrados nas fontes.
> 
>Essa análise deve ser estruturada logicamente, com títulos e marcadores para garantir clareza. 
>
>O tom deve ser objetivo e incisivo.
> ##

---

## 🚀 Considerações Finais

Este projeto permitiu desenvolver habilidades de:

- Curadoria de conteúdo  
- Pensamento crítico  
- Engenharia de prompts  
- Organização do conhecimento  

Além disso, demonstrou como ferramentas de IA podem potencializar o aprendizado.
