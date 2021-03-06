# blockstack-ios-client
iOS client for blockstack-core.

###Installation

Installation is done through [CocoaPods](http://cocoapods.org/), a Swift 3 and Objective-C dependency manager. Visit their site for more information about [CocoaPods](http://cocoapods.org/) configuration and installation.

To install [CocoaPods](http://cocoapods.org/), open `Terminal` and run the following command:
```
$ sudo gem install cocoapods
```

Add `Blockstack` to your `Podfile`:

```ruby
pod 'Blockstack', :git => 'https://github.com/blockstack/blockstack-ios-client.git'
```

If working with Swift, be sure to include `use_frameworks!` on your `Podfile`.

Install the pod:
```
$ pod install
```

###Usage example

To use the Blockstack client on your iOS application, initialize it with your app ID and app secret obtained by signing up for an account at the [Onename API](https://api.onename.com/) site.

This is how to lookup users:

```swift
let client = Blockstack(appId: "YOUR_APP_ID", appSecret: "YOUR_APP_SECRET")
client.lookup(["itsProf", "guylepage3"]) { (data, error) in
    if let error = error {
        debugPrint(error.localizedDescription, error)
    }
    
    if let data = data {
        debugPrint(String(data: data, encoding: .utf8))
    }
}
```
