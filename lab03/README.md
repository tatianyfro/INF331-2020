
## Lab03 - Model-View-Controller
### Orquestração e Coreografia<br>
#### ALUNO
Tatiany Fermino Rodrigues de Oliveira<br><br>
## Tarefa 1 - Diagrama de Orquestração

Segue o diagrama de atividades com o fluxo de execução que vai desde o pedido de um produto até a sua entrega para o cliente.
   ![Diagrama de Orquestração](images/diagrama1.png)
<br>
## Tarefa 2 - Diagrama de Coreografia
![Diagrama de Coreografia](images/diagrama1.png) </br>
Segue a sequência esperada de ações:
1) Através da interface iVenda o componente Catalogo captura do componente BuscaProduto a propriedade ProdutoBuscado que é uma string com as palavras chaves buscadas pelo cliente
2) Através da interface iBuscaProduto o componente Catalogo assina os seu tópicos de interesse que servirão para receber os lances dos parceiros
3) Através da interface iLeilao o componente Parceiro assina os seu tópicos de interesse guardados na propriedade Catalogo, separados por vírgula
4) Através da interface iVenda o componente Catalogo analisa a string ProdutoBuscado e cria um ou mais tópicos para postar no Barramento
5) Para cada tópico definido pelo componente Catalogo é criado um Leilao_ID que é utilizado como subtópico, por exemplo: "leilao/geladeira/5300"
6) Quando entra no barramento alguma mensagem de algum tópico assinado pelo componente Parceiro, o mesmo registra o seu lance no componente Lance e envia para 
o barramento a mensagem com o preço para o ProdutoBuscado através da interface iLeilao
7) O componente Catalogo captura as mensagens com os menores preços, guarda as referencias dos 3 menores que chegaram primeiro na sua propriedade TresLances
8) O componente Carrinho através da interface iCash captura a propriedade TresLances do componente Catalogo e busca no Componente Lance os dados para apresentar para o cliente 
9) Após apresentação dos 3 menores lances e o cliente enviar o lance selecionado para o carrinho através da interface iNotifica o barramento recebe os status dos lances ("selecionado" ou "não selecionado").
## Tarefa 3
Seguem as telas do meu aplicativo "Mercadinho":
<br><table border="0"><tr><td>Tela 1 <br>Nenhum produto selecionado<br><img alt="Tela 1 - nenhum produto selecionado" src="images/tela1.jpeg" width="60%" height="60%" /></td><td>Tela 2<br>Primeiro produto selecionado <br><img alt="Tela 2 - primeiro produto selecionado" src="images/tela2.jpeg" width="60%" height="60%" /></td><td>Tela 3 <br>Segundo produto selecionado <br><img alt="Tela 3 - segundo produto selecionado" src="images/tela3.jpeg" width="60%" height="60%" /></td></tr><tr><td>Tela 4 <br>Compra de um dos produtos efetiva<br><img alt="Tela 4 <br>Compra de um dos produtos efetiva" src="images/tela4.jpeg" width="60%" height="60%" /></td><td> Tela 5 (extra) <br>Select de produtos <br><img alt="Tela 5 - Select de produtos" src="images/extra1.jpeg" width="60%" height="60%" /></td><td> Tela 6  (extra) <br>2 produtos no carrinho <br><img alt="Tela 6 - 2 produtos no carrinho" src="images/extra2.jpeg" width="60%" height="60%"  /></td></tr></table>
	
<b> Diagrama de blocos do aplicativo</b>
	<br><br><img alt="Diagrama de blocos do aplicativo" src="images/blocks.png" width="50%" height="50%" /><br>
 	
[Baixe aqui o arquivo do aplicativo exportado a partir do MIT App Inventor em formato aia.](app/Mercadinho.aia)<br>
   
## Tarefa 4
Imagens da Equipe 6 postadas no endereço [https://github.com/inf331equipe6.](https://github.com/inf331equipe6)
