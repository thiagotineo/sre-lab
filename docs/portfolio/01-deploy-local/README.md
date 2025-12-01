Durante o primeiro teste de execução, o Docker Compose exibiu dois avisos importantes:

1. MYSQL_ROOT_PASSWORD não definido

O MySQL subiria sem senha root.

Criei um arquivo .env no diretório do compose e defini MYSQL_ROOT_PASSWORD=mysq1r00tP@ss.

Após isso, o warning desapareceu.

2. Atributo version obsoleto no compose

O Compose avisou que a chave version: não é mais usada.

Removi a linha version: "3.x" do docker-compose.yml.

O arquivo passou a seguir o padrão atual da Compose Specification.

Essas correções evitaram problemas de segurança, compatibilidade e usabilidade ao seguir com o deploy local.
