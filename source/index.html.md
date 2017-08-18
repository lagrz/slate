---
title: 'WireCash API'
language_tabs:
  - shell: Shell
  - http: HTTP  
  - javascript--nodejs: Node.JS
  - python: Python
  - ruby: Ruby
  - java: Java
  - csharp: C#
toc_footers: []
includes:
  - authentication
  - api/authenticate
  - api/token
  - resources
  - api/company_id
  - api/country_code
  - api/country_list
  - api/state_code
  - api/state_code_country_code
  - api/state_list
  - schemas
  - schemas/AuthenticateRequest
  - schemas/AuthenticateResponse
  - schemas/RefreshTokenRequest
  - schemas/CompaniesResponse
  - schemas/CountryListResponse
  - schemas/StateListResponse
  - schemas/Company
  - schemas/ExchangeRate  
  - schemas/NameCode
  - schemas/Payer  
  - schemas/Service
search: true
highlight_theme: darkula
---

# WireCash API

> Scroll down for example requests and responses.

The WireCash API provides Services from our partners with fees, rates. Searchable by US state of origin, country remitting to, or both. See the various API resources for more information.

In order to obtain a username and password for API use you must contact us at [tech@wirecash.com](mailto:tech@wirecash.com)

Base URLs:

* <a href="https://api.wirecash.com/sandbox">https://api.wirecash.com/sandbox</a>
* <a href="https://api.wirecash.com/production">https://api.wirecash.com/production</a>
