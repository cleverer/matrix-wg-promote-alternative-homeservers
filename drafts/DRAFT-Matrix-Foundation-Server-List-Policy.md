# Matrix Foundation Server List Policy

This document describes the policy for the Matrix Foundation Server List, which is a list of trusted Matrix servers that meet certain criteria. The policy is intended to ensure that the servers on the list are reliable, secure, and provide a good user experience.

The criteria outlined below are specific to the Matrix Foundation Server List and are not intended to be a comprehensive set of requirements for all lists of Matrix servers. The Matrix Foundation Server List is intended to be a curated and also opinionated list of servers.  
The policy outlined here may be used for other or as the basis for other lists of Matrix servers.

> [!NOTE]  
> This document does not describe or formalize the list itself, but rather the policy a homeserver must meet to be included in the list. The list itself and it's format is maintained separately and may be updated independently of this policy.  
> In contrast to the policy, the list specification can be used by anyone to host their own list of servers, and the criteria outlined in this document are only applicable to the Matrix Foundation Server List.

Interpretation, changes and implementation of the policy are handled by the Matrix Foundation Homeserver Decentralization Working Group.

---

## To be included in the Matrix Foundation Server List, a server must meet the following criteria

1. The server must be running a recent version of the Matrix server software (Synapse, Dendrite, or another implementation) that is actively maintained and receives security updates. We defined recent as the last 2 patch versions at any given time of a maintained minor and major version.
2. The server is Backed Up daily
3. Multiple people have root access to the server and can manage it
4. The admins commit to communicate changes to the hosting or offering 3 months in advance.
5. The homeserver intends to operate for the long term.
6. The homeserver is advertised as operating for the public. If conditional registration is implemented, then the approval process must be clearly defined.
7. The server is in open federation. (It may however use a blocklist, but default needs to be to allow federation)
8. The server provides a human readable website with at least the following information:
    - Who administrates it?
    - How can admins be contacted?
    - What moderation rules/server rules does the server have?
    - What are the registration requirements/process?
9. The server admins are present in [#homeserver-decentralization:matrix.org](https://matrix.to/#/%23homeserver-decentralization:matrix.org).
10. The server supports a well-known support endpoint according to the matrix spec: https://spec.matrix.org/unstable/client-server-api/#getwell-knownmatrixsupport
11. The server has a moderation policy that aligns with the [Matrix code of conduct](https://matrix.org/legal/code-of-conduct/).
    - It should probably use [policy lists](https://asgard.chat/draupnir/subscribe-to-policy-lists.html) and at least enforce [#matrix-org-coc-bl:matrix.org](https://matrix.to/#/#matrix-org-coc-bl:matrix.org)
    - More policy lists are encouraged but not required.

## A server may be removed for the following reasons

1. The server fails to meet the criteria outlined above and does not remediate it's violations in a reasonable timeframe. With a reasonable timeframe we mean weeks.
2. The server administration asks for removal from the list.
3. No admin of a server is present in [#homeserver-decentralization:matrix.org](https://matrix.to/#/%23homeserver-decentralization:matrix.org) anymore. This is an automatic immediate removal.
4. The server registration policy is now only allowing a closed target group (eg. through political or societal changes, but not changing the policy).
5. Server uptime is below 95% over the period of a year.

## How to request inclusion in the list

_TBD:_ ask in the [#homeserver-decentralization:matrix.org](https://matrix.to/#/%23homeserver-decentralization:matrix.org) room. 

### Process
Inclusions are reviewed manually and might require some time.

## Appendix: Data required for representation in the list

To be included in the list, a server must provide the following information:

Title | Description
--- | ---
Server Name | The matrix `server_name` of the server, which is used to identify it within the Matrix ecosystem.
Server Common Name | A human-readable name for the server, which can be used for display purposes.
Server URL | The URL of the server, which should be accessible and properly configured.
UI URL | If the server is providing a web-client, the url to it.
Server Software | The name and version of the Matrix server software being used (e.g., Synapse 1.50.0).
Server Admin Contact | Contact information for the server administrator, such as an email address or a link.
Server Location | The physical location of the server, which can be used for geographical diversity and latency considerations.
Legal Location | The country or legislation the operators are registered/operating in.
Hosting company Location | If the server is not bare metal operated by the admins, the legal legislation of the hoster.
Domain registry Location | The legislation the TLD of the server is registered in.
IPv4 Support | Does the server have IPv4 Connectivity (inbound and outbound). 
IPv6 Support | Does the server have IPv6 Connectivity (inbound and outbound).
OIDC Support | Does the server support OIDC login / next gen auth?
Legacy Login Support | Does the server support legacy login?
Registration Requirements | If registration is limited, what requirements are therea and what is the approval process?
Public Room Drirectory | Does the server have a public room directory?
Number of active users | The number of active users (_TBD how do we define active users?_)
