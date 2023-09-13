Integrantes:

RM 99389 - Victor Flávio Demarchi Viana
RM 551117 - Lorenzo Gomes Andreata
RM 550695 - Gabriel Ferla
RM 97888 - Vinícius Almeida Bernardino de Souza
RM 98827 - André Coelho Solér


Sprint 3:

	Descrição:
	     No flow e circuitos disponíveis, você poderá montar um dashboard em MQTT usando a plataforma TagoIO para manter registro de distância, temperatura e umidade do sensor Ultrassônico e do sensor DHT22.

	Requisitos:

	  - É necessário instalar o node-red.
	  - É necessário instalar o node-red-node-serialport.
	  - É necessário instalar o com0com.
	  - É necessário instalar o SimulIDE 1.0.0 ou possuir um arduino com o circuito construido (se o arduino físico for sua escolha, também deve baixar o Arduino IDE).

	Instruções:

	  - Ao instalar o com0com, é necessário deixa-lo aberto em segundo plano, em seguida checar as duas portas "COM" que estão pareadas.
	  - Ao instalar o simulIDE, é necessário carregar o circuito ao arrastar o arquivo "Sprint3.sim1" para a bancada, e em seguida carregar seu firmware ao clicar com botão direito no arduino, clicar em "Carregar firmware" e selecionar o arquivo "Sprint3.hex", e por fim clicar duas vezes com o botão esquerdo na porta serial e trocar o "Nome da porta" para uma das portas do par com0com.
	  - Caso seja um arduino físico, é necessário realizar o circuito de forma parecida ao simulIDE (com as adaptações necessárias), conectar o arduino ao computador, selecionar uma das portas "COM" do par com0com clicando em "Tools, depois em "Port", em seguida selecionar uma das portas "COM" do par, e por fim copiar o código do arquivo "Arduino IDE Code.txt", colar no Arduino IDE e dar "Upload" para o arduino.
	  - Abra o Prompt de Comando do windows e digite "node-red", em seguida acesse "localhost:1880" em qualquer navegador (não feche o prompt).
	  - Arraste o arquivo "Sprint3.json" para dentro do Node-Red (considerando que o módulo de portas serial já foi instalado).
	  - Troque a porta serial clicando duas vezes no nódulo, em seguida no lápis, digite o nome da outra porta serial do com0com que completa o par, clique na lupinha e selecione a porta digitada.
	  - Caso o nódulo "function" não possua código dentro, copie e cole o conteúdo do arquivo "Node_Red_Function.txt" e cole na aba "On Message".
	  - Depois, é necessário se cadastrar no site da TagoIO, ir na aba "Devices", clicar em "Add Device", clicar em "Custom MQTT", trocar o "Device name" por qualquer um que desejar, e clicar em "Create my Device".
	  - Após isso, voltar a aba "Devices" e clicar no recém criado dispositivo, depois trocar o nome da token para o que desejar e clicar em "Generate", por fim clicar nas duas folhas de papel sobrepostas ou clicar sobre o token e copiar seu código.
	  - De volta ao Node Red, clique no nódulo de "mqtt out", em seguida coloque no campo "Topic" o seguinte valor "tago/data/post", após isso clique no lápis e subititua o campo "Server" por "mqtt.tago.io", o campo "ClientID" por qualquer nome que desejar, e no campo "Security", o "Username" deve ser o mesmo que colocou no "ClientID" e a "Password" deve ser o código da token que foi copiada no TagoIO, e finalizar cliando em "Add" e em seguida "Done".
	  - Em seguida clique em "Deploy" no canto superior direito.
	  - Inicie a sua aplicação no SimulIDE ou Arduino físico para testar a aplicação.
	  - Voltando ao TagoIO, clique na aba "Buckets", em seguida no dispositivo que criou, depois em "Variables" e cheque se aparecem "distancia", "temperature" e "humidity", como mostrado na imagem "Buckets_TagoIO.png".
	  - Caso não, reveja as etapas anteriores e tente novamente, caso sim, clique no "+" ao lado de "DASHBOARDS", dê um nome para sua tabela e clique em "Create my Dashboard".
	  - Em seguida, entre no modo editor ao clicar no lápis no canto superior direito (caso não o veja é porque já está nele), em seguida clique no "+" no canto superior direito e escolha dentre as opções de "Widgets".
	  - Após feita a escolha, Acesse a aba "Data from" e, no campo "Device", digite o nome do dispositivo que criou, em seguida selecione o campo "Variable" e digite "distancia", depois, clicar em "Create".
	 - Repita o passo anterior mais duas vezes, porém trocando o valor do campo "Variável" para "temperature" e "humidity".
	- Em seguida, clique no dashboard que criou e reinicie a simulação (seja no SimulIDE ou Arduino físico).
	- Tudo feito!