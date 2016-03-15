Bark: Microblogging in Matrix
===================================

Matrix seems like the ideal framework on which to build a microblogging system. In essence, a microblog is just a selective messaging application where you choose who you subscribe to. I plan to create a full implementation of a microblog (using examples such as Twitter and Google Plus as an influence on it's look) on top of Matrix. This involves building a structure to accommodate features such as ‘replying’, 'following' and a ‘central timeline' inside a client, to make it usable for everyone.

I have a huge interest in building a distributed service similar to existing microblogs, and 'Bark' is basically the opportunity I have to prove that one is viable, while also proving that Matrix is so much more than just a group messaging system to the masses.

## Why Microblog in Matrix

- Matrix is very well suited to a subscription system similar to how other microblogging systems work.
- Distributed messaging is something most microblogs don’t offer,but is something users would be interested in.
- Matrix has a wide variety of clients/libraries already, so this will not restrict the user on what tools they use.
- By hosting a homeserver, you can offer a much greater degree of privacy. Your messages are not stored in a single database, but in many servers which can apply different security settings per room.

## Design

### Rooms

Rooms will act as a user’s stream. Every user that joins Bark will create a single room on their homeserver which would serve as their personal ‘timeline’. They can post to it and allow/deny other users access to it. This gives the stream owner some flexibility about allowing people to read their posts and if they want people to 'write on' their stream.

A user may set their biography (a small piece of text about themselves) as their room topic. Following a user would be as simple as joining their room.
Replying to a user’s post would be as simple as sending two messages. The first would be '>replying to:eventid' where the eventid is the previous message. Secondly, sending the reply body.

This should allow for other clients to understand what is being said even if they don't understand the microblog format.

Room naming is more tricky due to the variety of permissions that users may be allowed. The bark client will create a room for the user on their homeserver (this would be a requirement) upon login to the client if it does not exist. The rooms name would be 'Bark - DisplayName' which would be searched for upon each login. You can set whatever permissions you want for this room to make it discoverable or not. 

People who wish to add you may do so by either typing in your rooms alias if it has one, or your internal ID if not.
The idea behind using this system is that we can provide the users a way to keep total control of their content via the rooms permissions control.


### Client

The client would be a single page webpage, which simplifys the process explained above.In additon to setting up the users room once matrix details have been given, it will listen for messages on each bark room. It will then sort them into a single stream. The messages would be interactable (e.g. you can 'reblog' them). The client would also have the media features implemented like taking a picture or sharing a audio/video file.

Searching for users would be limited at first to your own homeserver since matrix doesn't have a global index system, but you can add people by internalID or alias (the latter being automatic if it exists).

## Deliverables

- I plan to deliver a complete web based client by the end of the development period. Mpre specifically, this means the styling, javascript source code and html documents used to develop it.
- Full documentation on the implementation of creating a 'bark' client, and how to extent this one further.

## Timeframe

This is the schedule I plan to keep to. Each milestone has been given a deadline. I expect to meet them, and the time will include bug testing and research for each task.

|Week    | May           | June          | July            | August          |
|:------:|:-------------:|:-------------:|:---------------:|:---------------:|
|   1    | ///////////// |               |                 |                 |
|   2    | ///////////// | M.⚀ (Fri 12th)|  M.⚁ (Fri 8th)  | M.3 (Fri 12th)  |
|   3    | ///////////// |               |                 | **Final Submit**|
|   4    | Begin:28th    |               |                 | /////////////// |

## Milestones

### ⚀ Milestone 1 : Basic Functionality

My first milestone for the project would be to deliver on the basic aims of the project.
The CSS would be minimal right now as at this stage I will be focusing on good code quality first.
I suspect this 

- Connecting to and from Matrix in the client.
- Setting up the user
 - 'Stream' Room
- Sending and reciving messages.
- Subscribing to other people
- Showing all the messages in a timeline
- A minimal form of user profile, probably just enough to subscribe.


### ⚁ Milestone 2: User Interface

Milestone 2's objective is to have it ready for testing by anyone.
- Redesigned CSS with a central layout *will take the majority of the time*
- Settings dialogue to change privacy settings for a user.
- Reply feature
- Ability to see individual user profiles and streams.
- Browser features such as notifications.

In addition, I plan to give this to users to test and get some feedback

### ⚂ Milestone 3: Extra Features and Testing

This milestone will be mainly checking that everything is in place
and the usability is there.

- Taking in feedback from testing, and working on features that seem reasonable.
- Small features (such as replying inside a message).
- Search functionality
- Checking the client is responsive for phones,tablets and other devices.
- May be limited to homeservers, depending on how I plan to do it.
- Testing, testing and more testing.

## Extra features to implement at a later date
 - A bridge to services such as Twitter,Facebook,G+ etc.
  - Quite likely will be part of another project going on concurrently with my own, so I'll leave this discussion until     after the GSoC period.
 - Calling users directly through the client.
 
## Why me?

I’m currently a 1st year student of Computer Science at the University of Portsmouth in the UK.

- Familiar with the matrix client -> server spec, and already a [keen contributer](https://github.com/matrix-org/matrix-python-sdk/pull/9)
- Extremely fluent in Javascript, HTML and CSS
- Plenty of experience using Git/Github.
- Attention to detail with bugs [Javascript UTF8 bug](https://github.com/matrix-org/matrix-react-sdk/commit/081a975d2a3b8c63af68c551e09808806821d41b)
- Worked on several web projects before, including a from [scratch CMS](https://github.com/BreadFramework/bread)
- Regular contributions to open soure projects.[Activity Log](https://github.com/Half-Shot?tab=activity)
- In terms of real world experience, I have worked as a Software Developer for a total of 6 Months at a Embedded    Software Firm.
- I love working on open source software, and will be happy to continue working on it until I am satisfied with it.
