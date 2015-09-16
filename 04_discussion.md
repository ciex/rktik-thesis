# Evaluation and Discussion

Rktik is an evolution of the Souma prototype, which has evolved in some areas and taken a completely different approach in others. In this section I will reflect critically on how Rktik measures up to expectations set at the onset of its implementation and underline these findings with data from quantitative usage metrics.

I have collected usage metrics using the external services Google Analytics and Amplitude to find out how people use the site and particularly whether feature usage follows expected patterns. This data is supplemented by raw data posted to the live website. I tried to filter out my own usage of the service as much as possible. Interactions with other users on the site and technical issues make this difficult in some cases.

Depending on how much time I have available to continue work on this project I want to improve areas X, Y, Z. Additionally I want to build a P2P client for Rktik which can be used to communicate using the service without placing ones information in the Rktik server infrastructure.

## Usage Metrics [1p]

Usage metrics are collected using Amplitude and Google Analytics. Collected data includes X, Y, Z, …

Amplitude is a web service that allows tracking events and associated metadata using a Javascript library embedded in all Rktik pages. It is used to track user behavior, specifically how many users interact with certain features of the site.

Please see Appendix: Amplitude measurements for a complete list of captured event types, metadata and usage statistics.

Google Analytics is a web service used to track page load events and analyze visitor metadata sent by their browser and operating system.

Interesting finding 1

Interesting finding 2

Interesting finding 3

## Movement Agency

Movement agency as described in Section: Specific Patterns Movement Identity attributes action of members of a movement to the movement as a whole and thereby communicates the agency of the movement. Currently, movement can post thoughts to their blog as the sole action available. The concept can be furthered by introducing novel movement actions that can be triggered by members:

**Events**

A movement member may propose an event in the movement mindspace. An event consists of a title, location, date, time and privacy setting (members only or public) and can be implemented as an attachment type. Movement members may vote on whether the event proposal is made public which would display it prominently in the movement mindspace or movement blog depending on the events privacy settings. The proposal may be modified after posting in order to satisfy concerns voiced by other members in the events comments section and thereby gain the necessary votes to make it an official event.

**Public Chat**

A movement’s blog may contain a chat module, which non-members can use to converse with the movement. Messages entered into this chat would be displayed in the movement mindspace for members to see. Members can then propose answers and other members can confirm these by voting to a certain threshold. The user who posted the original message into the movement chat would then be shown the answer attributed to the movement as a whole.

**Posting in other parts of the site**

Members may propose a thought to be posted with attribution to the movement in another part of the site. This could be a personal message to a Persona, a reply to any thought not in the movement itself or as a message in the public chat of another movement (as described above).

## API for External Clients [2p]

An API is an application programming interface, which means ___.  

I want to build the API primarily for a client that is installed on a users computer, but it may also be used for third party services built on data published by Rktik. Usage scenarios might include A, B, C.

An external client has the advantages A, B, C. The disadvantages are X, Y, Z.

The API needs the capabilities of ___ presented as API endpoints with respective functionality. It also needs to be robust against abuse from third parties.

### Serialization and Encryption

Data transmitted via the API is to be end-to-end encrypted unless it is visible on the public part of the website. JSON and HTTP REST APIs have emerged as defacto standards in the web infrastructure. The API will serialise ORM models into JSON representations which are then encrypted and wrapped in another JSON representation.

[graphic]

Please see Appendix: API Specification for the full API specification.

### Peer to Peer Extension

Peer to peer is usually referring to a network transport model that doesn’t use server relays for data transmission, but instead exchanges data directly between end user machines. 

Server based infrastructure however has become very inexpensive while offering an unsurpassed performance. The original motivation for peer to peer transfer can still be retained using a server based network if the information transferred is only passing from peer to peer without being readable while in the server-based network. 

This is achieved by using end-to-end-encryption. While there are many libraries available that implement cryptographic primitives there is no clearly identifiable industry standard. The Souma prototype’s encryption was built using the Google Keyczar library and its implementations of the AES and RSA algorithms in combination with an HTTP based mechanism for key exchange.