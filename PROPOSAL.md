Google Summer of Code 2016 Proposal
===================================

## Bark, a full Microblog implementation in Matrix

- To create a simple blogging system akin to things like Twitter, but with the ability to run your own server.
- Decentralized blogging, which is not only super cool but could allow for much greater scale than a centralized service.
- To create a simple to use client that could be used by any internet user, that will still retain the features of matrix.
- To allow users the choice of their own client, whether that be in the browser or on the desktop.

## Why Microblog in Matrix

- Matrix is very well suited to a subscription system similar to how other microblogging systems work.
- Matrix offers distributed messaging, which isn't something most microblogs offer and something many users would be interested in.
- Matrix has a wide variety of clients/libraries already, so this will not restrict the user on what tools they use.
- By hosting a homeserver, you can offer a much greater degree of privacy. Your messages are not stored in a single database, but in many servers which can apply different security settings per room.

## Design

### Rooms
Rooms will act as a users **stream**. Every user that joins bark will create a single room on their homeserver which would serve . They can **post** to it and **allow/deny** other users access to it. This gives the stream owner some flexibility about allowing people to read their posts and if they want people to **'write on'** their stream.

A user may set their **biograpghy** ( a small piece of text about themselves ) as their room topic. Following a user would be as simple as joining their room.

Replying to a users post would be as simple as sending '>replying to:eventid' followed by your message in a users stream. This should allow for other clients to understand what is being said even if they don't understand the microblog format.

Room naming is more tricky due to the variety of permissions that users may be allowed. The bark client will create a room for the user on their homeserver (this would be a requirement) upon login to the client if it does not exist. The rooms name would be 'Bark - DisplayName' which would be searched for upon each login. You can set whatever permissions you want for this room to make it discoverable or not. People who wish to add you may do so by either typing in your rooms alias if it has one, or your internal ID if not.

The idea behind using this system is that we can provide the users a way to keep total control of their content via the rooms permissions control.

### Client

The client would be a web page designed to make this process more automated and fit for general use. In additon to setting up the users room once matrix details have been given, it will listen for messages on each bark room and sort them into a single stream. The messages would be interactable (e.g. you can 'reblog' them). The client would also have the media features implemented like taking a picture.

Searching for users would be limited at first to your own homeserver since matrix doesn't have a global index system, but you can add people by internalID or alias (the latter being automatic if it exists).

## Timescale
|Week    | May           | June          | July  | Auguest |
|:------:|:-------------:|:-------------:|:-----:|:-------:|
|   1    |               |               |       |         |
|   2    |               |               |       |         |
|   3    |               |               |       |         |
|   4    |               |               |       |         |

## Extra features to implement at a later date
 - A bridge to services such as Twitter,Facebook,G+ etc.
 - Calling users directly through the client.
 
## Why me?
- Familiar with the matrix client -> server spec, and already a [keen contributer](https://github.com/matrix-org/matrix-python-sdk/pull/9)
- Attention to detail with bugs [Javascript UTF8 bug](https://github.com/matrix-org/matrix-react-sdk/commit/081a975d2a3b8c63af68c551e09808806821d41b)
- Worked on several web projects before, including a from [scratch CMS](https://github.com/BreadFramework/bread)
- Regular contributions to open soure projects.[Activity Log](https://github.com/Half-Shot?tab=activity)
- I love working on open source software, and will be happy to continue working on it until I am satisfied with it.
