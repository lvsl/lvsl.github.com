---
layout: post
title: Using APIBlueprint for Fun and Profit
published: true
tags:
  - JSONSchema
  - Apiary
  - APIBlueprints
  - Contract First
---

### Intro
*Contract First Design* was postulated by [Bertrand Meyer](http://en.wikipedia.org/wiki/Bertrand_Meyer) almost 30 years ago.
Yet I have not seen any practical implementation of these ideas when designing a new API for a web service.

`Until now!`

[Apiary](http://apiary.io/how-it-works) has come quite far in delivering something that can be used in practice.
They provide a special language—[APIBlueprint](http://apiblueprint.org/)—plus a nice documentation reader with an embedded mock server and an API debugger with a simple editor (which can even sync with your *GitHub* account).
After spending a day playing with *Apiary* and *APIBlueprints*, I'd like to note that *API Blueprints* is nothing more than a Markdown template used by *Apiary* to generate its documentation and mocking services.
I found it very clumsy.
Still, the nice thing about *Apiary* is that they combined multiple related technologies and added some nice design.

### How-To
Here, I will attempt to describe the experience I had when building a sample API: [Xmetrics](http://docs.xmetricsv1.apiary.io/)

First things first:
I want explicit API versioning, but unfortunately, *Apiary* does not support this.
So I just added `/v1` to every resource I described in the API.

When describing API calls, I like to think about four essential things:

 - Query string parameters
 - Input data structures
 - Output data structures
 - Error descriptions

*Apiary* only has support for structured documentation of query string parameters.
For Input, Output, and Error descriptions, I use plain *Markdown* tables right after the Action declaration.

Here is what a complete section for one API call looks like:

    ### <API-call-name> [POST]
    
    #### Input JSON Description
    | Name | Description | Details |
    | ---- | ----------- | ------- |
    
    #### Output JSON Description
    | Name | Description | Details |
    | ---- | ----------- | ------- |
    
    #### Errors Description
    | Name | Description | Details |
    | ---- | ----------- | ------- |
    
    + Request (application/json)
    
        + Body
        
            ... sample JSON request ...
        
        + Schema
        
            ... JSON-Schema ...
    
    + Response 200 (application/json)

        + Body
        
            ... sample JSON response ...
    
        + Schema
        
            ... JSON-Schema ...

    + Response 500 (application/json)

        + Body
        
            ... sample JSON response ...
    
        + Schema
        
            ... JSON-Schema ...
 
One feature that surprised me and looks very neat is support for [JSON Schema](http://json-schema.org/).
It really helps to shape your API correctly.
The documentation doesn't clarify how to use or add a schema, but [luckily, there is support](http://support.apiary.io/knowledgebase/articles/147279-json-schema-validation).

IMHO, the next step for *Apiary* should be to add functionality to generate stub code for popular frameworks like Django, Rails, Express.js, Netty, Play Framework, etc. That would allow me to convert my spec into a working service.
**This Is Cool**.

### On Using Markdown
I've used Markdown extensively with [Pandoc](http://johnmacfarlane.net/pandoc/README.html) to generate a LaTeX paper.
Now, with APIBlueprints, I'm using it to produce a spec for my API (and to write this post as well).
Markdown is great for converting plain text into any particular format. However, the lack of a "standard markdown" is a major pain.
Every Markdown-based "language" tries to add or change syntax and impose syntactic (e.g., reserved keywords, indentation) and semantic rules.
I must admit that things have improved since the introduction of "GitHub Flavored Markdown."

*For those who like to read the original source, I refer to the [original](http://cecs.wright.edu/~pmateti/Courses/7140/Lectures/OOD/meyer-design-by-contract-1992.pdf) work.*
