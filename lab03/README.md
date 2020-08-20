
## Lab03 - Model-View-Controller
### Orquestração e Coreografia<br>
Tatiany Fermino Rodrigues de Oliveira<br><br>
## Tarefa 1 - Diagrama de Orquestração

Segue o diagrama de atividades com o fluxo de execução que vai desde o pedido de um produto até a sua entrega para o cliente.
   ![Diagrama de Orquestração](images/diagrama1.png)
<br>
## Tarefa 2 - Diagrama de Coreografia
![Diagrama de Coreografia](images/diagrama2_v2.png) </br>
</br><b>Segue a sequência esperada de ações:</b>
1) Através da interface iVenda o componente Catalogo captura do componente BuscaProduto a propriedade ProdutoBuscado que tem uma string com as palavras chaves buscadas pelo cliente "geladeira branca".
2) Através da interface iBuscaProduto o componente Catalogo assina os seu tópicos de interesse que servirão para receber os lances dos parceiros: "lance/#". 
3) Através da interface iLeilao o componente Parceiro assina os seu tópicos de interesse guardados na propriedade Catalogo, separados por vírgula, são eles: "leilao/geladeira/#, leilao/fogao/#". 
4) O componente Catalogo analisa a string ProdutoBuscado que chega através da interface iVenda e cria um ou mais tópicos para postar no Barramento.
5) Para cada tópico definido pelo componente Catalogo é criado um Leilao_ID que é utilizado como subtópico, por exemplo: "leilao/geladeira/5300".
6) Quando entra no barramento alguma mensagem de algum tópico assinado pelo componente Parceiro, o mesmo registra o seu lance no componente Lance e envia para o barramento a mensagem com o preço para o ProdutoBuscado através da interface iLeilao: "Mensagem: 'R$ 2350,00' Tópico: lance/geladeira/Lance_ID".
7) Através da interface iLeilao o componente Catalogo captura as mensagens com os menores preços, guarda as referências das 3 menores que chegarem primeiro em sua propriedade TresLances.
8) O componente Carrinho através da interface iCash captura a propriedade TresLances do componente Catalogo e busca no Componente Lance os dados para apresentar para o cliente.
9) O componente Carrinho através da interface iNotifica envia para o barramento 3 mensagens para notificar os parceiros donos dos 3 menores lances: "Mensagem: 'exibido' Tópico: leilao/geladeira/5300/<Lance_ID>".
10) Os outros parceiros que continuam observando o tópico "leilao/geladeira/5300" e não tiverem seus lances exibidos já podem excluir seus lances e enviar um mensagem "unsubscribe: leilao/geladeira/5300".


## Tarefa 3
Seguem as telas do meu aplicativo "Mercadinho":
<br><table border="0"><tr><td>Tela 1 <br>Nenhum produto selecionado<br><img alt="Tela 1 - nenhum produto selecionado" src="images/tela1_v2.jpeg" width="60%" height="60%" /></td><td>Tela 2<br>Primeiro produto selecionado <br><img alt="Tela 2 - primeiro produto selecionado" src="images/tela2_v2.jpeg" width="60%" height="60%" /></td><td>Tela 3 <br>Segundo produto selecionado <br><img alt="Tela 3 - segundo produto selecionado" src="images/tela3_v2.jpeg" width="60%" height="60%" /></td></tr><tr><td>Tela 4 <br>Compra de um dos produtos efetiva<br><img alt="Tela 4 <br>Compra de um dos produtos efetiva" src="images/tela4_v2.jpeg" width="60%" height="60%" /></td><td> Tela 5 (extra) <br>Select de produtos <br><img alt="Tela 5 - Select de produtos" src="images/extra1_v2.jpeg" width="60%" height="60%" /></td><td> Tela 6  (extra) <br>2 produtos no carrinho <br><img alt="Tela 6 - 2 produtos no carrinho" src="images/extra2_v2.jpeg" width="60%" height="60%"  /></td></tr></table>
<br>
<details><summary>Mercadinho  - Versão 1</summary>
<table border="0"><tr><td>Tela 1 <br>Nenhum produto selecionado<br><img alt="Tela 1 - nenhum produto selecionado" src="images/tela1.jpeg" width="60%" height="60%" /></td><td>Tela 2<br>Primeiro produto selecionado <br><img alt="Tela 2 - primeiro produto selecionado" src="images/tela2.jpeg" width="60%" height="60%" /></td><td>Tela 3 <br>Segundo produto selecionado <br><img alt="Tela 3 - segundo produto selecionado" src="images/tela3.jpeg" width="60%" height="60%" /></td></tr><tr><td>Tela 4 <br>Compra de um dos produtos efetiva<br><img alt="Tela 4 <br>Compra de um dos produtos efetiva" src="images/tela4.jpeg" width="60%" height="60%" /></td><td> Tela 5 (extra) <br>Select de produtos <br><img alt="Tela 5 - Select de produtos" src="images/extra1.jpeg" width="60%" height="60%" /></td><td> Tela 6  (extra) <br>2 produtos no carrinho <br><img alt="Tela 6 - 2 produtos no carrinho" src="images/extra2.jpeg" width="60%" height="60%"  /></td></tr></table>
</br><b> Diagrama de blocos do aplicativo</b>
	<br><br><img alt="Diagrama de blocos do aplicativo" src="images/blocks.png" width="50%" height="50%" /><br>	
</datails>
	
<b> Diagrama de blocos do aplicativo</b>
	<br><br><img alt="Diagrama de blocos do aplicativo" src="images/blocks_v2.png" width="50%" height="50%" /><br>
 	
[Baixe aqui o arquivo do aplicativo exportado a partir do MIT App Inventor em formato aia.](app/Mercadinho.aia)<br>
   
## Tarefa 4
Imagens da Equipe 6 postadas no endereço [https://github.com/inf331equipe6.](https://github.com/inf331equipe6)
