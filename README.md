1.	Deploy an application

	Project nodejs-project is a node js application. 
	Source code is available on https://github.com/leandroppereira/DO180-apps/tree/master/nodejs-helloworld
	It uses as library dependencies this repository https://registry.npmmirror.com/
Application must show a valid response on this URL http://nodejs-hello-nodejs-project.[WILDCARD-DOMAIN]/  

Passos para a reprodução do cenário:

oc new-project nodejs-project

oc new-app  --context-dir=nodejs-helloworld https://github.com/leandroppereira/desafio1 -i nodejs:14-ubi7 --name nodejs-hello --build-env npm_config_registry=https://registry.npmmirror.com/oc get all

Observação: Não utilize esse repositório. Para reproduzir, crie um repositório público com o mesmo conteúdo e utilize.

oc expose service/nodejs-hello
oc get builds
oc logs -f buildconfig/nodejs-hello

Será apresentado um build com erro
