# Markdown Playground
[Markdown Syntax](https://www.markdownguide.org/cheat-sheet/)

[Mermaid Syntax](https://mermaid.js.org/intro/syntax-reference.html)
```mermaid
graph TD;
A-->1;
A-->2;
A-->3;
```
Next TODO: draw a flowchart/app system design
## General Flow of the Allure UI Clone App

```mermaid
    flowchart TD;
    app[App]--> header[Header]

    header--> search-bar[Search Bar]
    header--> themes-languages[Themes/Language select]

    search-bar--> |dispatch keyword|search-bar-context[Search Bar Context]
    search-bar-context-->|filter nav items by search keyword|nav-bar

    note-search-bar-context[Using context to embed jsx element into navbar: `icon`]--> search-bar-context

    themes-languages--> |dispatch change themes/languages|redux[Redux store]
    redux--> |set Allure Theme/Language|app

    app[App]--> nav-bar[Nav Bar]
    nav-bar-->|navigate|app

    app[App]-->|url| outlet[Outlet]

    outlet-->check-path{Check path}
    check-path-->|path=/ or path = /dialog| dialog-page[Dialog page]
    check-path-->|path=*| others-page[Other pages]

    dialog-page-->titles[Page content]
    dialog-page-->example[Example]
    example--> dialog-example[Dialog Example]
    example--> show-example-code[Code viewer]
    prism-->|show code|show-example-code
```
