---
title: Authentication
parent: Advanced Configurations
---

# Authentication

When you enable the basic authentication dirrectly in your docker-compose.yml file, 
a prompt will be showed in the browser to you include the user and password defined in your enverionment variables.


- BasicAuth__Enabled
  enable the basic authentication

- BasicAuth__AdminUsername
Your username

- BasicAuth__AdminPassword
Your password


```yml
environment:
    BasicAuth__Enabled: true
    BasicAuth__AdminUsername: "dev"
    BasicAuth__AdminPassword: "dev"
```



{% capture docker_full_example_note %}
{% include note-docker-full-example.md %}
{% endcapture %}
{{ docker_full_example_note | markdownify }}
