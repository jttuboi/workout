você deve desenvolver um app em flutter de treino físico baseado nas definições que passarei por etapas.

Primeiro vamos ver o que terá o app. Ele deve ter uma página home para lista de treino, deve ter uma página de settings, deve ter um bottom sheet para detalhes do treino, deve ter uma dialog de confirmação, deve ter uma página de treino.

Os dados serão o seguinte:

- treino
  -- data (datetime)
  -- tipo (string)
  -- detalhes (string)

- tipo corrida
  -- distancia (tipo de dado: double, default: vazio, hint: km, format: x.xx)
  -- pace (tipo de dado: duration, default: vazio, hint: min/km, format: mm:ss)

- tipo calistenia
  -- repetições (tipo de dado: int, default: 3, hint: "qte", format: x)
  -- lista de exercicios

- exercicios para calistenia
  -- flexão (tipo de dado: int, default: 15, hint: "qte", format: x, tempo default pré exercicio: 30 seg, checkbox: true, image_url: string do asset)
  -- agachamento (tipo de dado: int, default: 30, hint: "qte", format: x, tempo default pré exercicio: 10 seg, checkbox: true, image_url: string do asset)
  -- fundo (tipo de dado: int, default: 8, hint: "qte", format: x, tempo default pré exercicio: 40 seg, checkbox: false, image_url: string do asset)
  -- prancha (tipo de dado: duration, default: 50, hint: "seg", format: ss, tempo default pré exercicio: 10 seg, checkbox: true, image_url: string do asset)
  -- barra (tipo de dado: int, default: 5, hint: "qte", format: x, tempo default pré exercicio: 60 seg, checkbox: false, image_url: string do asset)

Na lista de treino, os itens deverão ser ordenados por data do mais atual para o menos atual. ela terá a data, terá o titulo q será o nome do tipo, terá os detalhes, terá um botao de editar, terá um botao de deletar. qndo clica no botão de deletar, aparecerá uma dialog para confirmar a exclusão. qndo clica no botão de editar, ele abre o bottom sheet dos detalhes.
Ainda na tela home, terá um botão floating de adicionar um novo treino, qndo clica ele abre o bottom sheet dos detalhes. tbm terá um app bar com um botão pra tela de settings.

Na tela de settings, terá um app bar com um um botão voltar, um titulo escrito settings e um botão de exportar os dados em csv/json. no corpo, terá a lista de exercicios da calistenia. ela terá os default q sao flexão, agachamento, fundo, prancha e barra. em cada item ele terá um campo pra qual será o valor default e tbm o tempo default pré exercicio. dá pra atualizar os valores default por aqui. também deve ter um checkbox para escolher se ele será mostrado ou não como exercicio default na lista de exercicio de um treino novo.

No bottom sheet, terá a data de quando aconteceu o treino, o tipo de treino (corrida ou calistenia) e o detalhes.
Ai se for corrida, terá os campos de distancia e pace. lembrando que terá q colocar os hint e o format.
Se for calistenia, terá a quantidade de repeticoes e a lista de exercicios. no item do exercicio, terá o checkbox, o dado e o tempo pré exercicio. na lista de exercicio. pode reorganizar os exercicios na ordem que quiser via drag and drop.
Para ambos, se for edição, entao ele só tem o botao salvar.
Para inserção, se for corrida ele é igual o editar. Para calistenia, terá o botão iniciar e redireciona para tela de treino.

Na dialog pode ser um dialog de confirmaçao se quer deletar ou nao.

Na tela de treino, terá a imagem do exercicio, a qte recomendada, a repeticao atual, a qte feita e o botao next.
para aquele caso em q tiver duraçao, terá um timer q inicia crescendo ao invés do campo q mostra a qte feita. qndo clica em next, ele irá salvar o tempo q foi feito.
entre os exercicios, terá o tempo pré exercicio como contador até terminar. ai qndo termina a contagem ele aparece os campos citados anteriormente. lembrando q o primeiro exercicio nao tem contagem, ele já vai direto pros campos.
quando é o ultimo exercicio da ultima repeticao, ao clicar no botao next, ele sairá do treino e irá pra tela home. o treino será adicionado na lista de treinos.
Só pra confirmar, a tela de treino ela mostra o defult recomendado, seja quantidade ou seja tempo, e tbm terá o campo para anotar a qte feita e se for por tempo, terá o timer rodando.

No app, ele terá 2 coisas adicionais. O banco de dados drift para armazenar os dados dentro do app. E um controlador para exportar os dados em csv/json via share_plus.

Na construção do app, usar nomes de variáveis e afins em inglês, pois o código deve ser totalmente em inglês.
Já os dados deve ser em português, pois o app deve ser um app brasileiro.

Para a estrutura do projeto, usar para telas "screen", "dialog" e "bottom_sheet". tbm cada tela terá seu manager para gerenciar o estado da tela. tbm terá o repository para gerenciar os dados, acessando banco de dados e etc. se tiver regra de negocio, usar "use_case" q pode ser chamado pelo manager. terá os services para controlar coisas externas como o drift e o share_plus. qqr outra coisa q for externo, tbm colocar como service. pode utilizar o padrao de arquitetura recomendado pelo flutter com o command.
