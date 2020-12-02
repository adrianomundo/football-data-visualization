# Football Data Visualization

The repository contains the code for the dashboard on football visualization available [here]

![Data Visualization Screenshot](/data/viz_screenshot.png=200x200?raw=true)

## Getting Started
> Sagrada is a game of Dice Drafting and Window Crafting for 1 to 4 players that plays in about 30 minutes. Developer as a final project of Software Engineering course A.Y. 2017/2018 at Politecnico di Milano (also as Bachelor thesis). You can find more information [here]


## Usage

The game requires [Java 8 SE] or later versions to run.

#### Client

```sh
$ java -jar Client.jar 
```

#### Server
```sh
$ java -jar Server.jar
```

#### External libraries

The external libraries we used to implement some game's features are linked below.

| Library | Link | Use |
| ------ | ------ | ------ |
| GSON | https://github.com/google/gson | We use this library to load json file for the pattern card |
| Jansi | https://github.com/fusesource/jansi | We use this library to load ANSI escape codes to format CLI output with colors |

## Specification covered

**Game-specific met requirements:**

- Complete rules (toolcards from 1 to 12)

**Game-agnostic met requirements:**

- Server side
    - Implemented rules' game with JavaSE
    - Instantiated only once
    - It supports matches with Socket and RMI simultaneously
    
- Client side
    - Implemented with JavaSE
    - GUI implemented with JavaFX
    - On startup the player can choose the type of connection (Socket or RMI)
    - On startup the player can choose the type of user interface (CLI or GUI)

- Match start
    - If there are no matches in start-up phase, a new match is created, otherwise the player automatically gets into the match
    - The match starts once there are four logged players. When two players connect to the match, a timer is initialized, loaded from a configuration file located in the server-side. If the timer expires and the number of players isn't reached, the match starts with the logged players, if they are >= 2. Furthermore, if in the meantime the number of players falls below 2, the time is reset
    
- During the match
    - The players must follow the game's rules
    - The disconnection is handled both when it happens automatically and manually
    - The game continues, skipping the disconnected player
    - A player can reconnect to the match
    - All players are notified when a player disconnects
    - The players must do a move within a timer's duration
    - If at some point the player in the match is only one, the match ends with the remaining player's victory

- Advanced functionalities
    - **Dynamic pattern card**: pattern card manually loaded from a file in the pc
    - **Single Player**: game mode that allows a single player to do a match
    
- Detailed requirements - see this [file]
- Modeling: [UML]
- Design: [MVC Pattern]

## Build With
* [Intellij IDEA] - Java IDE
* [Java 8 SE] - version of SDK used
* [Maven] - dependency management 
* [jUnit] - testing framework
* [JavaFX] - library for GUI design with [SceneBuilder]
* [SonarQube] - test coverage and code quality
## Authors

* <a href="https://github.com/adrianomundo"> Adriano Mundo </a>
* <a href="https://github.com/SalvatoreFadda"> Salvatore Fadda </a>
* <a href="https://github.com/dariomiceli3"> Dario Miceli </a>


License
----
This project is licensed under the Apache 2.0 License - see the [LICENSE] file for details


[//]: #

   [here]: <https://datavizdashapp.herokuapp.com/>
   [LICENSE]: <https://github.com/adrianomundo/football-data-visualization/blob/main/LICENSE>
   [file]: <https://github.com/adrianomundo/ing-sw-2018-fadda-miceli-mundo/blob/master/Requirements.pdf>
   [UML]: <https://github.com/adrianomundo/ing-sw-2018-fadda-miceli-mundo/tree/master/deliveries/UML/final>
   [MVC Pattern]: <https://en.wikipedia.org/wiki/Model–view–controller>
   [Intellij IDEA]: <https://www.jetbrains.com/idea/>
   [Maven]: <https://maven.apache.org>
   [jUnit]: <https://junit.org/junit5/>
   [JavaFX]: <https://openjfx.io>
   [SonarQube]: <https://www.sonarqube.org>
   [SceneBuilder]: <https://gluonhq.com/products/scene-builder/>
