## Casa&Cor

### :computer: [Link do Projeto](https://casa-e-cor.vercel.app/)

---

#### Casa&Cor é um site 100% profissional responsivo de empresa de construção, com dark-mode e 5 páginas feito em HTML, LESS e JavaScript, sem o uso de frameworks.

---

### :green_circle: Google Lighthouse - Mobile

![lighthouse_performance](https://github.com/tiagocreator/casa-e-cor/assets/82607849/f322d93c-2e16-4264-9a38-415ee415ca70)
![lighthouse_accessibility](https://github.com/tiagocreator/casa-e-cor/assets/82607849/19af3c74-197a-4ae3-9858-bf2604df7b41)
![lighthouse_seo](https://github.com/tiagocreator/casa-e-cor/assets/82607849/b6d214c6-f6cb-4d1d-83cb-236525377211)
![lighthouse_best-practices](https://github.com/tiagocreator/casa-e-cor/assets/82607849/3c2acd78-d8bd-4c1d-a9c3-fe40e84260e3)

---

### :sparkles: Sobre o Site

Esse site utiliza o pré-processador de CCS, LESS, para usar sua capacidade de fazer cálculos de CSS para a responsividiade. Como as unidades __'em'__ são baseadas no tamanho da fonte de seu elemento pai. Se o elemento pai não tiver um tamanho de fonte declarado em seu CSS, o próximo elemento pai com um tamanho de fonte declarado será sua base. Como não estou declarando um tamanho de fonte em nenhum container, literalmente tudo na página procurará um tamanho de fonte na tag __'body'__ e, como declaramos um tamanho de fonte de __'20px'__, os containers se dividirão para obter o valor em __'em'__. Então, apenas defino o tamanho da fonte na tag __'body'__ para __'15px'__ em dispositivos móveis, tablets e desktops pequenos com até __'1023px'__ de largura. Em seguida, em __'1024px'__ de largura, é definido como __'20px'__.

---

### Explicando o funcionamento

As medidas de cada elemento que estariam em pixels agora estarão em __'ems'__ divididas em 20 (o tamanho de fonte padrão do projeto). Portanto, quando temos um elemento com __'100px'__ de largura, no arquivo __'.less'__ o escrevemos como __'100/20em'__, e o compilador o compilará em css como __'5em'__. Como o cálculo do __'em'__ é baseado em __'20px'__, quando alteramos o tamanho da fonte da tag __'body'__ para __'15px'__, ele encolherá TUDO porque os cálculos do __'em'__ estão em um tamanho de fonte menor e diminuirão proporcionalmente.

Por exemplo, se um elemento tiver __'20px'__ de largura, ele será escrito como __'20/20em'__ em seu arquivo __'.less'__ e compilado para __'1em'__ em seu arquivo __'.css'__. Essa é a sua proporção. Quando alteramos o tamanho da fonte do __'body'__ (a tag pai principal de tudo) para um número menor no celular, por exemplo, (__'15px'__), estamos dimensionando o tamanho de __'1em'__ para caber em uma fonte baseada em __'15px'__ em vez de __'20px'__. __'1em'__ seria tecnicamente __'15/15em'__, o que significa que ao reduzir o tamanho da fonte da tag __'body'__ em __'5px'__, TUDO que se baseia em seu tamanho de fonte de __'20px'__ também se reduzirá em __'5px'__ em escala.

Ambas as instâncias de __'15/15'__ e __'20/20'__ resultam em __'1em'__. O tamanho da fonte base do pai determina quão grande o valor __'1em'__ é escalado para cima ou para baixo por padrão. Pense em __'ems'__ como a proporção da medida e seu tamanho de fonte pai, e o tamanho da fonte da tag __'body'__ está dizendo no total, em tudo, o quão grande ou pequeno eles precisam ser. Estamos definindo a proporção com base nos estilos e medidas da fonte padrão.

Quanto maior o tamanho da fonte da tag __'body'__, maior será a escala de __'1em'__. Tamanhos de fonte menores diminuem o tamanho de __'1em'__. É assim que podemos controlar a responsividade móvel. __Assim, não precisa escrever estilos CSS separados para seu celular e fazer tamanhos maiores no desktop__. Ao escrever todos os valores de __'px'__ de nossas propriedades __'css'__ em __'x/20em'__, tudo será reduzido no celular e crescerá para seu tamanho de escala final no tamanho de fonte de __'20px'__.

Para que esse projeto funcione corretamente e dimensione como deveria, utilizei esse sistema de cálculo __'.less'__. Portanto, se tiver um texto __'h1'__ que deveria ter __'50px'__, eu escrevo como __'50/20em'__. Assim como eu faria normalmente. __No entando, qualquer uma de suas propriedades e filhos precisam ser divididos pelo novo tamanho de fonte declarado__. Portanto, se tiver uma margem inferior de __'20px'__, será __'20/50em'__, e não __'20/20em'__. Porque o pai tem seu próprio tamanho de fonte declarado agora.

Aqui está um exemplo de como isso fica em __'.less'__ usando a tag __'h1'__:

```
h1 {
    color: #fff;
    font-size: 24/20em; <--- Novo tamanho de fonte declarado
    line-height: 28/24; <--- Tudo dentro do h1 é dividido por este novo tamanho de fonte (line-height não precisa adicionar 'em')
    margin-bottom: 15/24em; <--- Tudo dentro do h1 é dividido por este novo tamanho de fonte

    span {
        display: block;
        color: #fff;
        margin-bottom: 50/24em; <--- Tudo dentro do h1 é dividido por este novo tamanho de fonte
    }
}
```

Além disso, se essa tag __'span'__ tiver um tamanho de fonte diferente da tag __'h1'__, eu declaro o novo tamanho da fonte dividido pelo novo tamanho da fonte do pai.

```
h2 {
    font-size: 24/20em; <--- Novo tamanho de fonte

    span {
        display: block;
        color: #fff;
        font-size: 50/24em  <--- Novo tamanho de fonte declarado, dividido pelo tamanho da fonte da tag pai
        margin-bottom: 50/50em; <--- Tudo dentro da tag span é dividido por este novo tamanho de fonte
    }
} 
```

---

### Como modificar os estilos projeto e usar esse sistema no seu computador

1. Eu utilizei o pré-processador LESS para usar sua capacidade de fazer cálculos.

Para instalar o pré-processador LESS, primeiro você deve baixar e instalar o __npm__ para poder instalar qualquer programa que desejar com uma linha de código.
Após instalar o __npm__, instale o LESS usando o seguinte comando no seu terminal:

__npm install less__

2. Eu uso o aplicativo Koala para compilar os arquivos LESS para CSS, com a função de compilação automática em tempo real.

Aqui está um link para baixar o Koala:
http://koala-app.com/

Clique no ícone de __'+'__ e selecione a pasta __css__ do projeto para iniciar o processo de compilação de LESS para CSS. Enquanto o aplicativo estiver aberto, ele irá monitorar e compilar automaticamente.

![koala](https://user-images.githubusercontent.com/82607849/235378495-3ba4dced-2001-4dde-9e6a-3760eca83d2b.png)

---

### :notebook: Licença

Criado e distribuído sob a licença __GPL v3__, veja LICENSE.txt para mais informações.
  
---

### :handshake: Contribuições

As contribuições são o que torna a comunidade de código aberto um lugar incrível para aprender, se inspirar e criar. Qualquer contribuições que você fizer são muito apreciadas.

Se você tiver uma sugestão para melhorar o projeto, faça um fork do repositório e crie uma solicitação pull. Você também pode simplesmente abrir uma issue com a tag "melhoria". Se puder, por favor, dê para dar uma estrela ao projeto! Obrigado.

---  

### Imagens

Página Home Light:

![home-light](https://github.com/tiagocreator/casa-e-cor/assets/82607849/228dffe4-b32d-461e-80c7-d08db6a27a2c)

Página Home Dark Mobile:

![home-dark-mobile](https://github.com/tiagocreator/casa-e-cor/assets/82607849/1599b5f3-cf55-4b18-ae14-bfc90150b963)

---

### :computer: [Link do Projeto](https://casa-e-cor.vercel.app/)
