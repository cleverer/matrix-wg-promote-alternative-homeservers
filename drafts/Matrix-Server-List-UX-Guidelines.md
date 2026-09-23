# Matrix Server List User Experience Guidelines

This is a draft trying to describe how we envision the user experience for finding a matrix homeserver.

In general the Client might either redirect to user to the matrix.org web server picker (TBD) for registering or show it's own UI.  
The Client UI might either be a wizard style, guiding the user through selecting a few filters and then recommending a small list of servers or just pick a random one based on the selection, but still allowing the user to change the selection or be a list or grid based overview of all servers, allowing to ser to apply filters like in a webshop.

All the data mentioned in the UX is collected by the list operator and provided to the client directly. The client shall not scrape the servers itself before registering to prevent leaking data such as IP addresses or client information to a server.

## Metadata of a server

Basic metadata should be presented when viewing a servers details. Some might also be shown in a list/grid/overview.

| Title                          | Description                                                                                                                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Server Name                    | The Matrix [`server_name`](https://spec.matrix.org/latest/appendices/#server-name) of the server, which is used to identify it within the Matrix ecosystem.                                                              |
| Server Common Name             | A human-readable name for the server, which can be used for display purposes.                                                                                                                                            |
| Server URL                     | The URL of the server, which should be accessible and properly configured.                                                                                                                                               |
| UI URL(s)                      | If the server is providing a web-client (or multiple), the URL(s) to it.                                                                                                                                                 |
| Server Software                | The name and version of the Matrix server software being used (e.g., Synapse 1.50.0).                                                                                                                                    |
| Server Admin Contact           | Contact information for the server administrator, such as an email address or a link.                                                                                                                                    |
| Hosting Type description       | How and where is the server hosted and what components play into it? eg. self-hosted / housing / colocation / local hoster / hyperscaler / DNS Provider. Basically any technical components required to host the server. |
| Hosting components legislation | The legislations the individual components of the hosting operate under.                                                                                                                                                 |
| IPv4 Support                   | Does the server have IPv4 Connectivity (inbound and outbound).                                                                                                                                                           |
| IPv6 Support                   | Does the server have IPv6 Connectivity (inbound and outbound).                                                                                                                                                           |
| Sign-Up Process                | What steps need to be taken to get an account and log in?                                                                                                                                                                |
| Number of active users         | The number of active users (Users retained after 30 days of signup)                                                                                                                                                      |

## Features shown to the User

Those features should be presented as filters and make it easy to find servers supporting specific features. They are complementary to the basic metadata of a server.

| User facing name               | Description                                                                                                   | Technical Features/MSCs                                                                                                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Link Preview                   | Server side embeddings are needed to show a privacy preserving Link preview in a messages.                    | ???                                                                                                                                                            |
| Public room directory          | Allows anyone to browse public rooms of this server                                                           | ???                                                                                                                                                            |
| Server internal room directory | Allows a user of the server browse all public rooms of the server                                             | ???                                                                                                                                                            |
| Modern Calls                   | Allows users to have 1:1 and group voice and videocalls                                                       | MatrixRTC, Livekit?                                                                                                                                            |
| Bridges                        | Allows users to bridge other messenger systems on this server, without having to install a bridge themselves  | -                                                                                                                                                              |
| Managed moderation services    | Allows a user to create rooms/spaces and add moderation tooling to it without having to install it themselves | -                                                                                                                                                              |
| Managed Bots                   | Does the Server offer managed bots, eg. for webhooks, games, productivity tools…                              | -                                                                                                                                                              |
| Upload limits                  | Does the server have limits fo ruploading files/attachements                                                  | -                                                                                                                                                              |
| Message retention time         | How far back in time are messages retained?                                                                   | -                                                                                                                                                              |
| File retention time            | How long are files/attachements kept?                                                                         | -                                                                                                                                                              |
| Authentication flows           | Does the server use/require Oauth, is it using username/password…                                             | [OAuth 2.0 API](https://spec.matrix.org/latest/client-server-api/#oauth-20-api) / [legacy login](https://spec.matrix.org/latest/client-server-api/#legacy-api) |
