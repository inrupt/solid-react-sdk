# Solid React SDK by inrupt

## Introduction

[Solid](https://solid.inrupt.com) is a revolutionary technology created by the inventor of the Web, Sir Tim Berners-Lee. It is a combination of standards and protocols that enable decentralization of the web as it exists today. Solid empowers individual entities (people, organizations, teams, etc.) to separate their data from the systems and applications that leverage it through the use of personal online datastores (pods).

Our goal is to provide developers with a robust toolkit that allows them to develop high-quality applications on Solid, without a ton of prior knowledge or expertise with decentralization or [linked data](https://solid.inrupt.com/docs/intro-to-linked-data).

We believe that providing developers with a great foundation to build awesome apps will help to establish best practices for development on Solid, and lead to some quality results that bring new users into the ecosystem.

We decided to start with React based on its relative popularity in the Solid developer community, but we plan on creating kits for other major frameworks very soon.

We use this SDK ourselves, and will continue to expand and improve upon it as we apply it to real-world use cases.

## Composition

The Solid React SDK is a combination of libraries, components, documentation, best practices, and an application generator meant to accelerate the development of high-quality Solid applications. The [Release Timeline](#release-timeline) identifies when a given listed item will be available.

In summary:

- **[Reusable Components](https://github.com/inrupt/solid-react-components)** that you can use on your own in the applications that you build
- **An [Application Generator](https://github.com/inrupt/generator-solid-react)** that incorporates all of the components and best practices together for you, standing up a fully functional Solid React application.
- **Best practice patterns** that you can reference as examples of how to accomplish particular things

More specifically:

- [Solid React Application Generator](#solid-react-application-generator)
- [User Registration](#user-registration)
- [User Authentication](#user-authentication)
- [Test Infrastructure](#test-infrastructure)
- [Error Handling](#error-handling)
- [Design System](#design-system)
- [Linked Data Javascript API](#linked-data-javascript-api)
- [User Profile](#user-profile)
- [Internationalization (i18n)](#internationalization-i18n)
- [User Preferences](#user-preferences)
- [Notifications](#notifications)
- [Accessibility](#accessibility)
- [Access Control](#access-control)
- [Linking Things](#linking-things)
- [Data Discovery](#data-discovery)
- [Shape-Based Forms](#shape-based-forms)

### Solid React Application Generator
Find it here: [inrupt/generator-solid-react](https://github.com/inrupt/generator-solid-react)  

Since most developers are entering the Solid ecosystem for the first time, we felt it was crucial to give them the ability to get something stood up quickly that they could use as the basis for a quality React application - *fast*. And so we've put together a [yeoman](https://yeoman.io) generator that combines all of the components and best practices in the SDK into something you can use to get going, or as a reference.


### User Registration
Find it here: [inrupt/solid-react-components](https://github.com/inrupt/solid-react-components)

User Registration is a bit different in a decentralized Solid world. "Registration" in the Solid ecosystem means having a Pod and a corresponding WebID. When a user doesn't have these and wants to use a Solid application, the application will need to help them register a new pod without losing the user in the shuffle. We provide componentry and an intuitive UX to facilitate this.

### User Authentication
Find it here: [inrupt/solid-react-components](https://github.com/inrupt/solid-react-components)

User Authentication in Solid uses [OpenID Connect](https://openid.net/connect/) (OIDC) with WebID to provide fully decentralized cross-domain authentication. We provide componentry to facilitate the complete login / logout workflows, leveraging [solid-auth-client](https://github.com/solid/solid-auth-client).

*Check out the [WebID-OIDC Spec](https://github.com/solid/webid-oidc-spec) for additional background.*

### Test Infrastructure
We believe that robust testing is essential to quality applications, and our aim is to have as complete coverage as possible. We use a combination of [Enzyme](https://airbnb.io/enzyme) and [Jest](https://jestjs.io), as we find that the two are quite complementary. Any release with new functionality, or updates to fix non-trivial bugs, will be accompanied by new or updated tests.

### Error Handling
Comprehensive Error Handling helps users and developers diagnose and respond to issues as they arise. Our goal is to have every error in the SDK captured and displayed in a friendly and informative manner, providing as much relevant information as we can.

Our set of component libraries will own their own error messages, and bubble them up to the parent application. Running the application generator will provide reference examples of how component error messages can be consumed and displayed to the user across several common cases, including in-line form validation errors, UI display errors, and server-generated error codes.

### Design System
Find it here: [inrupt/solid-style-guide](https://github.com/inrupt/solid-style-guide)  
View it live: https://design.inrupt.com  

Inrupt's atomic design system is a pattern library of user interface elements that can be utilized in Solid applications. It follows Brad Frost’s Atomic Design principles (http://atomicdesign.bradfrost.com/), and incorporates the Block, Element, Modifier Methodology (or BEM: https://en.bem.info/methodology/), for building systematic, coherent design systems. These patterns can be utilized as-is in their current state, or customized as needed. The Application Generator will automatically incorporate the design system into the code it generates.

### Linked Data Javascript API
One of the most unique aspects to developing on Solid is the underlying linked data model. It is also what makes Solid **so powerful**. For a brief primer, check out our [Introduction to Linked Data](https://solid.inrupt.com/docs/intro-to-linked-data).

Perhaps the greatest barrier to broad developer adoption of linked data has been the lack of intuitive utilities to query and manipulate it. While there are extremely powerful libraries to interface with the RDF ([Resource Description Framework](https://www.w3.org/RDF/) - the model that drives linked data), these require a lot of prior knowledge about RDF and tend to be hard to wield out of the gate by the average developer, which can lead to abandonment.

Ruben Verborgh lays this out well in [this post](https://ruben.verborgh.org/blog/2018/12/28/designing-a-linked-data-developer-experience/), and introduces the tooling that we've been excited to incorporate into the SDK - [https://github.com/RubenVerborgh/LDflex](https://rubenverborgh.github.io/LDflex/). We'll be using LDFlex throughout our components and generated code. However, we will also provide some examples of using a powerful lower level RDF library - [rdflib.js](https://github.com/linkeddata/rdflib.js/) - for reference.

### User Profile
Track it here: https://github.com/inrupt/solid-react-sdk/issues/9  

Nearly all applications will need to allow users to manage a user's profile information. While we originally provided a custom component to facilitate this, due to its limitations we have since re-implemented the User Profile to use [Shape-Based Forms](#shape-based-forms) that renders the form based on a User Profile shape, and provides a great reference for working with linked data forms to read and write linked data.

### Internationalization (i18n)
Track it here: https://github.com/inrupt/solid-react-sdk/issues/10  

Solid is a decentralized worldwide movement, with the ability for applications and data to interface across borders and cultures. As such, it is important to have robust internationalization support from the start. As many developers know, i18n is something that is fairly painless to incorporate when you start making something, and quite a pain to do after the fact. We provide code and demonstrate best practices for internationalization in a linked data Solid world.

### User Preferences
Track it here: https://github.com/inrupt/solid-react-sdk/issues/11

The applications most of us use today manage *user application preferences*. In Solid, user preferences are a bit different (and more powerful), because Solid decouples an application from the data model and corresponding entities ("things") that it depends on. As a result, while a user may manage some preferences that are very specific to the application they're using, they are just as likely to manage preferences associated with the "thing".

For example, consider a chat room. A chat room is a "thing" in linked data. Different people can use different chat apps to message each other in that chat room, because they speak the same vocabulary. That chat room can have a preference associated with it that automatically expands images inline. Regardless of what chat app you're using, your images will be expanded in that room. Similarly, Alice may have a preference associated with any instance of a "chat room" (regardless of the application) that suppresses inline image expansion. We provide the facilities to manage this cleanly.

### Notifications
Track it here: https://github.com/inrupt/solid-react-sdk/issues/12

Solid has a lightweight and versatile mechanism for notifications that work across applications and systems via [Linked Data Notifications](https://www.w3.org/TR/ldn/).

> Linked Data Notifications (LDN) supports sharing and reuse of notifications across applications, regardless of how they were generated. This allows for more modular systems, which decouple data storage from the applications which display or otherwise make use of the data. The protocol is intended to allow senders, receivers and consumers of notifications, which are independently implemented and run on different technology stacks, to seamlessly work together, contributing to decentralisation of our interactions on the Web.

Authorized agents can write messages to pods, and applications can determine which message types they are interested in subscribing to. We provide componentry to read and write notification messages, with the ability to receive messages in real-time via websockets.

### Accessibility
Accessibility is important to us. We believe and hope that the SDK is used to create inclusive applications that work for everyone. We have done our best to incorporate accessibility best practices throughout our code as outlined by Mozilla for [HTML](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML), [CSS & Javascript](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript). That said, we fully expect that there will be areas missed, either now or in the future. If you come across any, please let us know, or even better - fix it and submit a pull request!

### Access Control
Track it here: https://github.com/inrupt/solid-react-sdk/issues/13  

Solid determines what resources agents are able to access in a pod through [Web Access Control (WAC)](https://github.com/solid/web-access-control-spec).

> Web Access Control (WAC) is a decentralized cross-domain access control system. The main concepts should be familiar to developers, as they are similar to access control schemes used in many file systems. It's concerned with giving access to agents (users, groups and more) to perform various kinds of operations (read, write, append, etc) on resources.

Any application that is reading and writing linked data to a pod will need to manage permissions for some of that data eventually. We include helpers and componentry for reading and writing WAC statements pertaining to individual agents and/or groups.

### Linking Things
Track it here: https://github.com/inrupt/solid-react-sdk/issues/14

Leveraging the aforementioned [Linked Data Javascript API](#linked-data-javascript-api), we provide code and UI that shows developers how to link different things together. In linked data, you can link any "Thing" to any "Thing". It's crucial for developers to internalize that, and so we do our best to illustrate how that's done through example.

### Data Discovery
Track it here: https://github.com/inrupt/solid-react-sdk/issues/15

Data discovery is the key to interoperability. Applications need to know where to find a particular kind of data, and similarly, where to put it. Different users will have different preferences based on how they organize the data in their pod. We will provide a means to solve this problem an a universal way that is not implementation specific through linked data shapes.

### Shape-Based Forms
Track it here: https://github.com/inrupt/solid-react-sdk/issues/26

Shapes are a way of defining a data structure and constraints of a linked data object. They are a critical component of linked data, allowing different applications to use a shared shape and ensure they are using the same data and format. 

Applications can use shapes in various ways, from data validation to UI generation. As part of the SDK, we provide a demonstration of how to use shapes in an application to build a user-facing form, complete with data submission.

## Release Timeline

We follow an iterative release pattern, and will have scheduled releases every two weeks. Releases may include new components, as well as improvements or fixes to existing ones.

**Next generator release candidate:** v0.5.1-rc on Wednesday, May 29th 2019  
**Next generator public release:** v0.5.0 on Wednesday, May 22nd 2019


:construction: Feature backlog (in order):

- [User Preferences](https://github.com/inrupt/solid-react-sdk/issues/11)
- [Notifications](https://github.com/inrupt/solid-react-sdk/issues/12)
- [Shape-Based Forms](https://github.com/inrupt/solid-react-sdk/issues/26)
- [Access Control](https://github.com/inrupt/solid-react-sdk/issues/13)
- [Linking Things](https://github.com/inrupt/solid-react-sdk/issues/14)
- [Internationalization](https://github.com/inrupt/solid-react-sdk/issues/10) (Phase 2)
- [Data Discovery](https://github.com/inrupt/solid-react-sdk/issues/15)


:white_check_mark: Released:

- [Solid React Application Generator](#solid-react-application-generator)
- [User Authentication](#user-authentication)
- [User Registration](#user-registration)
- [Design System](#design-system)
- [Accessibility](#accessibility)
- [Test Infrastructure](#test-infrastructure)
- [Error Handling](#error-handling)
- [Internationalization](#internationalization-i18n) (Phase 1)
- [User Profile](https://github.com/inrupt/solid-react-sdk/issues/9)
- [Shape-Based Forms](#shape-based-forms) (Phase 1)


## Feedback

Feedback is essential and much appreciated. If you have a problem, an idea, or anything in between, [open an issue](https://github.com/Inrupt-inc/solid-react-sdk/issues/new) to let us know! A member of the project team will follow up.

## Browser and Device Support

We aim to support the latest stable version of each major browser on desktop, mobile, and tablet.

## License

[MIT](LICENSE.md)
