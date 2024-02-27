# Trabalhando com Machine Learning na Prática no Azure ML

## Passos para criar um modelo de previsão

Passos realizados conforme descrito em: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html

Após a criação de um workspaçe dentro do estúdio do azure, é necessário clicar em 'ML automatizado' e  depois em '+ Novo trabalho de ML automatizado':

<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem1.png?raw=true" width="" /> 

&nbsp;

Após preencher os dados conforme imagem abaixo, clicar em avançar:


<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem2.png?raw=true" width=""/> 
&nbsp;

Selecionar regressão no tipo de tarefa e clicar no botão azul 'Criar'.

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem3.png?raw=true" width=""/> 

&nbsp;

Após, será aberto um menu onde deve-se ser preenchido o nome e o ativo de dados.
Após preenchimento, clicar em avançar:

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem4.png?raw=true" width=""/> 

&nbsp;

A fonte de dados deve ser 'De arquivos da Web":

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem5.png?raw=true" width=""/> 

&nbsp;

A URL da WEB é preenchida com "https://aka.ms/bike-rentals

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem6.png?raw=true" width=""/> 

&nbsp;

As configurações do ativo de dados devem ser preenchidas conforme a imagem abaixo:

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem7.png?raw=true" width=""/> 

&nbsp;

No Esquema, devem ser selecionadas todas as linhas, menos 'Path':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem8.png?raw=true" width=""/> 

&nbsp;

Após as configurações, basta clicar em 'Criar':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem9.png?raw=true" width=""/>


&nbsp;

Após a criação, é necessário selecionar 'bike-rentals' e clicar no botão 'Avançar':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem10.png?raw=true" width=""/>

&nbsp;

Em Configurações de tarefas, preencher conforme a imagem abaixo:

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem11.png?raw=true" width=""/>

&nbsp;

Ainda em Configurações de tarefas, deve-se clicar em 'Exibir definições de configurações adicionais' e preencher conforme imagem abaixo. Depois clicar em 'Salvar':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem12.png?raw=true" width=""/>

&nbsp;

Continuando em Configurações de tarefas, clicar em 'Limites' e nas opções que surgirem, preencher conforme abaixo. Após, clicar em 'Avançar':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem13.png?raw=true" width=""/>

&nbsp;

Em Computação, preencher conforme a imagem abaixo e clicar em 'Avançar':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem14.png?raw=true" width=""/>

&nbsp;

Apenas clicar em 'Enviar trabalho de treinamento".

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem15.png?raw=true" width=""/>

&nbsp;

Agora o trabalho começará sua inicialização, podendo demorar em torno de 10 minutos:

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem16.png?raw=true" width=""/>

&nbsp;

Abaixo, imagem demonstrando o trabalho após a finalização de sua inicialização. Nessa tela, devemos clicar em 'mslearn-bike-rental':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem17.png?raw=true" width=""/>

&nbsp;

Nos nomes de exibição, devemos selecionar o que estiver com a marcação 'Melhor', clicando no nome:

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem18.png?raw=true" width=""/>


&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem19.png?raw=true" width=""/>

&nbsp;

Na visão geral que é carregada, devemos clicar em 'Implantar' e escolher 'Serviço Web':

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem20.png?raw=true" width=""/>

&nbsp;

Após o tempo de inicialização do serviço, devemos clicar em Pontos de Extremidade no menu lateral esquerdo e selecionar o modelo que criamos anteriormente. Dentro do Ponto de Extremidade, clicamos na aba 'Testar' e passamos o seguinte json:

``` JASON
{
  "input_data": {
    "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]
  }
}
```

Após clicar no botão 'Testar' o resultado do teste é retornado, conforme imagem abaixo, sendo a previsão geral 359.77.

&nbsp;
<img align="right" src="https://github.com/pvtoledo/pvtoledo-lab-azure-mlearning/blob/main/imgs/imagem21.png?raw=true" width=""/>