---
date: 22-09-2024
type: project diary
---

# 1	Let There Be Light

The most I have ever tackeled was Tic Tac Toe, when I just started to program. 2 years have since passed and I have finished CS50, my first year in CS Bsc, quite a few websites using different stacks and some street wisdom. First I tackeled my new goal head on, when it started to hurt, I decided to sit down, do my due diligence.

Namecode is a group, teams over the board interactive puzzle game where given $x$ *cards*, each card with a word on it. A *team*'s job is to derive the cards that are given to it by the *master card*, usually, a $\frac{1}{3}$ for each team, $\frac{1}{3}$ third is *neutral* and a single $1$ is the *killer*. Each team, in its turn, *guess* cards usings its *team leader*'s guidence, he will say 2 thing: A word and a number. the word is the clue, the number is how many card should be guessed from this clue. 

Creating the logic wasn't a fuss, took a few hours, after quite a bit of refactorting, i arrived at some Classes im happy with, and the game run freely, with a single player (me) in the teminal, I even color coded the cards (fancy, I know). The wall was hit when trying to take the game online, for my friends back home. Sessions, Websocket, Multyplayer, Concurruncy, Game Architecture... Ok, I need a learning pause. My darkest deepest fear is to start a project realizing and realizing i made a structural mistake in the very basis of it, to minimize this chance, theres no escape from reading too many out of my league books. Lets study!

# 2	Game Design

## 2.1	Books

- _The Art of Game Design: A Book of Lenses_ by Jesse Schell
- _Game Design Workshop_ by Tracy Fullerton
- _Rules of Play: Game Design Fundamentals_ by Katie Salen and Eric Zimmerman

## 2.2	Blogs

- Gamasutra.com
- Gamedev.net

## 2.3	Multiplayer Principles

- _Designing Virtual Worlds_ by Richard Bartle
- _Multiplayer Game Programming: Architectures and Network Models_ by Josh Glazer and Sanjay Madhav

- [Gaffer on Games](https://gafferongames.com/) – In-depth articles on multiplayer game architecture and networking.
- Unity Multiplayer Documentation – While Unity-specific, many networking concepts are applicable.

# 3	Websockets

## 3.1	Docs

- [MDN WebSockets Documentation](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
- RFC 6455 - The WebSocket Protocol

## 3.2	Tuts

- WebSockets Tutorial by WebSockets.org
- Real-Time Web Applications with WebSockets

## 3.3	In Java

- [Spring Guide: Messaging with STOMP over WebSocket](https://spring.io/guides/gs/messaging-stomp-websocket/)
- [Spring WebSocket Documentation](https://docs.spring.io/spring-framework/docs/current/reference/html/web.html#websocket)

- Baeldung's Guide to Spring WebSockets
- [Java Brains Spring WebSockets Tutorial](https://www.youtube.com/watch?v=UdX9C4sAPQc) – Video tutorial.

# 4	Stomp Protocol

## 4.1	Docs
- STOMP Protocol Specification
## 4.2	Tuts
- Introduction to STOMP
- STOMP over WebSockets
## 4.3	In Springboot
- [Messaging with STOMP over WebSocket](https://spring.io/guides/gs/messaging-stomp-websocket/)

# Session Management