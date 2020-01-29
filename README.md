# ShellScript__monitoracao_servidores
Shell script para monitorar servidores stand-alone sem uso de ferramentas, com alertas via email e thresholds definidos em arquivo de configuração.

##  Foi meu inicio de codificação de scripts de grande quantidade de linhas, ao qual tive a necessidade de monitorar servidores no ambiente onde trabalhava//
    pois não tinha ferramentas disponíveis e nem podia implementar nenhuma.
    E um codigo ainda meio primitivo, mas que me ajudou em muito na monitoração do ambiente.
    
    Este script foi publicado no meu antigo blog pontosh do wordpress (pontosh.wordpress.com).
    
    Codigo completo para realizar monitoração e coleta de dados de performance de servidores linux através da crontab.

"""
Renomear o arquivo abaixo para .sh ou .txt .

script-para-monitoracao-completo

Quantas e quantas vezes não fomos surpreendidos com algum filesystem que chegou à 100% de utilização ou o load da máquina subiu demais deixando o seu ambiente lento. Sabemos que há várias ferramentas de monitoração pagas ou open source, porem, muitas vezes precisamos de um simples e-mail informando o evento ou em algum momento consolidar o histórico de utilização de recursos da máquina em um gráfico ou planilha.

Foi devido à essas necessidades que desenvolvi um script para coletar informações de uso de CPU, memória, Load e uso de filesystems, e tambem informar através de e-mail, algum threshold que foi violado.
Deixarei o código aberto para ajudar os “brothers da tela preta” e permitindo que a comunidade possa alterar e customiza-lo para as suas necessidades.

Existem alguns pré-requisitos para poder utilizar o script:
– Pacotes mailx, sendmail (ou postfix), sysstat e sudo;
– Sudo configurado para permitir executar os comandos touch e chown no /etc/threshold.env;
– Sendmail ou postfix com relay devidamente configurado;

Após configurado, o script cria um diretório monitora, que por padrão é o home do usuário que está executando, mas que será solicitado mudança na primeira execução.
Serão criados arquivos com o historico da coleta, sendo gravados dentro do subdiretorio historico, e à cada dia é criado um arquivo novo (ex. HISTORICO_02-03-2015.txt).
Este arquivo de texto com campos separados por vírgulas, poderá ser utilizado para gerar um gráfico ou importar em planilha ou banco de dados.
Também será criado um arquivo com os parâmetros de threshold (/etc/thresholds.env), que servirá como base de comparação no momento da verificação e irá realizar o alarme se o parâmetro coletado for maior do que esperado.
Será criado uma entrada na crontab, ao qual voce irá informar a periodicidade de checagem, em minutos,

Basta copiar o texto abaixo, salvar como monitor.sh no seu home e rodar primeiramente com o parametro -configurar com seu usuário ou root para realizar a criação do diretório, arquivos e configuração.

Renomear o arquivo abaixo para .sh ou .txt .
"""
