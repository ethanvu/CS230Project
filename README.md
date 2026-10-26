# CS230Project
This repository holds my software design document for The Gaming Room's game, *Draw It or Lose It*, along with the Java code I wrote for the project.
 
## Project Reflection
 
### The client and their software requirements
The client was The Gaming Room. They had an Android-only game called *Draw It or Lose It*, which is similar to the TV game show *Win, Lose or Draw*. Teams try to guess a puzzle while the app draws images from a library of stock drawings. Each game has four one-minute rounds. If a team doesn't guess in time, the other teams each get one 15-second guess. The Gaming Room wanted to turn the game into a web-based app that runs on many platforms. The requirements were:
 
- A game can have one or more teams.
- Each team can have multiple players.
- Game and team names must be unique.
- Every game, team, and player needs a unique ID.
- Only one instance of the game service can exist in memory.
- The app must work in a distributed environment, on desktop and mobile.
### What I did particularly well
I connected the technical decisions directly to the client's needs. In the domain model, I explained how the Entity base class, the Singleton pattern for GameService, and iterator-based name checks meet the requirements for unique names and IDs. In the evaluation and recommendations, I compared Linux, macOS, Windows, and mobile platforms on their server options, licensing costs, client-side development, and development tools. I also backed my recommendations with specific numbers, such as the storage size of the image library.
 
### What helped when developing the code
Planning the design first made the coding easier. Once the UML diagram showed which classes inherited from Entity and how GameService, Game, Team, and Player were related, I knew where each attribute and method belonged. I spent less time rewriting code. Writing out the rules for unique names and the single-instance requirement also showed me exactly where the Singleton and iterator patterns were needed.
 
### What I would revise
I would revise the System Architecture View and the Evaluation section. The architecture section has no diagram, so I would add one showing the browser clients, load balancer, Linux application servers, database, image storage, and CDN, and how they connect. I would also bring the evaluation up to date with current licensing prices, and make the table cells shorter and easier to compare side by side.
 
### Interpreting and implementing the user's needs
I turned each thing the client asked for into a specific design decision:
 
- Unique names became duplicate-name checks that run before a new game or team is created.
- One instance of the service became the Singleton pattern.
- Support for many platforms became a responsive web client talking to a single back end.
- Fast gameplay became memory strategies such as preloading the next image and serving compressed images.
Considering the user's needs matters because software that works technically but doesn't fit how people use it fails anyway. Here, a lagging image or an unfair timer would ruin the game, no matter how clean the code is.
 
### My approach to designing software
I started with the requirements. I identified the main objects and their relationships, picked design patterns that fit the constraints, and then compared platforms before making recommendations. In the future I would:
 
- Write user stories and use cases early.
- Sketch UML and architecture diagrams before writing code.
- Build small prototypes to test risky parts, such as real-time image rendering.
- Compare options with a weighted decision matrix that includes cost.
- Review the design with the client and teammates at each stage, so problems are caught before they become expensive to fix.
