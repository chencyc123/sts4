Describes the current support for Spring WebFlux in Spring Tools 4. Spring WebFlux is a framework for writing Reactive Web applications. WebFlux supports two programming models for defining Request Mappings:
- Annotation based, Spring MVC-style
- Functional, lambda style

The level of tooling support for these programming models is different.

## Annotation based, Spring MVC-style
The support for WebFlux backed annotation based request mappings is identical to regular Spring MVC annotation based request mappings as documented [here](/Live-Application-Information#live-request-mappings). This includes:
- Symbol navigation
- Live Request Mapping highlights, hovers and Code Lenses
- Code snippet content assist proposals

## Functional, lambda style
The support for WebFlux functional style request mapping definitions is limited to:
- Symbol navigation
- Request Mapping handler functions Code Lens

### Request Mapping Handler Functions Code Lens
The common pattern for defining functional style Request Mapping is having two classes (See [Reactive REST Service getting started guide](https://spring.io/guides/gs/reactive-rest-service):
- Router Functions Bean class
- Request Mapping handler functions Component class

The Component hosting Request Mapping handlers is missing the data about request mapping path. The Code Lens makes that information available in the handlers class.

[[/images/webflux-functional-rm-codelens-eclipse.png|WebFlux Functional RequestMapping Code Lens]]

 