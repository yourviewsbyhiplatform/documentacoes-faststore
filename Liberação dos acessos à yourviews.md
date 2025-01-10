# Liberação dos acessos à yourviews

A liberação de acessos para a yourviews é necessária para que seja possível obtermos os dados dos pedidos de sua loja para que possamos disparar os emails corretamente para seus clientes efetuarem uma avaliação, e também, para que possamos fornecer um suporte com a melhor qualidade possível.

## Passo a Passo

### Passo 1 - Criando perfil de acesso na vtex

O primeiro passo é criar um perfil de acesso no painel administrativo da vtex para a yourviews.

Para isso, a maneira mais simples de se chegar a essa tela no painel da vtex, é clicando no ícone do seu avatar no canto superior direito, clicar em "configurações da conta" e depois em "perfis de acesso"

![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZjF2NG1qcHBjY2NxenpremwxamNiamFyZjhpZHZ0bDU2N2JpcWZ5MSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/YjIbPpNjeB6D1XHIZ4/giphy.gif)

Após acessar os perfis de acesso, vamos clicar em "Novo Perfil"
![](https://i.imgur.com/DWcOlPO.png)

Agora vamos dar um nome e cadastrar cada produto e recurso

#### Passo 1.1 - Nome do Perfil
Recomendamos que você de o nome de "yourviews" para esse perfil e selecione o perfil "custom"
![](https://i.imgur.com/QGjfyvc.png)

#### Passo 1.2 - Produto OMS
Esse produto serve para que a yourviews possa ter acesso aos pedidos da sua loja
Para isso, selecione o produto "OMS" e selecione os recursos a seguir:
 - View Order
 - List Orders
 - View store sales stats

Após selecionado os recursos, basta clicar em "configurar outro produto"

![](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExd29jNW9tNWZqZ3M2N3VjM3psemJveThuaXNzbGF2b3JscmlvMHphaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/YR9VN9cVj2Zoqo9oZ6/giphy.gif)

#### Passo 1.2 - Produto Catalog

Esse produto serve para que a yourviews possa ter acesso ao CMS da loja.
Para isso, selecione o produto "Catalog" e selecione o recurso a seguir:
 - Configuration -> CMS
 
Após selecionado os recursos, basta clicar em "configurar outro produto"
![](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExajN2YnpqaHJ2eXZjM20wdmo0bjI1cm1vZTd4eG1weno4Y3Btem1iNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Nsw3DayZu7B1aj6NX8/giphy.gif)

#### Passo 1.3 - Produto CMS e GraphQL

Esse produto serve para que a yourviews possa ter acesso ao cms da loja corretamente e ao graphql da loja.
Para isso, selecione o produto "CMS" e selecione todos os recursos
 
Após selecionado os recursos, basta clicar em "configurar outro produto"

![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExemRmMGNvazIyYnlpczVqcmJwZGE4Z3d1Y2xkNHp0NHJxNTdudDFhbyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/zDEkOlwOfzsJdeTbcS/giphy.gif)

Agora que já adicionamos todos os recursos e produtos necessários, precisamos adicionar o e-mail da yourviews a este acesso:

Adicione o email `acesso@yourviews.com.br` e clique em adicionar para passar os devidos acessos criados para a yourviews.

![](https://i.imgur.com/sehSTM4.png)

Agora é só clicar em "salvar"

![enter image description here](https://i.imgur.com/vg26m6X.png)

### Passo 2 - Criando chave de aplicação

A criação da chave de aplicação é necessária ser criada e passada para o time de onboarding da HiPlatform / Yourviews para que possamos integra a sua loja com a nossa plataforma.

Para isso, vamos primeiro acessar a tela de criação de chaves de acesso:

![enter image description here](https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExd2tzbTdndTY0MG1wa2Q4aTIxZXIxa2JlODd4YjduNXk2cHdtczczMSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Kr4BztRLMEobefxjB4/giphy.gif)

Clique em "gerenciar minhas chaves" e depois em "gerar chave" para podermos criar uma nova chave

Na tela de criação da chave, recomendamos que coloque um rótulo com o nome da yourviews. Após isso, clique em "adicionar perfis" e adicione o perfil que você acabou de criar:

![](https://i.imgur.com/HbSWQad.png)

Clique em "gerar""
**Importante!** Não esqueça de salvar a chave de aplicação e o token com muito cuidado para depois enviar para o time da HiPlatform / Yourviews!

![enter image description here](https://i.imgur.com/76LoU1P.png)

Para enviar para o nosso time a chave e o token, envie da seguinte maneira:
```
VtexAppKey: {sua_chave_de_aplicação}
VtexAppToken: {seu_token_de_aplicação}
```

### Finalização

**Pronto!**

O acesso para a yourviews está pronto!

**Mas calma!**

Agora o próximo passo é inserir o script e elementos na faststore
Para isso, [clique aqui](https://github.com/yourviewsbyhiplatform/documentacoes-faststore/blob/master/Instalar%20Yourviews%20na%20VTEX%20Faststore.md), para ver o passo a passo.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyODYzOTU3MDNdfQ==
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzYyNTQ1MzQzXX0=
-->