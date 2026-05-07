---
categories: []
consumed_apis: []
description: APIs for authentication methods in HashiCorp Vault including Token, AppRole, Kubernetes, LDAP, JWT/OIDC, GitHub, Userpass, and AWS auth methods. These endpoints handle user and machine authentication to obtain Vault tokens.
layout: capability
name: HashiCorp Vault Vault Auth Methods API
operations:
- description: HashiCorp Vault Create token
  method: POST
  name: createtoken
  path: /auth/token/create
- description: HashiCorp Vault Create orphan token
  method: POST
  name: createorphantoken
  path: /auth/token/create-orphan
- description: HashiCorp Vault Create token with role
  method: POST
  name: createtokenwithrole
  path: /auth/token/create/{role_name}
- description: HashiCorp Vault Lookup token
  method: POST
  name: lookuptoken
  path: /auth/token/lookup
- description: HashiCorp Vault Lookup self token
  method: GET
  name: lookupselftoken
  path: /auth/token/lookup-self
- description: HashiCorp Vault Renew token
  method: POST
  name: renewtoken
  path: /auth/token/renew
- description: HashiCorp Vault Renew self token
  method: POST
  name: renewselftoken
  path: /auth/token/renew-self
- description: HashiCorp Vault Revoke token
  method: POST
  name: revoketoken
  path: /auth/token/revoke
- description: HashiCorp Vault Revoke self token
  method: POST
  name: revokeselftoken
  path: /auth/token/revoke-self
- description: HashiCorp Vault Read token role
  method: GET
  name: readtokenrole
  path: /auth/token/roles/{role_name}
- description: HashiCorp Vault Create or update token role
  method: POST
  name: createorupdatetokenrole
  path: /auth/token/roles/{role_name}
- description: HashiCorp Vault Delete token role
  method: DELETE
  name: deletetokenrole
  path: /auth/token/roles/{role_name}
- description: HashiCorp Vault Login with AppRole
  method: POST
  name: loginwithapprole
  path: /auth/approle/login
- description: HashiCorp Vault Read AppRole
  method: GET
  name: readapprole
  path: /auth/approle/role/{role_name}
- description: HashiCorp Vault Create or update AppRole
  method: POST
  name: createorupdateapprole
  path: /auth/approle/role/{role_name}
- description: HashiCorp Vault Delete AppRole
  method: DELETE
  name: deleteapprole
  path: /auth/approle/role/{role_name}
- description: HashiCorp Vault Read AppRole role ID
  method: GET
  name: readapproleroleid
  path: /auth/approle/role/{role_name}/role-id
- description: HashiCorp Vault Generate AppRole secret ID
  method: POST
  name: generateapprolesecretid
  path: /auth/approle/role/{role_name}/secret-id
- description: HashiCorp Vault Login with Kubernetes
  method: POST
  name: loginwithkubernetes
  path: /auth/kubernetes/login
- description: HashiCorp Vault Read Kubernetes auth configuration
  method: GET
  name: readkubernetesconfig
  path: /auth/kubernetes/config
- description: HashiCorp Vault Configure Kubernetes auth
  method: POST
  name: configurekubernetesauth
  path: /auth/kubernetes/config
- description: HashiCorp Vault Read Kubernetes role
  method: GET
  name: readkubernetesrole
  path: /auth/kubernetes/role/{name}
- description: HashiCorp Vault Create or update Kubernetes role
  method: POST
  name: createorupdatekubernetesrole
  path: /auth/kubernetes/role/{name}
- description: HashiCorp Vault Delete Kubernetes role
  method: DELETE
  name: deletekubernetesrole
  path: /auth/kubernetes/role/{name}
- description: HashiCorp Vault Login with LDAP
  method: POST
  name: loginwithldap
  path: /auth/ldap/login/{username}
- description: HashiCorp Vault Login with JWT/OIDC
  method: POST
  name: loginwithjwt
  path: /auth/jwt/login
- description: HashiCorp Vault Login with username and password
  method: POST
  name: loginwithuserpass
  path: /auth/userpass/login/{username}
- description: HashiCorp Vault Read userpass user
  method: GET
  name: readuserpassuser
  path: /auth/userpass/users/{username}
- description: HashiCorp Vault Create or update userpass user
  method: POST
  name: createorupdateuserpassuser
  path: /auth/userpass/users/{username}
- description: HashiCorp Vault Delete userpass user
  method: DELETE
  name: deleteuserpassuser
  path: /auth/userpass/users/{username}
- description: HashiCorp Vault Login with GitHub
  method: POST
  name: loginwithgithub
  path: /auth/github/login
personas: []
provider_name: HashiCorp Vault
provider_slug: hvault
search_terms:
- hashicorp vault login with kubernetes
- createorphantoken
- hashicorp vault create or update approle
- hashicorp vault create or update kubernetes role
- hashicorp vault create orphan token
- loginwithkubernetes
- hashicorp vault create token
- loginwithjwt
- readkubernetesconfig
- readuserpassuser
- createtokenwithrole
- hashicorp vault lookup token
- hashicorp vault login with approle
- hashicorp vault read approle role id
- hashicorp vault delete approle
- hashicorp vault renew token
- api
- lookupselftoken
- hashicorp vault configure kubernetes auth
- hashicorp vault lookup self token
- configurekubernetesauth
- deletetokenrole
- hashicorp vault login with ldap
- secrets management
- createtoken
- hashicorp vault renew self token
- hashicorp vault read kubernetes role
- hashicorp vault read userpass user
- hashicorp vault revoke token
- hashicorp vault delete userpass user
- deleteapprole
- hashicorp vault delete kubernetes role
- encryption
- hvault
- revokeselftoken
- loginwithgithub
- hashicorp vault login with github
- readtokenrole
- loginwithuserpass
- identity
- infrastructure
- readapprole
- hashicorp vault read token role
- hashicorp vault create or update userpass user
- hashicorp vault read approle
- loginwithapprole
- createorupdateuserpassuser
- revoketoken
- hashicorp vault delete token role
- generateapprolesecretid
- createorupdateapprole
- renewtoken
- deleteuserpassuser
- renewselftoken
- readkubernetesrole
- createorupdatekubernetesrole
- hashicorp vault generate approle secret id
- hashicorp vault read kubernetes auth configuration
- hashicorp vault login with jwt/oidc
- createorupdatetokenrole
- deletekubernetesrole
- hashicorp vault create or update token role
- readapproleroleid
- hashicorp vault create token with role
- lookuptoken
- loginwithldap
- hashicorp vault login with username and password
- security
- hashicorp vault revoke self token
slug: hvault-capability
source_filename: hvault-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Vault Vault Auth Methods API\n  description: APIs for authentication methods in HashiCorp Vault including Token, AppRole, Kubernetes, LDAP, JWT/OIDC, GitHub,\n    Userpass, and AWS auth methods. These endpoints handle user and machine authentication to obtain Vault tokens.\n  tags:\n  - Hvault\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hvault\n    baseUri: https://vault.example.com/v1\n    description: HashiCorp Vault Vault Auth Methods API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Vault-Token\n      value: '{{HVAULT_TOKEN}}'\n    resources:\n    - name: auth-token-create\n      path: /auth/token/create\n      operations:\n      - name: createtoken\n        method: POST\n        description: HashiCorp Vault Create token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: auth-token-create-orphan\n      path: /auth/token/create-orphan\n      operations:\n      - name: createorphantoken\n        method: POST\n        description: HashiCorp Vault Create orphan token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-create-role-name\n      path: /auth/token/create/{role_name}\n      operations:\n      - name: createtokenwithrole\n        method: POST\n        description: HashiCorp Vault Create token with role\n        inputParameters:\n        - name: role_name\n          in: path\n          type: string\n          required: true\n          description: Name of the token role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup\n      path: /auth/token/lookup\n      operations:\n      - name: lookuptoken\n\
  \        method: POST\n        description: HashiCorp Vault Lookup token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup-self\n      path: /auth/token/lookup-self\n      operations:\n      - name: lookupselftoken\n        method: GET\n        description: HashiCorp Vault Lookup self token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew\n      path: /auth/token/renew\n      operations:\n      - name: renewtoken\n        method: POST\n        description: HashiCorp Vault Renew token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew-self\n      path: /auth/token/renew-self\n      operations:\n      - name: renewselftoken\n        method: POST\n        description: HashiCorp\
  \ Vault Renew self token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke\n      path: /auth/token/revoke\n      operations:\n      - name: revoketoken\n        method: POST\n        description: HashiCorp Vault Revoke token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke-self\n      path: /auth/token/revoke-self\n      operations:\n      - name: revokeselftoken\n        method: POST\n        description: HashiCorp Vault Revoke self token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-roles-role-name\n      path: /auth/token/roles/{role_name}\n      operations:\n      - name: readtokenrole\n        method: GET\n        description: HashiCorp Vault Read token role\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdatetokenrole\n        method: POST\n        description: HashiCorp Vault Create or update token role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetokenrole\n        method: DELETE\n        description: HashiCorp Vault Delete token role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-approle-login\n      path: /auth/approle/login\n      operations:\n      - name: loginwithapprole\n        method: POST\n        description: HashiCorp Vault Login with AppRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-approle-role-role-name\n      path: /auth/approle/role/{role_name}\n\
  \      operations:\n      - name: readapprole\n        method: GET\n        description: HashiCorp Vault Read AppRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdateapprole\n        method: POST\n        description: HashiCorp Vault Create or update AppRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapprole\n        method: DELETE\n        description: HashiCorp Vault Delete AppRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-approle-role-role-name-role-id\n      path: /auth/approle/role/{role_name}/role-id\n      operations:\n      - name: readapproleroleid\n        method: GET\n        description: HashiCorp Vault Read AppRole role ID\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-approle-role-role-name-secret-id\n      path: /auth/approle/role/{role_name}/secret-id\n      operations:\n      - name: generateapprolesecretid\n        method: POST\n        description: HashiCorp Vault Generate AppRole secret ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-kubernetes-login\n      path: /auth/kubernetes/login\n      operations:\n      - name: loginwithkubernetes\n        method: POST\n        description: HashiCorp Vault Login with Kubernetes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-kubernetes-config\n      path: /auth/kubernetes/config\n      operations:\n      - name: readkubernetesconfig\n        method: GET\n        description: HashiCorp Vault Read Kubernetes\
  \ auth configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: configurekubernetesauth\n        method: POST\n        description: HashiCorp Vault Configure Kubernetes auth\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-kubernetes-role-name\n      path: /auth/kubernetes/role/{name}\n      operations:\n      - name: readkubernetesrole\n        method: GET\n        description: HashiCorp Vault Read Kubernetes role\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdatekubernetesrole\n        method: POST\n        description: HashiCorp Vault\
  \ Create or update Kubernetes role\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletekubernetesrole\n        method: DELETE\n        description: HashiCorp Vault Delete Kubernetes role\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-ldap-login-username\n      path: /auth/ldap/login/{username}\n      operations:\n      - name: loginwithldap\n        method: POST\n        description: HashiCorp Vault Login with LDAP\n        inputParameters:\n        - name: username\n          in: path\n\
  \          type: string\n          required: true\n          description: LDAP username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-login\n      path: /auth/jwt/login\n      operations:\n      - name: loginwithjwt\n        method: POST\n        description: HashiCorp Vault Login with JWT/OIDC\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-userpass-login-username\n      path: /auth/userpass/login/{username}\n      operations:\n      - name: loginwithuserpass\n        method: POST\n        description: HashiCorp Vault Login with username and password\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n    - name: auth-userpass-users-username\n      path: /auth/userpass/users/{username}\n      operations:\n      - name: readuserpassuser\n        method: GET\n        description: HashiCorp Vault Read userpass user\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdateuserpassuser\n        method: POST\n        description: HashiCorp Vault Create or update userpass user\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserpassuser\n        method:\
  \ DELETE\n        description: HashiCorp Vault Delete userpass user\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-github-login\n      path: /auth/github/login\n      operations:\n      - name: loginwithgithub\n        method: POST\n        description: HashiCorp Vault Login with GitHub\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hvault-rest\n    description: REST adapter for HashiCorp Vault Vault Auth Methods API.\n    resources:\n    - path: /auth/token/create\n      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n        description: HashiCorp Vault Create\
  \ token\n        call: hvault.createtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create-orphan\n      name: createorphantoken\n      operations:\n      - method: POST\n        name: createorphantoken\n        description: HashiCorp Vault Create orphan token\n        call: hvault.createorphantoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create/{role_name}\n      name: createtokenwithrole\n      operations:\n      - method: POST\n        name: createtokenwithrole\n        description: HashiCorp Vault Create token with role\n        call: hvault.createtokenwithrole\n        with:\n          role_name: rest.role_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup\n      name: lookuptoken\n      operations:\n      - method: POST\n        name: lookuptoken\n        description: HashiCorp Vault Lookup token\n        call:\
  \ hvault.lookuptoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup-self\n      name: lookupselftoken\n      operations:\n      - method: GET\n        name: lookupselftoken\n        description: HashiCorp Vault Lookup self token\n        call: hvault.lookupselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/renew\n      name: renewtoken\n      operations:\n      - method: POST\n        name: renewtoken\n        description: HashiCorp Vault Renew token\n        call: hvault.renewtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/renew-self\n      name: renewselftoken\n      operations:\n      - method: POST\n        name: renewselftoken\n        description: HashiCorp Vault Renew self token\n        call: hvault.renewselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke\n\
  \      name: revoketoken\n      operations:\n      - method: POST\n        name: revoketoken\n        description: HashiCorp Vault Revoke token\n        call: hvault.revoketoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke-self\n      name: revokeselftoken\n      operations:\n      - method: POST\n        name: revokeselftoken\n        description: HashiCorp Vault Revoke self token\n        call: hvault.revokeselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: readtokenrole\n      operations:\n      - method: GET\n        name: readtokenrole\n        description: HashiCorp Vault Read token role\n        call: hvault.readtokenrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: createorupdatetokenrole\n      operations:\n      - method: POST\n        name: createorupdatetokenrole\n\
  \        description: HashiCorp Vault Create or update token role\n        call: hvault.createorupdatetokenrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: deletetokenrole\n      operations:\n      - method: DELETE\n        name: deletetokenrole\n        description: HashiCorp Vault Delete token role\n        call: hvault.deletetokenrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/login\n      name: loginwithapprole\n      operations:\n      - method: POST\n        name: loginwithapprole\n        description: HashiCorp Vault Login with AppRole\n        call: hvault.loginwithapprole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/role/{role_name}\n      name: readapprole\n      operations:\n      - method: GET\n        name: readapprole\n        description: HashiCorp Vault Read AppRole\n     \
  \   call: hvault.readapprole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/role/{role_name}\n      name: createorupdateapprole\n      operations:\n      - method: POST\n        name: createorupdateapprole\n        description: HashiCorp Vault Create or update AppRole\n        call: hvault.createorupdateapprole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/role/{role_name}\n      name: deleteapprole\n      operations:\n      - method: DELETE\n        name: deleteapprole\n        description: HashiCorp Vault Delete AppRole\n        call: hvault.deleteapprole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/role/{role_name}/role-id\n      name: readapproleroleid\n      operations:\n      - method: GET\n        name: readapproleroleid\n        description: HashiCorp Vault Read AppRole role ID\n        call: hvault.readapproleroleid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/role/{role_name}/secret-id\n      name: generateapprolesecretid\n      operations:\n      - method: POST\n        name: generateapprolesecretid\n        description: HashiCorp Vault Generate AppRole secret ID\n        call: hvault.generateapprolesecretid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/login\n      name: loginwithkubernetes\n      operations:\n      - method: POST\n        name: loginwithkubernetes\n        description: HashiCorp Vault Login with Kubernetes\n        call: hvault.loginwithkubernetes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/config\n      name: readkubernetesconfig\n      operations:\n      - method: GET\n        name: readkubernetesconfig\n        description: HashiCorp Vault Read Kubernetes auth configuration\n        call: hvault.readkubernetesconfig\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/config\n      name: configurekubernetesauth\n      operations:\n      - method: POST\n        name: configurekubernetesauth\n        description: HashiCorp Vault Configure Kubernetes auth\n        call: hvault.configurekubernetesauth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/role/{name}\n      name: readkubernetesrole\n      operations:\n      - method: GET\n        name: readkubernetesrole\n        description: HashiCorp Vault Read Kubernetes role\n        call: hvault.readkubernetesrole\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/role/{name}\n      name: createorupdatekubernetesrole\n      operations:\n      - method: POST\n        name: createorupdatekubernetesrole\n        description: HashiCorp Vault Create or update\
  \ Kubernetes role\n        call: hvault.createorupdatekubernetesrole\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/kubernetes/role/{name}\n      name: deletekubernetesrole\n      operations:\n      - method: DELETE\n        name: deletekubernetesrole\n        description: HashiCorp Vault Delete Kubernetes role\n        call: hvault.deletekubernetesrole\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/ldap/login/{username}\n      name: loginwithldap\n      operations:\n      - method: POST\n        name: loginwithldap\n        description: HashiCorp Vault Login with LDAP\n        call: hvault.loginwithldap\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/login\n      name: loginwithjwt\n      operations:\n      - method:\
  \ POST\n        name: loginwithjwt\n        description: HashiCorp Vault Login with JWT/OIDC\n        call: hvault.loginwithjwt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/userpass/login/{username}\n      name: loginwithuserpass\n      operations:\n      - method: POST\n        name: loginwithuserpass\n        description: HashiCorp Vault Login with username and password\n        call: hvault.loginwithuserpass\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/userpass/users/{username}\n      name: readuserpassuser\n      operations:\n      - method: GET\n        name: readuserpassuser\n        description: HashiCorp Vault Read userpass user\n        call: hvault.readuserpassuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/userpass/users/{username}\n\
  \      name: createorupdateuserpassuser\n      operations:\n      - method: POST\n        name: createorupdateuserpassuser\n        description: HashiCorp Vault Create or update userpass user\n        call: hvault.createorupdateuserpassuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/userpass/users/{username}\n      name: deleteuserpassuser\n      operations:\n      - method: DELETE\n        name: deleteuserpassuser\n        description: HashiCorp Vault Delete userpass user\n        call: hvault.deleteuserpassuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/github/login\n      name: loginwithgithub\n      operations:\n      - method: POST\n        name: loginwithgithub\n        description: HashiCorp Vault Login with GitHub\n        call: hvault.loginwithgithub\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hvault-mcp\n    transport: http\n    description: MCP adapter for HashiCorp Vault Vault Auth Methods API for AI agent use.\n    tools:\n    - name: createtoken\n      description: HashiCorp Vault Create token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorphantoken\n      description: HashiCorp Vault Create orphan token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createorphantoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtokenwithrole\n      description: HashiCorp Vault Create token with role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createtokenwithrole\n\
  \      with:\n        role_name: tools.role_name\n      inputParameters:\n      - name: role_name\n        type: string\n        description: Name of the token role\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookuptoken\n      description: HashiCorp Vault Lookup token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.lookuptoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookupselftoken\n      description: HashiCorp Vault Lookup self token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hvault.lookupselftoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewtoken\n      description: HashiCorp Vault Renew token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.renewtoken\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewselftoken\n      description: HashiCorp Vault Renew self token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.renewselftoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoketoken\n      description: HashiCorp Vault Revoke token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.revoketoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeselftoken\n      description: HashiCorp Vault Revoke self token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.revokeselftoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readtokenrole\n      description: HashiCorp Vault Read token role\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: hvault.readtokenrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdatetokenrole\n      description: HashiCorp Vault Create or update token role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createorupdatetokenrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetokenrole\n      description: HashiCorp Vault Delete token role\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hvault.deletetokenrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithapprole\n      description: HashiCorp Vault Login with AppRole\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithapprole\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: readapprole\n      description: HashiCorp Vault Read AppRole\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hvault.readapprole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdateapprole\n      description: HashiCorp Vault Create or update AppRole\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createorupdateapprole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapprole\n      description: HashiCorp Vault Delete AppRole\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hvault.deleteapprole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readapproleroleid\n      description: HashiCorp Vault Read AppRole role ID\n      hints:\n        readOnly: true\n    \
  \    destructive: false\n        idempotent: true\n      call: hvault.readapproleroleid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateapprolesecretid\n      description: HashiCorp Vault Generate AppRole secret ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.generateapprolesecretid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithkubernetes\n      description: HashiCorp Vault Login with Kubernetes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithkubernetes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readkubernetesconfig\n      description: HashiCorp Vault Read Kubernetes auth configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hvault.readkubernetesconfig\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: configurekubernetesauth\n      description: HashiCorp Vault Configure Kubernetes auth\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.configurekubernetesauth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readkubernetesrole\n      description: HashiCorp Vault Read Kubernetes role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hvault.readkubernetesrole\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the role\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdatekubernetesrole\n      description: HashiCorp Vault Create or update Kubernetes role\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: hvault.createorupdatekubernetesrole\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the role\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletekubernetesrole\n      description: HashiCorp Vault Delete Kubernetes role\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hvault.deletekubernetesrole\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the role\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithldap\n      description: HashiCorp Vault Login with LDAP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithldap\n      with:\n    \
  \    username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: LDAP username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithjwt\n      description: HashiCorp Vault Login with JWT/OIDC\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithjwt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithuserpass\n      description: HashiCorp Vault Login with username and password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithuserpass\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readuserpassuser\n\
  \      description: HashiCorp Vault Read userpass user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hvault.readuserpassuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdateuserpassuser\n      description: HashiCorp Vault Create or update userpass user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.createorupdateuserpassuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuserpassuser\n      description: HashiCorp Vault Delete userpass user\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hvault.deleteuserpassuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loginwithgithub\n      description: HashiCorp Vault Login with GitHub\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hvault.loginwithgithub\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HVAULT_TOKEN: HVAULT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hvault/refs/heads/main/capabilities/hvault-capability.yaml
tags:
- Hvault
- API
tools:
- description: HashiCorp Vault Create token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: HashiCorp Vault Create orphan token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorphantoken
- description: HashiCorp Vault Create token with role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtokenwithrole
- description: HashiCorp Vault Lookup token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lookuptoken
- description: HashiCorp Vault Lookup self token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookupselftoken
- description: HashiCorp Vault Renew token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewtoken
- description: HashiCorp Vault Renew self token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewselftoken
- description: HashiCorp Vault Revoke token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revoketoken
- description: HashiCorp Vault Revoke self token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeselftoken
- description: HashiCorp Vault Read token role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readtokenrole
- description: HashiCorp Vault Create or update token role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdatetokenrole
- description: HashiCorp Vault Delete token role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetokenrole
- description: HashiCorp Vault Login with AppRole
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithapprole
- description: HashiCorp Vault Read AppRole
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readapprole
- description: HashiCorp Vault Create or update AppRole
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdateapprole
- description: HashiCorp Vault Delete AppRole
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapprole
- description: HashiCorp Vault Read AppRole role ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readapproleroleid
- description: HashiCorp Vault Generate AppRole secret ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateapprolesecretid
- description: HashiCorp Vault Login with Kubernetes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithkubernetes
- description: HashiCorp Vault Read Kubernetes auth configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readkubernetesconfig
- description: HashiCorp Vault Configure Kubernetes auth
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: configurekubernetesauth
- description: HashiCorp Vault Read Kubernetes role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readkubernetesrole
- description: HashiCorp Vault Create or update Kubernetes role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdatekubernetesrole
- description: HashiCorp Vault Delete Kubernetes role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekubernetesrole
- description: HashiCorp Vault Login with LDAP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithldap
- description: HashiCorp Vault Login with JWT/OIDC
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithjwt
- description: HashiCorp Vault Login with username and password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithuserpass
- description: HashiCorp Vault Read userpass user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readuserpassuser
- description: HashiCorp Vault Create or update userpass user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdateuserpassuser
- description: HashiCorp Vault Delete userpass user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserpassuser
- description: HashiCorp Vault Login with GitHub
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwithgithub
---
