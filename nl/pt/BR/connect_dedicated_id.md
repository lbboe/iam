---



copyright:

  years: 2015，2018

lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Conectando um ID dedicado ao seu IBMid público
{: #connect_dedicated_id}

Para efetuar login em uma nuvem dedicada na qual o serviço IAM público está disponível, a CLI do {{site.data.keyword.Bluemix_notm}} solicita que você efetue login com seu IBMid público em vez do ID dedicado.
{:shortdesc}

```
  $ ibmcloud login -a https://api.{dedicated_env}.bluemix.net
  Terminal da API: https://api.{dedicated_env}.bluemix.net

  O serviço de token público do IAM está disponível no ambiente dedicado.
  Efetue login com seu IBMid público ou use '--no-iam' para efetuar login somente como um usuário dedicado.

  E-mail>
```

Se seu ID dedicado já foi conectado ao IBMid público, ele autenticará e efetuará login:

```
  Authenticating...
  OK

  Conectado ao usuário dedicado my_dedicated_id
```

No entanto, se seu ID dedicado não foi conectado ao IBMid público, você será solicitado a conectar-se manualmente com o IBMid público:

```
  Você está efetuando login com um IBMid que não está associado a nenhum usuário dedicado.
  To set up the connection, input the credentials of the dedicated user.

  Escolha um tipo de credencial:
  1. Nome do usuário e senha
  2. Um código de tempo (obtenha um em https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

Selecione uma opção para inserir as credenciais para o ID dedicado. Após a autenticação bem-sucedida, seu ID dedicado será conectado a seu IBMid público.

## Forçar o login no servidor UAA local

Para forçar a criação de log para o servidor do UAA com um ID dedicado, especifique a opção `--no-iam` no comando `ibmcloud login`:

```
  $ ibmcloud login --no-iam
```

## Desconectar seu ID dedicado do IBMid público 

É possível usar `ibmcloud iam dedicated-id-disconnect` para desconectar o IBMid público com o ID dedicado conectado.

```
  $ ibmcloud iam dedicated-id-disconnect Você realmente deseja desconectar my_dedicated_id do IBMid público? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```
