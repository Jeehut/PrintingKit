# Getting Started

This article explains how to get started with PrintingKit.


## Overview

PrintingKit helps you print PDF documents and other items in Swift and SwiftUI.

For instance, to print a PDF in SwiftUI, just do this:

```swift
struct MyView: View {

    var body: some View {
        Button("Print document") {
            let bundle = Bundle.main
            let url = bundle.url(forResource: "doc", withExtension: "pdf")
            let item = PrintItem.pdfFile(at: url)
            try? StandardPrinter().print(item)
        }
    }
}
```

You can also let your views implement ``PrinterView`` to make printing even easier.

For instance, you don't have to specify a ``Printer``:

```swift
struct MyView: View, PrinterView {

    var body: some View {
        Button("Print image") {
            let bundle = Bundle.main
            let url = bundle.url(forResource: "img", withExtension: "jpg")
            try? printItem(.imageFile(at: url))
        }.disabled(!canPrintImages())
    }
}
```

More view-specific functionality may be added in the future.


## Available item types

PrintingKit currently supports the following print item types:

* ``PrintItem/attributedString(_:configuration:)`` - an attributed string.
* ``PrintItem/imageData(_:)`` - JPG or PNG data.
* ``PrintItem/imageFile(at:)`` - a JPG or PNG file at a certain URL.
* ``PrintItem/pdfData(_:)`` - PDF document data.
* ``PrintItem/pdfFile(at:)`` - a PDF document file at a certain URL.
* ``PrintItem/string(_:configuration:)`` - a plain string.
* ``PrintItem/view(_:withScale:)`` - any SwiftUI view.

Note that some items currently can't be printed on some platforms.


## Checking printing capabilities

A ``Printer`` provides information about which items it can print.

For instance, you can use ``Printer/canPrint(_:)`` to see if the printer can print a certain item, as well as ``Printer/canPrintImages`` and  ``Printer/canPrintViews`` to see if it can print images and views.

A ``PrinterView`` lets you check this even easier, without having to provide a printer.
