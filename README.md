# myOauth
Meu piloto aplicação com Oauth

> ### Autenticação
>> Processo de aplicação em nome do usuário - valida se o usuário atual participa do fluxo em questão
>> Protocolo de autenticação - informações úteis sobre o usuário - credencial

> ### Autorização
>> Permissionamento e Segurança

> ### Vazamento de informações
>> Riscos de expor a base de usuários


Usuário tenta acessar recurso sem estar autenticado
App verifica que o usuário não está logado
Envia o usuário para o sistema externo de authn
Usuário envia as credenciais para realizar a autenticação
Servidor de autorização processa a requisição do usuário e realiza a autenticação
Servidor notifica o App que o usuário foi autenticado com sucesso!
Usuário acessa os outros sistemas
    Pois o servidor já validou aquelas credenciais anteriormente

#### Padronização dos passos acima é o OAuth 2.0

Framework que possibilita a uma aplicação terceira obter acesso limitado a um serviço ou recurso HTTP, seja em nome de um proprietário do recurso ou em benefício próprio (RFC 6749).
"Uma ESPECIFICAÇÃO que define um protocolo de delegação que é útil para transmitir decisões de autorização em uma rede de aplicativos e APIs feitos para web."

#### Fluxos (grant types) definidos pelo OAuth 2.0

> Authorization Grant / Authorization Code
> Implicit (não recomendado por questões de segurança e não existe no draft do OAuth 2.1)
> Resource Owner Password Credentials (depreciado pelo guia de boas práticas e não existe no draft do OAuth 2.1)
> Client Credentials

Além da RFC 6749, temos várias outras specs que compõem o ecossistema do OAuth 2.0 e a complementam com detalhes de ela não cobre. Entre as specs conhecidas estão:
 - RFC 6750 (The OAuth 2.0 Authorization Framework: Bearer Token Usage)
 - RFC 6819 (OAuth 2.0 Threat Model and Security Considerations)
 - RFC 7636 (Proof Key for Code Exchange by OAuth Public Clients - substitui o Implicit)
 - RFC 8252 ()

 #### Papéis (roles) definidas no OAuth 2.0

 > Resource Owner: Uma entidade capaz de conceder acesso a um recurso protegido.
 > Resource Server: Hospedeiro de recursos protegidos.
 > Client: Aplicaçao que requisita recursos protegidos.
 > Authorization Server: servidor do access token para acessar o Resource Server.

 #### Tipos de Client OAuth 2.0

 > Condidencial e inconfidencial


#### JWT

> "JSON Web Token é um meio compacto de representar afirmações (claims) que serão transferidas entre duas partes".
> RFC 7519
> JSON
> Assinado digitalmente, o que o torna verificável e confiável. Pode ser assinado com um segredo HMAC, chaves RSA, etc.
> Estrutura
>> Cabeçalho.Corpo.Assinatura
>>> Cabeçalho: JOSE Header (RFC 7515 - seção 4)
>>> Corpo: payload (RFC 7519 - seção 4) - iss, sub, aud, exp, etc..
>>> Assinatura: signature (RFC 7515)
>> Tudo em base64

#### JOSE

> Javascript Object Signing and Encryption
>> Suíte, ou conjunto, de especificações com aspectos de segurança:
>>> JWS - assinatura de dados em JSON
>>> JWE - criptografia de conteúdo de dados em JSON
>>>

#### OpenID Connect 1.0 (OIDC)

> Extensão do OAuth - camada de identidade
> /userinfo
> OIDC - especificação que padroniza a obtenção e representação dos dados da identidade do usuário
> id_token - token fornecido por uma aplicação para representar informações complementares do usuário (login facebook, google, open-banking, etc.)

#### Fluxos OpenID Connect

> Authorization Code Flow
> Implicit Flow
> Hybrid Flow

### OAuth 2.1

Especificações adicionais + recomendações 

> Security BCP
> PPKCE obrigatório
> Device Grant
> etc.

