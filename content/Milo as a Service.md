---
title: "Building in public: Milo as a Service"
aliases:
  - "Building in public: Milo as a Service"
---
![This is a photo of my cat Milo](milo_caddy.webp)
*photo of my cat, milo, looking like a boss*
## Context 

In November 2025, a couple of my friends and I attended the [Google Developer Group DevFest Toronto 2025](https://gdg.community.dev/events/details/google-gdg-cloud-toronto-presents-google-developer-group-devfest-toronto-2025/). In one of the workshops, we used Gemini CLI to "vibe code" a gmail add-on that greets you with a random cat photo whenever you're checking your inbox. The add-on application used  [catAAS](https://cataas.com/) to retrieve these images.

In all honesty, I was more fascinated by [catAAS](https://cataas.com/) than the actual add-on; a RESTful API service dedicated to providing the API consumers with cat photos. They claim to have over 1900 unique cats in their system, which is impressive. 

The API itself is simple, it accepts public GET requests to retrieve a random cat, a list of cats, a specific cat, and a cat photo with provided text, i.e. `GET /cat/says/{text}`. You can see their API schema on their [docs](https://cataas.com/doc.html). 

I wanted to create something like this for Milo and thus the idea of Milo as a Service was born. 

p.s here's a photo of us at the end of the conference

![[img_0371.jpg]]

## Introducing: Milo as a Service (MiloAAS)

Though Milo as a Service may seem like a simple CRUD web API... ok well, it IS a simple CRUD web API. The focus of building this service, however, is not the API itself, it is the infrastructure, architecture and software design behind it. 

The core domain logic simply includes

1. Retrieving random photos of Milo
2. Allowing authorized users to contribute photos of Milo (thx mom)
3. Authentication and authorization for the aforementioned contributors

None of this is groundbreaking, I am keeping the core business logic **intentionally simple.**

The primary goal of MiloAAS is to build a production style enterprise backend with a focus on  

- developer operations (DevOps), 
- developer experience (DX), 
- cloud infrastructure (via AWS), and, 
- an appropriate and scalable software architecture for the backend application itself. 

