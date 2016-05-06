# Text2Net-Console
Ferramenta de linha de comando para gerar redes a partir de textos baixados do DOU

Esse projeto deve ser usado como processador da saida gerada pelo DOUDownloader (https://github.com/rafaelhss/DouDownloader).


## CouchDB
Essa solução armazena as conexoes no banco de dados couchDB. Portanto é necessario que ele seja instalado em sua maquina. A instalação padrao disponivel em [http://couchdb.apache.org/#download] é o bastante.



## Executando rapidamente

A solucao tem um consumo de memória intenso. Para minimizar os efeitos disso uma estratégia é fracionar os arquivos de entrada em porções menores.
Assim, temos dois executaveis. Um deles fraciona em arquivos menores e outro processa esses arquivos. Embora recomendado, o fracionamento dos arquivos é opcional.
Os fragmentos sao gerados de tal forma que nao quebram uma portaria ao meio. ha a garantia de que uma portaria estara sempre em apenas um fragmento.


A pasta 'Executavel' na raiz ja contem os arquivos jar gerados a partir do projeto. Nela tambem voce encontra os arquivos 'Executar.bat' que invoca os jars adequadamente para gerar fragmentos e processar os fragmentos gerados.

Edite a linha 5 do arquivo bat colocando o caminho completo ate a pasta txt gerada pelo DouDownloader

Enquanto a geracao de conexoes acontece, voce pode acompanhar a inclusao de documentos no banco pela url http://127.0.0.1:5984/_utils/index.html

Se forem identificadas mais de 10 pessoas na mesma portaria ela sera ignorada. Isso por que é provavel que se trate de apenas uma listagem na qual as pessoas nao tem relação tao proxima. Caso queria considerar esses casos, alttere o ConnectionProducer.java (Se implementar parametrizacao para isso, ficarei feliz em aceitar seu pull request) 
