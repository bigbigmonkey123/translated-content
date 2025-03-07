---
title: CORS errors
slug: Web/HTTP/CORS/Errors
tags:
  - CORS
  - Errors
  - HTTP
  - HTTPS
  - Messages
  - NeedsTranslation
  - Same-origin
  - Security
  - TopicStub
  - console
  - troubleshooting
translation_of: Web/HTTP/CORS/Errors
---
{{HTTPSidebar}}

[Cross-Origin Resource Sharing](/es/docs/Web/HTTP/CORS) ({{Glossary("CORS")}}) is a standard that allows a server to relax the [same-origin policy](/es/docs/Web/Security/Same-origin_policy). This is used to explicitly allow some cross-origin requests while rejecting others. For example, if a site offers an embeddable service, it may be necessary to relax certain restrictions. Setting up such a CORS configuration isn't necessarily easy and may present some challenges. In these pages, we'll look into some common CORS error messages and how to resolve them.

If the CORS configuration isn't setup correctly, the browser console will present an error like `"Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at $somesite"` indicating that the request was blocked due to violating the CORS security rules. This might not necessarily be a set-up mistake, though. It's possible that the request is in fact intentionally being disallowed by the user's web application and remote external service. However, If the endpoint is meant to be available, some debugging is needed to succeed.

## Identifying the issue

To understand the underlying issue with the CORS configuration, you need to find out which request is at fault and why. These steps may help you do so:

1. Navigate to the web site or web app in question and open the [Developer Tools](/es/docs/Tools).
2. Now try to reproduce the failing transaction and check the [console](/es/docs/Tools/Web_Console) if you are seeing a CORS violation error message. It will probably look like this:

![Firefox console showing CORS error](https://mdn.mozillademos.org/files/16050/cors-error2.png)

The text of the error message will be something similar to the following:

```
Cross-Origin Request Blocked: The Same Origin Policy disallows
reading the remote resource at https://some-url-here. (Reason:
additional information here).
```

> **Nota:** **Note:** For security reasons, specifics about what went wrong with a CORS request _are not available to JavaScript code_. All the code knows is that an error occurred. The only way to determine what specifically went wrong is to look at the browser's console for details.

## CORS error messages

Firefox's console displays messages in its console when requests fail due to CORS. Part of the error text is a "reason" message that provides added insight into what went wrong. The reason messages are listed below; click the message to open an article explaining the error in more detail and offering possible solutions.

- [Reason: CORS disabled](/es/docs/Web/HTTP/CORS/Errors/CORSDisabled)
- [Reason: CORS request did not succeed](/es/docs/Web/HTTP/CORS/Errors/CORSDidNotSucceed)
- [Reason: CORS header ‘Origin’ cannot be added](/es/docs/Web/HTTP/CORS/Errors/CORSOriginHeaderNotAdded)
- [Reason: CORS request external redirect not allowed](/es/docs/Web/HTTP/CORS/Errors/CORSExternalRedirectNotAllowed)
- [Reason: CORS request not http](/es/docs/Web/HTTP/CORS/Errors/CORSRequestNotHttp)
- [Reason: CORS header ‘Access-Control-Allow-Origin’ missing](/es/docs/Web/HTTP/CORS/Errors/CORSMissingAllowOrigin)
- [Reason: CORS header ‘Access-Control-Allow-Origin’ does not match ‘xyz’](/es/docs/Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin)
- [Reason: Credential is not supported if the CORS header ‘Access-Control-Allow-Origin’ is ‘\*’](/es/docs/Web/HTTP/CORS/Errors/CORSNotSupportingCredentials)
- [Reason: Did not find method in CORS header ‘Access-Control-Allow-Methods’](/es/docs/Web/HTTP/CORS/Errors/CORSMethodNotFound)
- [Reason: expected ‘true’ in CORS header ‘Access-Control-Allow-Credentials’](/es/docs/Web/HTTP/CORS/Errors/CORSMissingAllowCredentials)
- [Reason: CORS preflight channel did not succeed](/es/docs/Web/HTTP/CORS/Errors/CORSPreflightDidNotSucceed)
- [Reason: invalid token ‘xyz’ in CORS header ‘Access-Control-Allow-Methods’](/es/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowMethod)
- [Reason: invalid token ‘xyz’ in CORS header ‘Access-Control-Allow-Headers’](/es/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowHeader)
- [Reason: missing token ‘xyz’ in CORS header ‘Access-Control-Allow-Headers’ from CORS preflight channel](/es/docs/Web/HTTP/CORS/Errors/CORSMissingAllowHeaderFromPreflight)
- [Reason: Multiple CORS header ‘Access-Control-Allow-Origin’ not allowed](/es/docs/Web/HTTP/CORS/Errors/CORSMultipleAllowOriginNotAllowed)

## See also

- Glossary: {{Glossary("CORS")}}
- [CORS introduction](/es/docs/Web/HTTP/CORS)
- [Server-side CORS settings](/es/docs/Web/HTTP/Server-Side_Access_Control)
- [CORS enabled image](/es/docs/Web/HTML/CORS_enabled_image)
- [CORS settings attributes](/es/docs/Web/HTML/CORS_settings_attributes)
- <https://www.test-cors.org> – page to test CORS requests
