# React SDK for Solid

## Introduction

Our goal is to provide developers with a robust toolkit that allows them to develop high-quality applications on Solid, without a ton of prior knowledge or expertise with linked data or decentralization.

We believe that providing developers with a great foundation to build awesome apps will help to establish best practices for development on Solid, and lead to some quality results that bring new users into the ecosystem.

## Composition

The React SDK for Solid is a combination of libraries, components, documentation, best practices, and an application generator meant to accelerate the development of high-quality Solid applications.

- **Reusable Components** that you can use on their own in the applications that you build
- **An Application Generator** that incorporates all of the components and best practices together for you, standing up a fully functional Solid application.
- **Best practice patterns** that you can reference as examples of how to accomplish particular things

The React SDK for Solid is composed of the following items.

- [Application Generator](#application-generator)
- [User Registration](#user-registration)
- [User Authentication](#user-authentication)
- [Test Infrastructure](#test-infrastructure)
- [Design System](#design-system)
- [Linked Data Interface](#linked-data-interface)
- [User Profile](#user-profile)
- [Internationalization (i18n)](#internationalization)
- [User Preferences](#user-preferences)
- [Notifications](#notifications)
- [Accessibility](#accessibility)
- [Access Control](#access-control)
- [Linking Things](#linking-things)
- [Data Discovery](#data-discovery)

### Application Generator
Since most developers are entering the Solid ecosystem for the first time, we felt it was crucial to give them the ability to get something stood up quickly that they could use as the basis for a quality application - *fast*. And so we've put together a [yeoman](https://yeoman.io) generator that combines all of the components and best practices in the SDK into something you can use to get going, or as a reference.

### User Registration
User Registration is a bit different in a decentralized Solid world. In a typical application, new users go through a closed registration workflow and get an entry in a proprietary database. In Solid, users enter the registration process when they don't have a WebID to identify themselves, or a Solid Pod for reading and writing data. When a user doesn't have these things and wants to use a Solid application, the application needs to send them to a Pod Provider to register, with a callback to return them when they're done. We provide componentry to facilitate this, with an intuitive UX.

### User Authentication
User Authentication in Solid uses [OpenID Connect](https://openid.net/connect/) (OIDC) with WebID to provide fully decentralized cross-domain authentication. We provide componentry to facilitate the complete login / logout workflows, leveraging [solid-auth-client](https://github.com/solid/solid-auth-client).

*Check out the [WebID-OIDC Spec](https://github.com/solid/webid-oidc-spec) for additional background.*

### Test Infrastructure
We believe that robust testing is essential to quality applications, and our aim is to have as complete coverage as possible. We use a combination of [Enzyme](https://airbnb.io/enzyme) and [Jest](https://jestjs.io), as we find that the two are quite complementary. Any release with new functionality, or updates to fix non-trivial bugs, will be accompanied by new or updated tests.

### Design System
The Inrupt atomic design system is a pattern library of user interface design elements to be utilized for solid based applications. Following Brad Frost’s Atomic design principles (http://atomicdesign.bradfrost.com/) along with the structure of Block, Element, Modifier Methodology (or BEM: https://en.bem.info/methodology/)  for building systematic, coherent design systems, these patterns can be utilized as-is or customized throughout from within it’s the atomic components to streamline the efforts to produce a user interface with solid.

### Linked Data Interface
One of the most unique aspects to developing on Solid is the underlying linked data model. It is also what makes Solid **so powerful**. For a brief primer, check out our [Introduction to Linked Data](https://solid.inrupt.com/docs/intro-to-linked-data).

Perhaps the greatest barrier to broad developer adoption of linked data has been the lack of intuitive utilities to query and manipulate it. While there are extremely powerful libraries to interface with RDF (the model that drives linked data), these require a lot of knowledge about RDF and tend to be hard to wield out of the gate by the average developer, which can lead to abandonment.

Ruben Verborgh lays this out well in [this post](https://ruben.verborgh.org/blog/2018/12/28/designing-a-linked-data-developer-experience/), and introduces the tooling that we've been excited to incorporate into the SDK - [https://github.com/RubenVerborgh/LDflex](LDFlex). We'll be using LDFlex throughout our components and generated code. However, we will also provide some examples of using a powerful lower level RDF library - [rdflib.js](https://github.com/linkeddata/rdflib.js/) - for reference.

### Linking Things
Leveraging the aforementioned [Linked Data Interface ](#linked-data-interface), we provide code and ui that shows developers how to link different things together. In Linked Data, you can link any "thing" to any "thing". It's crucial for developers to internalize that, and so we do our best to illustrate how that's done through example.

### User Profile
Solid uses WebID as a globally unique user identifier. It also doubles as the gateway to a given user's profile data. Nearly all applications will need to allow users to manage profile information, and so we provide a component to facilitate this. It's also a great reference for working with linked data forms to read and write linked data.

### User Preferences
The applications most all of us use today manage *user application preferences*. In Solid, user preferences are a bit different (and more powerful), because Solid decouples an application from the data model and corresponding entities ("things") that it depends on. As a result, while a user may manage some preferences that are very specific to the application they're using, they are just as likely to manage preferences associated with the "thing".

For example, consider a chat room. A chat room is a "thing" in linked data. Different people can use different chat apps to message each other in that chat room, because they speak the same vocabulary. That chat room can have a preference associated with it that automatically expands images inline. Regardless of what chat app you're using, your images will be expanded in that room. Similarly, Alice may have a preference associated with any instance of a "chat room" (regardless of the application) that suppresses inline image expansion. We provide the facilities to manage this cleanly.

### Internationalization (i18n)
Solid is a decentralized worldwide movement, with the ability for applications and data to interface across borders and cultures. As such, it is important to have robust internationalization support from the start. As many developers know, i18n is something that is fairly painless to incorporate when you start making something, and quite a pain to do after the fact. We provide code and demonstrate best practices for internationalization in a linked data Solid world.

### Notifications
Solid has a lightweight and versatile mechanism for notifications that work across applications and systems via [Linked Data Notifications](https://www.w3.org/TR/ldn/).

> Linked Data Notifications (LDN) supports sharing and reuse of notifications across applications, regardless of how they were generated. This allows for more modular systems, which decouple data storage from the applications which display or otherwise make use of the data. The protocol is intended to allow senders, receivers and consumers of notifications, which are independently implemented and run on different technology stacks, to seamlessly work together, contributing to decentralisation of our interactions on the Web.

Authorized agents can write messages to pods, and applications can determine which message types they are interested in subscribing to. We provide componentry to read and write notification messaages, with the ability to receive message in real-time via websockets.

### Accessibility
Accessibility is important to us. We believe and hope that the SDK is used to create inclusive applications that work for everyone. We have done our best to incorporate accessibility best practices throughout our code as outlined by Mozilla for [HTML](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML), [CSS & Javascript](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript). That said, we fully expect that there will be areas missed, either now or in the future. If you come across any, please let us know, or even better - fix it and submit a pull request!

### Access Control
Solid determines what agents are able to access resources in a pod through [Web Access Control (WAC)](https://github.com/solid/web-access-control-spec).

> Web Access Control (WAC) is a decentralized cross-domain access control system. The main concepts should be familiar to developers, as they are similar to access control schemes used in many file systems. It's concerned with giving access to agents (users, groups and more) to perform various kinds of operations (read, write, append, etc) on resources.

Any application that is reading and writing linked data to a pod will need to manage permissions for some of that data eventually. We include helpers and componentry for reading and writing WAC statements pertaining to individual agents and/or groups.

### Data Discovery
Data discovery is the key to interoperability. Applications need to know where to find a particular kind of data, and similarly, where to put it. Different users will have different preferences based on how they organize the data in their pod. We will provide a means to solve this problem an a universal way that is not implementation specific through linked data shapes.

## Release Timeline

We follow an iterative release pattern, and will have scheduled releases every two weeks. Releases may be a combination of new components or improvements or fixes to existing components.

Date | Targeted for Release | Notes
-----|-----|-----
**1/23/2019** | [Application Generator](#application-generator), [User Authentication](#user-authentication), [User Registration](#user-registration),   [Design System](#design-system), [Accessibility](#accessibility), [Test Infrastructure](#test-infrastructure) | Initial release focused on standing up the core infrastructure of the SDK and Application Generator. Components in subsequent releases will be incorporated into the generator as part of that release.
**2/6/2019** | [Linked Data Interface](#linked-data-interface), [User Profile](#user-profile), [Forms](Forms) | Reading and writing Linked Data associated with a User Profile using LDFlex.
**2/20/2019** | [Internationalization](#internationalization), [User Preferences](#user-preferences) | Weaving in i18n and Preferences.
**3/6/2019** | [Notifications](#notifications) | Reading and writing notifications, with real-time support over websockets.
**3/20/2019** | [Access Control](#access-control) | Helpers and componentry for reading and writing WAC statements
**4/3/2019** | [Linking Things](#linking-things), [Data Discovery](#data-discovery) | An approach for universal data discovery, and intuitive examples of how to create a linked data graph for use in your applications.

## Browser Support

We aim to support the latest stable version of each major browser; Firefox, Chrome, Safari, and Edge.
