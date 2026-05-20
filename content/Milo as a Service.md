---
title: "Building in public: Milo as a Service"
aliases:
  - "Building in public: Milo as a Service"
---
![This is a photo of my cat Milo](milo_caddy.webp)
## Context 

In November 2025, a couple of my friends and I attended the [Google Developer Group DevFest Toronto 2025](https://gdg.community.dev/events/details/google-gdg-cloud-toronto-presents-google-developer-group-devfest-toronto-2025/). In one of the workshops, we used Gemini CLI to "vibe code" a gmail add-on that greets you with a random cat photo whenever you're checking your inbox. The add-on application used  [catAAS](https://cataas.com/) to retrieve these images.

![[img_0371.jpg]]

In all honesty, I was more fascinated by [catAAS](https://cataas.com/) than the actual add-on; a RESTful API service dedicated to providing the API consumers with cat photos. They claim to have over 1900 unique cats in their system, which is impressive. 

The API itself is simple, it accepts public GET requests to retrieve a random cat, a list of cats, a specific cat, and a cat photo with provided text, i.e. `GET /cat/says/{text}`. You can see their API schema on their [docs](https://cataas.com/doc.html).



milo as a Service (MiloAAS) is a proposed (to myself) web API built using Java and Spring Boot. It is inspired by _[catAAS](https://cataas.com/)_; however, the goals of this project are different.

The core feature set includes 

- retr