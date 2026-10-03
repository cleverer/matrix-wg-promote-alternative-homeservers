# Architecture

## General Concepts

There is no clear concept of how servers will be discovered. Therefore we list the approaches here and document the architecture decisions around them.

### Static lists

All concepts here assume a static list (with all necessary data to render a data table of the server included) mainained by hand or eg. Pull Requests or Github Issue templates.

#### Hardcoded Lists

&nbsp; | &nbsp;
--- | ---
Status | Rejected
Description | Clients can just hardcode servers that offer open registration in their codebase, without any checks.
Advantages | + Easy to implement.
Disadvantages | - Not very flexible<br/>- does not allow server operators to customize displaying of the server
Reasoning | Rejected for obvious reasons.

#### Hardcoded Web Picker on matrix.org

&nbsp; | &nbsp;
--- | ---
Status | Rejected
Description | We could offer a web picker with hardcoded servers on the matrix.org Website
Advantages | + Easy to implement.<br/>+ Good and easy visibility
Disadvantages | - Not very flexible<br/>- does not allow server operators to customize displaying of the server
Reasoning | 

#### Hardcoded JSON file

&nbsp; | &nbsp;
--- | ---
Status | Under Consideration
Description | We could offer a file served on the matrix.org Website. It could then be fetched by a web-picker in the website and from clients.
Advantages | + Easy to implement.<br/>+ Reasonably flexible
Disadvantages | - Does not directly allow server operators to customize displaying of the server<br/>- Central location can be a single source of failure<br/>- Manual editing is error prone<br/>- Lack of standardization hinders adoption
Reasoning |

#### List file/JSON/API that loads from any server (set by the client developer)

&nbsp; | &nbsp;
--- | ---
Status | Under Consideration
Description | We could standardize a shared format and offer a manually maintained file on matrix.org. It could then be fetched by a web-picker in the website and from clients. Any client developer could also choos their own servers and hardcode them.
Advantages | + Easy to implement.<br/>+ Reasonably flexible<br/>+ Standardization pushes adoption
Disadvantages | - Does not directly allow server operators to customize displaying of the server<br/>- Manual editing is error prone 
Reasoning |

### Dynamic lists

The concepts here do not necessarily assume to be including all data to render the data table on its own and might require more requests.

#### Hardcoded list on matrix.org to asks servers if they accept registrations

&nbsp; | &nbsp;
--- | ---
Status | Rejected
Description | Matrix.org could serve a directory of all participating servers. Clients (or a server picker) could then query all the servers on that list on a specific endpoint to ask if reistartion is open and fetch all the data to render the list.
Advantages | + Allows autonomy to the server admins
Disadvantages | - Does not scale at all, client peformance will be abysmal<br/>- Every server admin gets too much data about the clients.<br/>- Directory list still has to be maintained somehow.
Reasoning | This approach does not really make sense, as the disadvantages are too big.

#### Hardcoded list on any server to asks servers if they accept registrations
&nbsp; | &nbsp;
--- | ---
Status | Rejected
Description | Any server could serve a directory of all participating servers. Clients (or a server picker) could then query all the servers on that list on a specific endpoint to ask if reistartion is open and fetch all the data to render the list.
Advantages | + Allows autonomy to the server admins<br/>+ Allows client developers to provide an opinionated list
Disadvantages | - Does not scale at all, client peformance will be abysmal<br/>- Every server admin gets too much data about the clients.<br/>- Directory list still has to be maintained somehow.
Reasoning | This approach does not really make sense, as the disadvantages are too big.

_WIP_
- Config file => (semi-)dynamically generated List => Client only needs to fetch one file
  - Data might be a bit delayed
- Config file & Discovery Proxy
  - Data is up to date, only list provider knows client
  - Might be significant load
  ![](./assets/architecture-proxy.png)

## Needed Technical Specifications

We need at least 2 specifications:

1. Format of the server list to be loaded by server pickers (clients), depending on architecture concept
2. Format of the server advertisement endpoint.

The first one is more urgent and important, as list generation can happen manually initially.
