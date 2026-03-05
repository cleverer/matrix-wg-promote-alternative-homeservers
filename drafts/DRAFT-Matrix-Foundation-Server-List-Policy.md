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

1. The server must be running a recent version of the Matrix server software (Synapse, Dendrite, or another implementation) that is actively maintained and receives security updates.

## A server may be removed for the following reasons

1. The server fails to meet the criteria outlined above and does not remediate it's violations in a reasonable timeframe.

## How to request inclusion in the list

_TBD:_ ask in the [#homeserver-decentralization:matrix.org](https://matrix.to/#/%23homeserver-decentralization:matrix.org) room. 

### Process
Inclusions are reviewed manually and might require some time.

## Appendix: Data required for representation in the list

To be included in the list, a server must provide the following information:

Title | Description
--- | ---
Server Name | The matrix server_name of the server, which is used to identify it within the Matrix ecosystem.
Server Common Name | A human-readable name for the server, which can be used for display purposes.
Server URL | The URL of the server, which should be accessible and properly configured.
Server Software | The name and version of the Matrix server software being used (e.g., Synapse 1.50.0).
Server Admin Contact | Contact information for the server administrator, such as an email address or a link.
Server Location | The physical location of the server, which can be used for geographical diversity and latency considerations.
