É possível comprovar que os jobs testes-unitarios e scan-de-seguranca rodaram em paralelo pois, durante a execução do pipeline, os logs aparecem de forma intercalada no terminal. Além disso, cada job é executado em um container separado, identificado pelo nome do job entre colchetes, como [testes-unitarios] e [scan-de-seguranca], demonstrando execução simultânea.
gamahtur@Tininha:~/meu-projeto-ci$ sudo act -l
INFO[0000] Using docker host 'unix:///var/run/docker.sock', and daemon socket 'unix:///var/run/docker.sock'
Stage  Job ID             Job name           Workflow name       Workflow file              Events
0      teste-basico       teste-basico       Hello Local         01-hello-local.yml         workflow_dispatch,push
0      setup-e-lint       setup-e-lint       Pipeline Principal  02-pipeline-principal.yml  push
1      scan-de-seguranca  scan-de-seguranca  Pipeline Principal  02-pipeline-principal.yml  push
1      testes-unitarios   testes-unitarios   Pipeline Principal  02-pipeline-principal.yml  push
2      build-e-deploy     build-e-deploy     Pipeline Principal  02-pipeline-principal.yml  push
