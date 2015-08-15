# Refactoring
### The perfect way for developers to procrastinate

Evan DeLaney (@edelaney05)
CocoaHeads August 2015

---
## The Patient

`https://github.com/CocoaHeadsAtlanta/2015-08_Refactoring`

---
# Workflow
1. Learn a refactoring technique
2. Apply that technique to `AddressBook`
3. Discuss
4. Rinse and repeat

---
# Yes, we are gold plating contrived example code.
#### You come up with the next CocoaHeads meeting in 24 hours.

---
> This needs to be refactored
-- Every engineer, ever

^ Manager Pro Tip™: Try not to use “refactoring” when communicating with to non-technical types when what you mean is “re-write that nasty hack of technical debt that our insane deadline forced me to do at 2am.”

---
> I do not understand this $h%@!
-- Translation

^ Engineering Pro Tip™: If you don’t understand a something in the code base you’re working on, then start your context gathering process by exploring the code with unit tests. That might uncover where refactoring would improve things.

---
# Real Talk
**Refactoring:** a change made to the internal structure of software to make it easier to understand and cheaper to modify without changing its observable behavior.

^ Refactoring has business value. Refactoring isn’t *easy* but it strives to make the code more *simple*.

---
# Code Smells Should Drive Refactoring

---
# Refactor #1
## Conventions, Readability, and Style

---
# Readability, Style, and Conventions
- Public or Private methods and properties
- String-ly Typed Code / Magic Numbers
- Direct ivar access vs. accessor methods
- Naming conventions
- Comments

---
# Apple Has an Opinion
- [Coding Guidelines for Cocoa](fhk.io/apple-cocoa-guidelines)
- [Programming with Objective-C, Conventions](fhk.io/objc-conventions)

---
# 

---
# Refactor #2
## Extract a  
## `{ Class | Method | Thingy }`

---
# Single Responsibility Principle
- “A class should only have one reason to change” … wat.
- Tell your rubber duckie in one sentence **without using a conjunction** what the code you’re working on does.

> It’s the delegate of my application ~~and sets up my Core Data stack~~.
> It displays controls for managing audio playback, ~~brews espresso, calculates pi to 1000 digits, and plays backgammon.~~

---
# UIViewController
## >mic drop<

^ The subclass heavy design of `UIViewController` kinda sucks, and I think after 8 years Apple is starting to agree (look at the billion view controller-y related protocols we got in iOS 7 - transitioning delegate, etc). There are plenty of resources out there for helping us think of ways to put our view controllers on a diet. Start with Chris Eidhof’s [Lighter View Controllers](http://chris.eidhof.nl/posts/lighter-uiviewcontrollers.html) and his re-hashing in [Issue 1](http://www.objc.io/issues/1-view-controllers/lighter-view-controllers/) of objc.io.

---
# Correct. This ain’t easy.

^ The goal is *simplicity*, which doesn’t imply that it will be *easy*, too. Rich Hickey has an excellent talk titled [Simple Made Easy](http://www.infoq.com/presentations/Simple-Made-Easy)

---
# 

---
# Refactor #3
## Replace Conditional with Polymorphism

---
# Same Interface, Different Behavior

^ Swift is leading the charge by championing “Protocol Oriented Programming.” If you haven’t watched the 2015 WWDC video [Protocol-Oriented Programming in Swift](https://developer.apple.com/videos/wwdc/2015/?id=408) set aside an hour.

---
# Smells
- Repeated if-else statements in different classes
- Switch statements with a handful of cases
- Objects that have a  “type” property and enum
- Long chains of if-else

---
## Isolates behavior into one obvious area

---
> Switches get stitches
-- Gang Slogan

---
# Refactor #4
## Leverage Language Features

---
# Objective-C
- Categories
- `id`
- Dynamic Dispatch
- Key-Value Coding (and Key-Value Observing)

^ At the iOS 7 Tech Talks, Apple evangelist Dave DeLong knocked my socks off with the talk Architecting Moderns iOS Apps, Part 2. About halfway through he starts talking about maintaining backwards compatibility, and it changed my entire perspective on leveraging the Objective-C language and runtime to write “clean code.”

---
# Swift
- Extensions
- Generics
- Enums
- **Swift 2.0:** Guard-let

^ Another great 2015 WWDC video about leveraging language specific features for refactoring is [Swift in Practice](https://developer.apple.com/videos/wwdc/2015/?id=411)

---
# 
