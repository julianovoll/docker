# How to Remove Images and Containers in Docker
# Docker rmi

O comando docker rmi remove as imagens por ID.

Para remover a imagem, primeiro você precisa listar todas as imagens para obter os IDs de imagem, nomes de imagem e outros detalhes.<br> 
Faça isso executando o comando:

<code>docker images -a</code> ou <code>docker images</code>.

Depois disso, certifique-se de qual imagem deseja remover, para depois fazer isso executando o comando:<br>
<code>docker rmi **id-da-imagem**</code>. <br>
Em seguida, confirme que a imagem foi removida listando todas as imagens e verificando.

# Remover várias imagens

Há uma forma de remover mais de uma imagem por vez quando você quiser remover diversas imagens.<br>
Para fazer isso, obtenha os IDs das imagens listando todas elas e execute o comando a seguir.

<code>docker rmi **id-da-imagem** **id-da-imagem** ...</code>

Escreva os IDs das imagens no comando acima com espaços entre eles.

# Remover todas as imagens ao mesmo tempo

Para remover todas as imagens, há um comando que faz isso:<br>
<code>docker rmi $(docker images -q)</code>

No comando acima, há, de fato, dois comandos. O primeiro, executa em $(), que é a sintaxe do shell, e retorna seja quais forem os resultados executados naquela sintaxe. Enquanto isso, -q- é a opção usada para retornar os IDs exclusivos. $() retorna os resultados dos IDs de imagens e docker rmi remove todas elas.


#Docker rm

docker rm remove contêineres por nome ou por ID.

Quando você tem contêineres do Docker em execução, é preciso pará-los primeiro antes de exclui-los.

Parar todos os contêineres em execução:<br>
<code>docker stop $(docker ps -a -q)</code><br>
    
Excluir todos os contêineres parados:<br>
<code>docker rm $(docker ps -a -q)</code>


origem: https://www.freecodecamp.org/portuguese/news/como-remover-imagens-e-conteineres-no-docker/
