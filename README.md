<p align="center">
    <img src ="Resources/Logo_GitHub.png" alt="PrintingKit Logo" title="PrintingKit" width=600 />
</p>

<p align="center">
    <img src="https://img.shields.io/github/v/release/danielsaidi/PrintingKit?color=%2300550&sort=semver" alt="Version" title="Version" />
    <img src="https://img.shields.io/badge/swift-5.8-orange.svg" alt="Swift 5.8" title="Swift 5.8" />
    <img src="https://img.shields.io/github/license/danielsaidi/PrintingKit" alt="MIT License" title="MIT License" />
    <a href="https://twitter.com/danielsaidi">
        <img src="https://img.shields.io/twitter/url?label=Twitter&style=social&url=https%3A%2F%2Ftwitter.com%2Fdanielsaidi" alt="Twitter: @danielsaidi" title="Twitter: @danielsaidi" />
    </a>
    <a href="https://mastodon.social/@danielsaidi">
        <img src="https://img.shields.io/mastodon/follow/000253346?label=mastodon&style=social" alt="Mastodon: @danielsaidi@mastodon.social" title="Mastodon: @danielsaidi@mastodon.social" />
    </a>
</p>


## About PrintingKit

PrintingKit helps you print PDF documents, images, etc. in Swift and SwiftUI.

For instance, to print a PDF file in the main bundle, just do this:

```swift
let bundle = Bundle.main
let url = bundle.url(forResource: "doc", withExtension: "pdf")
let item = PrintItem.pdfFile(at: url)
try? StandardPrinter().print(item)
```

PrintingKit currently supports the following `PrintItem` types:

* `.attributedString(_:configuration:)` - an attributed string.
* `.imageData(_:)` - JPG or PNG data.
* `.imageFile(at:)` - a JPG or PNG file at a certain URL.
* `.pdfData(_:)` - PDF document data.
* `.pdfFile(at:)` - a PDF document file at a certain URL.
* `.string(_:configuration:)` - a plain string.
* `.view(_:withScale:)` - any SwiftUI view. 

PrintingKit supports `iOS 13` and `macOS 11`.



## Installation

PrintingKit can be installed with the Swift Package Manager:

```
https://github.com/danielsaidi/PrintingKit.git
```

If you prefer to not have external dependencies, you can also just copy the source code into your app.



## Getting started

The [online documentation][Documentation] has a [getting started][Getting-Started] guide that helps you get started with PrintingKit.

For instance, to print a PDF in SwiftUI, just do this:

```swift
struct MyView: View {

    var body: some View {
        Button("Print document") {
            let bundle = Bundle.main
            let url = bundle.url(forResource: "doc", withExtension: "pdf")
            let item = PrintItem.pdf(at: url)
            try? StandardPrinter().print(item)
        }
    }
}
```

You can also let your views implement `PrinterView` to make printing even easier.

For more information, see the [getting started][Getting-Started].



## Documentation

The [online documentation][Documentation] has more information, code examples, etc., and lets you overview the various parts of the library.



## Demo Application

The demo app lets you explore the library on iOS and macOS. To try it out, just open and run the `Demo` project.



## Support this library

I manage my various open-source projects in my free time and am really thankful for any help I can get from the community. 

You can sponsor this project on [GitHub Sponsors][Sponsors] or get in touch for paid support.



## Contact

Feel free to reach out if you have questions or if you want to contribute in any way:

* Website: [danielsaidi.com][Website]
* Mastodon: [@danielsaidi@mastodon.social][Mastodon]
* Twitter: [@danielsaidi][Twitter]
* E-mail: [daniel.saidi@gmail.com][Email]



## License

PrintingKit is available under the MIT license. See the [LICENSE][License] file for more info.



[Email]: mailto:daniel.saidi@gmail.com
[Website]: https://www.danielsaidi.com
[Twitter]: https://www.twitter.com/danielsaidi
[Mastodon]: https://mastodon.social/@danielsaidi
[Sponsors]: https://github.com/sponsors/danielsaidi

[Documentation]: https://danielsaidi.github.io/PrintingKit/documentation/printingkit/
[Getting-Started]: https://danielsaidi.github.io/PrintingKit/documentation/printingkit/getting-started
[License]: https://github.com/danielsaidi/PrintingKit/blob/master/LICENSE
