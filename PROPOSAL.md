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
- Rooms will act as a users "stream".
  - Users may join these rooms to subscribe to the user.
  - Users can take advantage of exsiting matrix features to lock down the rooms for privacy if they wish
  - The topic will act as the users bio.
- A client will be built to assemble the rooms into a single stream
  - In addition, the client will be able to assemble a profile page of a user from the information in the room.

## Timescale
| May           | June          | July  | Auguest |
|:-------------:|:-------------:|:-----:|:-------:|
|               |               |       |         |
|               |               |       |         |
|               |               |       |         |

## Features not present
- Voice/Video calling
 - While present in some matrix clients, it's out of scope for what the project is and most likely will not be implemented.
 
## Why me?
- Familiar with the matrix client -> server spec, and already a [keen contributer](https://github.com/matrix-org/matrix-python-sdk/pull/9)
- Attention to detail with bugs [Javascript UTF8 bug](https://github.com/matrix-org/matrix-react-sdk/commit/081a975d2a3b8c63af68c551e09808806821d41b)
- Worked on several web projects before, including a from [scratch CMS](https://github.com/BreadFramework/bread)
- Regular contributions to open soure projects.[Activity Log](https://github.com/Half-Shot?tab=activity)
- 
