---
title: Rebill - API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - ruby
  - python
  - php
  - go

toc_footers:
  - <a target="_blank" href="https://docs.rebill.to/resources/postman/Rebill.postman_collection.json">Download Postman Collection</a>
  - <a target="_blank" href="https://docs.rebill.to/resources/postman/Rebill.postman_environment.json">Download Postman Environment</a>
  - <br><a href='mailto:developers@rebill.to?subject=Assistance Request'>Request Assistance</a>

includes:
  - authentication
  - cards
  - customers
  - notifications
  - organizations
  - payments
  - plans
  - products
  - recipients
  - regions
  - roles
  - subscriptions
  - vat
  - users
  - vendors
  - webhooks
  - checkout_landing
  - checkout_express
  - errors

search: true

code_clipboard: true
---

# Introduction

<div class="right-block">
  <h1>Just getting started?</h1>
  <p>Check out our <a href="https://support.rebill.to" target="_blank" rel="noopener noreferrer" class="docs-link">development quickstart</a> guide.</p>
</div>

<div class="right-block">
  <h1>NOT A DEVELOPER?</h1>
  <p>Use apps or get a quote from <a href="https://support.rebill.to" target="_blank" rel="noopener noreferrer" class="docs-link">our partners</a> to get started with Rebill. You may also <a href="mailto:support@rebill.to"> contact us</a> to get personalized assistance.</p>
</div>

<blockquote class="plaintext">
<p>BASE URL</p>
</blockquote>
<div class="highlight">
  <pre class="highlight plaintext endpoints" style="">
  https://api.rebill.to/v1/
  </pre>
</div>

Welcome to the Rebill API. You can use our API to access Rebill API endpoints, which can get information on customers, cards, subscriptions, plans, and more. Also, you can process payments through any of your connected payment gateways.

We have language bindings in Curl, Ruby, Python, and Javascript. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

Rebill uses a token Bearer to allow access to the API. You can access to the APIs using your own personal account, and asking for special access to the other functionalities [by email](mailto:support@rebill.to).

Looking for any specific Endpoint? Write us with your request to [support@rebill.to](mailto:support@rebill.to).

<blockquote class="plaintext light">
<p>ENDPOINTS</p>
</blockquote>
<div class="highlight light">
  <pre class="highlight plaintext light endpoints" style="">
    <a href="#"><div class="method"><span class="get">GET</span></div><div class="endpoint">/auth/:id</div></a>
    <a href="#"><div class="method"><span class="post">POST</span></div><div class="endpoint">/auth/:id</div></a>
    <a href="#"><div class="method"><span class="put">PUT</span></div><div class="endpoint">/auth/:id</div></a>
    <a href="#"><div class="method"><span class="delete">DELETE</span></div><div class="endpoint">/auth/:id</div></a>
  </pre>
</div>