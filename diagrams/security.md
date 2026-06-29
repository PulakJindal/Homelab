````markdown
# Security Layers

```mermaid
flowchart TB
    Internet --> UFW
    UFW --> SSH
    SSH --> Ubuntu

    Ubuntu --> Docker
```
````
