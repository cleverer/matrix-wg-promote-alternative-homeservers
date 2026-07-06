# Matrix Foundation Server List Policy

This document describes the policy for the Matrix Foundation Server List, which is a list of trusted Matrix servers that meet certain criteria.
The policy is intended to ensure that the servers on the list are reliable, secure, and provide a good user experience.
The main audience for this list is for new users, not familiar with the wider Matrix network and how to participate in it (maybe even switching from other platforms like Whatsapp, Signal, Facebook Messenger, Discord etc).
Newcomers should effectively be able to pick one "blindly" and end up on a server comparably reliable and trustworthy as the [Foundation's own public homeserver](https://matrix.org/homeserver/about/).

The criteria outlined below are specific to the Matrix Foundation Server List and are not intended to be a comprehensive set of requirements for all lists of Matrix servers. The Matrix Foundation Server List is intended to be a curated and also opinionated list of servers.  
The policy outlined here may be used for other or as the basis for other lists of Matrix servers.

> [!NOTE]  
> This document does not describe or formalize the list itself, but rather the policy a homeserver must meet to be included in the list. The list itself and its format is maintained separately and may be updated independently of this policy.  
> In contrast to the policy, the list specification can be used by anyone to host their own list of servers, and the criteria outlined in this document are only applicable to the Matrix Foundation Server List.

Interpretation, changes and implementation of the policy are handled by the Matrix Foundation Homeserver Decentralisation Working Group.  
According to the WGs charter, the WG periodically updates the list. There are not guarantuees towards processing time, but it is the goal to automate as much as possible and react promptoly to issues.

---

## To be included in the Matrix Foundation Server List, a server must meet the following criteria

1. The server must be running a recent version of the Matrix server software ([https://matrix.org/ecosystem/servers/](https://matrix.org/ecosystem/servers/)) that is actively maintained and receives security updates. As a point of reference what we expect, the explanations mentioned here can be taken: https://cyberessentials.online/cyber-essentials-patch-management-explained/
2. The backups are set up to meet a recovery point objective (RPO) of 24 hours. (https://en.wikipedia.org/wiki/IT_disaster_recovery) We do not expect any RTO, but an off-site backup.
3. Multiple people have root access to the server and know how to operate and manage it.
4. The server has a clear policy on how stable its offering is. This means the admins communicate what time frame they will offer between announcing and applying a meaningful reduction to the provided feature set. (This aims to reduce user frustration, if the server suddenly changes its offer.)
5. The homeserver intends to operate for the long term.
6. The homeserver is advertised as operating for the public. The onboarding needs to be open for anyone and the process (any steps necessary for signup) are clearly defined and published by the admins.
7. The server participates in the open Matrix federated network. (It may use a blocklist for moderation purposes, but needs generally allow federation.)
8. The server provides a human readable website on the servers domain to allow non-technical versed people find the information about their account (eg. reset password, find the login to the webclient…) with at least the following information:
    - Who administrates it?
    - How can admins be contacted?
    - What moderation rules/server rules does the server have?
    - What are the registration requirements/process?
    - Hosting type description (see appendix)
    - Hosting components legislation (see appendix)
9. The server supports a well-known support endpoint according to the Matrix spec: https://spec.matrix.org/unstable/client-server-api/#getwell-knownmatrixsupport
10. The server has a moderation policy that aligns with the [Matrix code of conduct](https://matrix.org/legal/code-of-conduct/).

## A server may be removed for the following reasons

1. The server fails to meet the criteria outlined above and does not remediate its violations in a reasonable timeframe. This is roughly "weeks" and may be decided case-by-case by the maintainers of the list.
2. The server administration asks for removal from the list.
3. Server uptime is below a mean of 95% over the period of one year.
4. The Matrix.org Foundation reserves the right to remove any servers that might negatively affect the Foundation's or Matrix network's reputation or is otherwise decided to be unsafe to pick for new users.

## How to request inclusion in the list

_TBD:_ ask in the [#homeserver-decentralisation:matrix.org](https://matrix.to/#/%23homeserver-decentralisation:matrix.org) room. 

### Process
Inclusions are reviewed manually and might require some time.

## Appendix: Data required for representation in the list

To be included in the list, a server must provide the following information:

Title | Description
--- | ---
Server Name | The Matrix [`server_name`](https://spec.matrix.org/latest/appendices/#server-name) of the server, which is used to identify it within the Matrix ecosystem.
Server Common Name | A human-readable name for the server, which can be used for display purposes.
Server URL | The URL of the server, which should be accessible and properly configured.
UI URL(s) | If the server is providing a web-client (or multiple), the URL(s) to it.
Server Software | The name and version of the Matrix server software being used (e.g., Synapse 1.50.0).
Server Admin Contact | Contact information for the server administrator, such as an email address or a link.
Hosting Type description | How and where is the server hosted and what components play into it? eg. self-hosted / housing / colocation / local hoster / hyperscaler / DNS Provider. Basically any technical components required to host the server.
Hosting components legislation | The legislations the individual components of the hosting operate under.
IPv4 Support | Does the server have IPv4 Connectivity (inbound and outbound). 
IPv6 Support | Does the server have IPv6 Connectivity (inbound and outbound).
OAuth 2.0 API Support | Does the server support [OAuth 2.0 API](https://spec.matrix.org/latest/client-server-api/#oauth-20-api) login / next gen auth?
Legacy Login Support | Does the server support [legacy login](https://spec.matrix.org/latest/client-server-api/#legacy-api)?
Sign-Up Process | What steps need to be taken to get an account and log in?
Public Room Directory | Does the server have a public room directory?
Number of active users | The number of active users (Users retained after 30 days of signup)
