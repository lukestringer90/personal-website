---
layout: note
title: iOSDevUK 2022
when: 5th - 8th Sep 2022
year: 2022
where: Aberystwyth 󠁧󠁢󠁥󠁮󠁧󠁿🏴󠁧󠁢󠁷󠁬󠁳󠁿
---

10th anniversay of the coference!

## I ❤️ Swift Concurrency
**Tunde Adegoroye**

- Annotate with `@MainActor` to return from a function on the main thread
- `async let` to run in parallel
- Taskgroup to run child tasks in parallel
	- No order
	- Taskgroup finishes when all children finish
- Actor can safely update it’s state across threads
- Tasks have
	- Priority
	- Relationships
	- Handel cancelation
- Xcode 13.2 added backwards support
- Course on Youtube [tundsdev](https://www.youtube.com/c/tundsdev)

## The bleeding edge of SwiftUI
**Malin Sundberg**

- Orbitapp is for macOS + other platforms
- Mercury weather app
- Attach a `presentationDetent` to a sheet, and add fractional size
- Can add a drag indicator if just one size
- View that fits allows you to reuse subviews. Use Grid or Vstack etc
- SwiftCharts and Widgets are SwiftUI only

## Remember Me: A Guide to Memory Debugging
**Luke Parham**

- Memory impacts everything
- Frequent causes of crashes
- iOS & watchOS don’t use paging to free up memory
- Jetsam monitors memory pressure
- Kills apps to free up memory
- memgraphs snapshot memory
- Open in Xcode or cli
- Can snapshot over time to analyse changes
- On macOS use leaks cli for any app
- Leak when lose track and forgets to free
- Retain cycles
- Abandonment is not a leak
	- e.g. a big image hanging around not being used
	- Cached but not used
	- Cannot be identified with a tool
	1. Get a memgraph
	2. Start with footprint to see where
	3. Look at dirty memory Malloc
	4. Malloc-history where allocated
	5. Heap mmap —trace tree
- Less likely to happen in Swift, but in older Obj-c

## Unintended Consequences
**Steve Westgarth**

- The Engineering Leader podcast
- Changing a mental model is risky
- Release Later (reduce risk of unintended consequences) vs Release Early (maximise opportunities)
- Should we implement tracking
- Is it unethical?
- The software we create is our shared collective responsibility
- Consider what the unintended consequences could be in your company

## Becoming an iOS Dev, again
**Michał Waśniewski**

- Split in progression track Engineer vs Management
- Management 3.0 Moving Motivators
- More freedom?
- Not a promotion, it is a role change

## Next Step: Management?
**Leah Voge**

- Management != Leadership
- “Guides a team to execution”
	- Willingness to give feedback
	- Team building + cohesion
	- Execution to get stuff done
- You should like people a lot
- Success is harder to define as a manager
- Less peers and can feel lonely, so be part of a community
- Hands on manager is a nightmare
- Hands warm development
	- Logs. Bugs. Code review.
	- Not critical path.
- You don’t need to be a manager

## NHS COVID-19 app: delivering a resilient app at speed
**Mo Ramezanpoor**

- Singapore, Norway, UK all tried with core bluetooth
- Apple + Google defined Expose Notifications API
- Swift packages to segregate prod + internal builds
- Everything injected
- Good test coverage
- Scenario picker

## Mysteries of SwiftUI Text View
**Natalia Panferova**

- Worked one SwiftUI at Apple
- Text inherits the context from its parent components
- `Text("")` uses a string literal localised string
- SwiftUI Text can parse Markdown
- Release offset timer date style interpolates as live
- Nest text for different styles with modifiers
- Can concatenate, but better to interpolate to allow system to re-order words for other languages
- Can override styles
	- Those applied in interpolation take precedent
	- Reset but using `nil`

## Indie app business models - a better ad-supported option
**Jake Nelson**

- Not evil ads
- Sell an add slot like a newspaper
- Uses expecting Free apps
- Some users only go for free
- Very Free without any monetisation
- Paymeium pat upfront plus consumables
- Start with free then change to paid later. Helps to get feedback early
- Combine methods
- Privacy friendly ads to monetise free users

## Hey Siri!
**Adrian Strahan**

- Snonav audience guidance for routing
- Siri + Siri Shortcuts
	- Report last instruction
	- Change Sky route
- Pronunciation: Piste -> Peeste

## Swift your personal website using Publish
**Danijela Vrzan**

- Static Site Generate (SSG)
- JAMSTACK = JS API Marksup
- Use a CMS for anything dynamic
- Publish by Swift Sundell
- PLOT is a DSL for type safe HTML. 
	- Can use in an iOS app as well
- Define and render using SwiftUI-luke syntax
- INK parses markdown to HTML

## Spark your creativity: the power of iPad Playgrounds
**Anna Beltram**

- Break out of habits to reform creatively
- Builds something in Swift Playgrounds
- Not just at your worklatp on Xcode
- Swift Playground separate app on iPad + macOS
- Can build a full app and launch on App Store
