# Yourviews - Vtex Faststore

Esse help tem como objetivo passar as instruções de como inserir o script da yourviews e as informações necessárias dos produtos para que a yourviews possa exibir os elementos corretamente em seu site que usa a FastStore da VTEX.

Abaixo há um passo a passo a ser seguido para que tudo funcione corretamente.

## Passo 1 - Obter o script da yourviews com a sua chave de loja

O script da Yourviews é o primeiro passo é o mais importante para que tudo funcione corretamente.

Importante: Certifique-se que a você esteja usando o script com a chave da sua loja corretamente!

Para isso acesse o painel com seu login e senha da Yourviews e acesse essa url: [https://service.yourviews.com.br/admin/Account/StoreApi](https://service.yourviews.com.br/admin/Account/StoreApi)

Nessa tela você poderá obter a chave da sua loja correta!

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc6dD-t5kkcBP5WobrA5z0OzVJoW9U123MCDD48M2h9q7agflp5Me2hi3Iepo6Wzw9SUQ7TA4C6IuN967SjSDO39ibNSql6yhA-kr8tPLlxgztwF6tc0WsddWoOe4MtlReb5vmQJQ?key=fzk-W8PesKQC-gQs6-CF8g)

Copie e cole no lugar `{chave_da_loja}` no script abaixo:

```
(function () {
var yvs = document.createElement("script");
yvs.type = "text/javascript";
yvs.async = true;
yvs.id = "_yvsrc";
yvs.src = "//service.yourviews.com.br/script/{chave_da_loja}/yvapi.js";
var yvs_script = document.getElementsByTagName("script")[0];
yvs_script.parentNode.insertBefore(yvs, yvs_script);
})();
```
o script deverá ficar assim, com a sua chave, exemplo:
```
(function () {
var yvs = document.createElement("script");
yvs.type = "text/javascript";
yvs.async = true;
yvs.id = "_yvsrc";
yvs.src = "//service.yourviews.com.br/script/22ea3a15-68cc-4866-3ffd-11533c4d1122/yvapi.js";
var yvs_script = document.getElementsByTagName("script")[0];
yvs_script.parentNode.insertBefore(yvs, yvs_script);
})();
```

Após copiar seu script com a chave da sua loja, agora podemos ir para o passo 2 que é inserir isso no código da sua loja faststore.

## Passo 2 - Inserir o script da yourviews na faststore

* É Importante ressaltar que os próximos passos é necessário de conhecimento técnico em programação para realizar as implementações!

Dentro do código fonte da loja faststore, seguiremos inserindo um ThirdPartyScript como é mencionado na documentação da faststore: [https://developers.vtex.com/docs/guides/faststore/project-structure-handling-third-party-scripts](https://developers.vtex.com/docs/guides/faststore/project-structure-handling-third-party-scripts)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdkqAHlknDb2r0AOsYjzX6lzCwJ3JWgYJ30RBCKhXnKlmAYoai5hPAB7DBmVCA20ZSh_ghXxlcQFStGrOFxrhzYKje8KexatkyuVdc6wcFgTajuQG6_icCOiR3ldA_HouxNpoAT?key=fzk-W8PesKQC-gQs6-CF8g)

Adicione o script em uma variável com crase e insira a variável dentro de __html para que ele seja inserido no seu site.

Após isso, execute yarn dev para certificar que o script foi inserido, procure por “yvapi” dentro do html do seu site e veja se encontre:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdUaxbw5oTJZo20M5Srb9SybwHd7Z2To9I29kSxalDRnnobPfCiIah2FK0tyc5kyZQUl8cOOGCNdBIWgXew-Q2pW0mnY32XivBzrl-4Jdn4TEfBBfvwr4nOyc5BR9x17RFtOix3IA?key=fzk-W8PesKQC-gQs6-CF8g)

**Pronto!**

## Passo 3 - Adicionar as Informações do Produto na PDP

Para inserir as informações da Yourviews na PDP da loja, é necessário seguir um passo a passo:

### Passo 3.1 - Configurar o Headless CMS

Primeiramente, é importante seguir a docuemntação de configuração da loja com o headless CMS da vtex e faststore: [https://developers.vtex.com/docs/guides/faststore/headless-cms-overview](https://developers.vtex.com/docs/guides/faststore/headless-cms-overview)

### Passo 3.2 - Criar a section

Após toda a configuração do Headless pronta, vamos para o código em cms/sections.json e adicionamos uma nova section para a seção da Yourviews:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc_XWPiJGSxDn9EAFzTwXhv7qrVHoREkxLKBGKLr9NKIUkvbHcPiTeAsU2bIqOIRjRa2AwJvb2_3LlQ-Vt2E036jLQwLQSsM7rRcIv_MBUR9bFhuVnuPo2I0AZVL2o1e_4lSCVK?key=fzk-W8PesKQC-gQs6-CF8g)

Código:

```
{
  "name": "YourviewsProductInfos",
  "schema": {
    "title": "Yourviews Product Infos",
    "description": "",
    "type": "object",
    "required": [],
    "properties": {}
  }
}
```

### Passo 3.3 - Criar o componente

Após criar a section, vamos criar o componente em /src/components/YourviewsProductInfos.tsx

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjo0Ar3Fmpo5O4wXt4RHC_0F80wcQQrqq-YEGIn8fTZjqUhYBCqbjQfuQxoL0W-XKk-lagV_qwiUnIIfPGNS0vevDctlImNL2eqPhbnwu8P66_E15gQ5ZyK3giTRfQBJTeAwbdHQ?key=fzk-W8PesKQC-gQs6-CF8g)

Código:

```
import React from "react";
import { usePDP } from "@faststore/core";

export default function YourviewsProductInfos() {
  const pdp = usePDP();
  
  return (
    <div>
      <input
        id="yv-productId"
        type="hidden"
        value={pdp?.data?.product?.isVariantOf?.productGroupID}
      />
      <input
        id="yv-productName"
        type="hidden"
        value={pdp?.data?.product?.name}
      />
      <input
        id="yv-productImage"
        type="hidden"
        value={pdp?.data?.product?.image[0]?.url}
      />
      <input
        id="yv-productPrice"
        type="hidden"
        value={pdp?.data?.product?.offers?.lowPrice}
      />
      <input
        id="yv-productCategory"
        type="hidden"
        value={
          pdp?.data?.product?.breadcrumbList?.itemListElement[
            pdp?.data?.product?.breadcrumbList?.itemListElement?.length - 2
          ]?.name
        }
      />
    </div>
  );
}

```

### Passo 3.4 - Exportar o componente

Após a seção e o componente criados, agora precisamos exportar o componente no arquivo components/index.tsx:

![](https://i.imgur.com/FDWZ7xz.png)
 
 Código:
```
import YourviewsProductInfos from "./YourviewsProductInfos";

export default {
  YourviewsProductInfos,
};
```


### Passo 3.5 - Sincronizar e Adicionar na PDP

Agora basta adiconar esse componente no Headless CMS na PDP, para isso, siga as instruções da VTEX Faststore para efetuar o cms-sync:
https://developers.vtex.com/docs/guides/faststore/headless-cms-overview

Após sincronizar, vá até o painel da VTEX, acesse o Headless CMS e vá até a PDP:
![](https://i.imgur.com/6flNi7f.png)

E insira a seção em qualquer local da PDP:
![](https://i.imgur.com/x9SvVkN.png)

Ficando assim:
![](https://i.imgur.com/lAYVN7J.png)

Após isso, basta confirmar se em qualquer PDP, os elementos estão sendo inseridos:
![](https://i.imgur.com/KrWlK8i.png)

**Pronto!**

## Passo 4 - Adicionar o identificador de cada produto nas prateleiras

O identificador do produto nas prateleiras serve para que o script da Yourviews possa exibir das estrelas de avaliação de cada produto nas prateleiras (shelfs), para inserir esse identificador corretamente, basta seguir os passos abaixo:

Dentro do código fonte da loja faststore, vá até o código de personalização das prateleiras que foi implementado para a loja e insira um novo elemento parecido com os elementos inseridos no passo 3:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfi3oNoW8zsZh_0Jo0Q_w6iU_CxssfMEyrCtSDMp1FLlRRh3rEZ3QV-sjY3nY2LcB7zL4rtJqxby48YwnHj14j0m_7JYJTDdEAl_TxREGLmMIrgnVWnqyyGPeKtWlYrOMakD8p9?key=fzk-W8PesKQC-gQs6-CF8g)

O local onde o input é inserido é opcional, porém precisa ficar dentro de cada card de cada produto na prateleira de produtos.

Importante: O atributo value precisa ser o “productGroupID” que fica dentro de “isvariantOf”, como é mostrado no print acima, isso serve para que possamos obter o id do produto original e não o id do sku.

Caso sua loja não possua uma personalização de prateleiras ainda, recomendamos que siga as instruções na documentação da VTEX Faststore para que crie uma nova personalização a insira o input:

[https://developers.vtex.com/docs/guides/faststore/organisms-product-shelf](https://developers.vtex.com/docs/guides/faststore/organisms-product-shelf)

[https://developers.vtex.com/docs/guides/faststore/building-sections-overview](https://developers.vtex.com/docs/guides/faststore/building-sections-overview)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzMjQzMjc5OV19
-->