---
layout: note
title: SwiftLeeds
when: 7th Oct 2020
year: 2021
where: Leeds 🏴󠁧󠁢󠁥󠁮󠁧󠁿
---

[Conference Website](https://swiftleeds.co.uk)

## Server-side Swift State of the Union: Life after async/await
[Tim Condon](https://twitter.com/0xTim)

* A number of developments in Swift over the last few years to make server side easier
	* Codable
	* Xcode support for SPM
	* Key paths
	* Concurrency
* Upcoming features:
	* Swift Crypto
	* Additional Linux Distros
* Tim Condon believes Swift on the Server **IS Ready for Production**
* Is being used by:
	* Nodes (Arriva trains)
	* Allegro (like Amazon in Poland)
	* John Lewis
	* BBC (for testing infrastructure)
	* Amazon (part of Prime Video)
	* Spotify (open source contributions to Vapor)
	* Apple (although not clear on the specifics [maybe iCloud?])
* Swift as a language feels in the sweet spot between Go and Rust
* Non-Xcode setup for Vapor is still hard
	* Want to improve it
	* As well on Linux
* async/await is exciting as it provides compiler checks for concurrent code
	* Better than using closures
	* Will add the “missing piece” for server application development
* Task local values will help tracing across micro services
	* Tasks are automatically attached to; no need to pass a context object
	* Unique to Swift over other server-side languages
 
## Using Core Data in a SwiftUI application
[Donny Wals](https://twitter.com/DonnyWals)

- Core Data is an old ORM and has 16+ years or optimisation
- Although it is not very friendly to Swift, it does work well with SwiftUI
- Use SwiftUI features such as
	- `@FetchRequest`
	- `@SectionFetchRequest`
- However using these poses the question - does this leak Core Data into your SwiftUI views? 
	- Perhaps not
	- It is really convent even if it does
* Use `@State` for searching and predate updating
* Using a child context
	* Doesn’t trigger notifications to UI
	* Can be discarded when changes are not wanted
	* Saves into the view context
		* Then save the view context to persist to store
* Use a view model to be responsible for managing the contexts and saving
	* Use an `EditAndCreateViewModel` for both behaviours to make it easier
* Managed objects can be over served as they support KVO
	* This makes them work well with SwiftUI

[Example code repo](https://github.com/donnywals/CoreDataInSwiftUI)

## 🍏 + 🔥 = ❤️ (Firebase for Apple Developers)
[Peter Friese](https://twitter.com/peterfriese)

* Bindable items were introduced in WWDC 2021
* When editing don’t want to make changes everywhere
	* Use inner `@ObservableObject`
	* Like a view model
* Use `@ApplicationAppDelegateAdapter` to reuse an existing App Delegate

##  Understanding Data Races and Actors
[Antoine van der Lee](https://twitter.com/twannl)

Useful links for crashes:
* [EXC_BAD_ACCESS](http://avanderlee.com/swift/exc-bad-access-crash/)
* [signal.h(0p) - Linux manual page](https://man7.org/linux/man-pages/man0/signal.h.0p.html)

* Race conditions can cause weird behaviour
* Data conditions can cause crashes
* Multiple threads access the same value at the same time
* Can use a serial lock queue to stop races
* Actors synchronise mutable state across threads
* All lines in an actor are implicitly `isolated`
* Mark non-mutable data `nonisolated`
* Can use the Xcode thread sanitiser
	* Helps to find data races
	* Can do it just on the test suite as it can slow execution down

## Understanding and Using the App Store Connect 
[Josh Holtz](https://twitter.com/joshdholtz)

* The old API was not meant for external access
* Developers figured it out through proxies and reverse engineering
* The new API looks like it is is based on the [JSON API spec](https://jsonapi.org)
* Uses JWTs
	* You can create them in a tool like Paw
* The API still has some missing features
	* Cannot upload an `.ipa`
	* No access token for enterprise accounts
* Spaceship (part of Fastlane) support all new endpoints

## There’s no IF OR ELSE. It’s all about YOU
[Danijela Vrzan](https://twitter.com/dvrzan)

* Changed career from Civil Engineering to Software Engineering
* Moved from Croatia to Canada
* Is a contribuer to http://raywenderlich.com
	* Writing articles helps to learn subjects
* Don’t be afraid to follow you dream
* Don’t be scared to fail

## The life of an Indie Developer
[Jordi Bruin](https://twitter.com/jordibruin)

* There are three kinds of indie developer:
	* Tool Builder
	* Beta chaser
	* Nice filler
* Look at the new API from Apple for inspiration
	* Build small apps around them
* Iterate and get user feedback
* Don’t over polish before releasing
* Being featured on the App Store is good
* Better to be features on site like iMore as this drives more traffic
* Find communities your potential users are active in
	* Facebook
	* Reditt
* Ask them for help
	* Give out promo codes
* A passion project can fill a niche
	* Something to work on over time
	* Dedicated core users will pay for your app
