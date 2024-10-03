# ABOUT 

This document provides factual statements regarding the AC-PRO-EDGE firmware. These documents are stored in markdown format, and is part of the `URCMarkdownRepo`. Additionally, the diagrams in these markdown files are in mermaid syntax.

# RESOURCES

* Markdown format is documented here: https://www.markdownguide.org/basic-syntax/

* The Marmaid diagram syntax is documented here: https://mermaid.js.org/intro/syntax-reference.html

# .GIT

This section documents the how the AC-PRO-EDGE firmware is developed using .git

## .GIT Conceptualization

``` mermaid
graph 
  A[Working Files] --> B[Staging Area];
  B --> C[.git Object Database]
  C --> Remotes
```

## .GIT Branches

``` mermaid
graph 
  A[Ben Develop] --> dev[develop];
  B[Brad Develop] --> dev
  C[Tim Develop] --> dev
  D[Vince Develop] --> dev
  dev --> rel[Release]
```


## .GIT-hook-based Workflow 

``` mermaid
graph LR
  A[commit to your-branch] --> |hook runs...| B{git commit succeeds?};
  B -->|No| C[Investigate Problem...];
  C --> |Try Again|A;
  B--> |Yes| E[git push your-branch];

```

# RESOURCES

* Markdown format is documented here: https://www.markdownguide.org/basic-syntax/

* https://mermaid.js.org/intro/syntax-reference.html