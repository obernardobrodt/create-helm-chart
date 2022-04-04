# create-helm-chart
How to create helm chart ? Let´s my guys

# Requeriments
kubernetes
Helm
VScode (Opcional)

# Commands

Criando nosso Chart

` helm create template-chart `


Verificando se está tudo Ok
` helm create template-chart `

Criando nosso pacote de arquivo atráves do nosso chart, somente se tivermos isso poderemos instalar ele
` helm package .\template-chart\ `


instalando ele, como podemos ver isso atraves do pacote que criamos, estamos instalando apontando para a namespace correta
`helm install template-chart .\template-chart-0.1.0.tgz -n helm `

Voce deve receber a seguinte mensagem: 

Release "template-chart" has been upgraded. Happy Helming!
NAME: template-chart
LAST DEPLOYED: Mon Apr  4 15:07:55 2022
NAMESPACE: helm
STATUS: deployed
REVISION: 1
NOTES:

verifique se está tudo rodando corretamente
` kubectl get po $(minha-namespace)`

* como atualizar? Você pode atualizar qualquer campo da sua Chart,  value.yaml, templates e afins.
porem após atualizar vc pode criar um novo pack com uma nova versão ou atualizar o que tem com o seguinte comando

` helm package .\template-chart\`


E para refletir em seu cluster? É mais simples ainda, segue:

` helm upgrade template-chart .\template-chart-0.1.0.tgz -n helm`

