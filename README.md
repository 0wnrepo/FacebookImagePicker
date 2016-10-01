# GBHFacebookImagePicker

[![CI Status](http://img.shields.io/travis/Florian Gabach/GBHFacebookImagePicker.svg?style=flat)](https://travis-ci.org/Florian Gabach/GBHFacebookImagePicker)
[![Version](https://img.shields.io/cocoapods/v/GBHFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/GBHFacebookImagePicker)
[![License](https://img.shields.io/cocoapods/l/GBHFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/GBHFacebookImagePicker)
[![Platform](https://img.shields.io/cocoapods/p/GBHFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/GBHFacebookImagePicker)

- [🗝 Features](#features)
- [⤵️ Installation](#installation)
- [🛠 Usage](#usage)
- [👓 Translation](#translation)

## Screenshot

![Preview](https://github.com/terflogag/GBHFacebookImagePicker/raw/master/preview.png)

## Features 

- Login with Facebook SDK and display user's Albums
- Display pictures of each albums 
- Handling denied photo's access 
- Select and get URL of the picked picture 

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

* Xcode 8 
* iOS 9.0+ target deployment
* FBSDKCoreKit, FBSDKLoginKit (>= 4.0)

## Installation

GBHFacebookImagePicker is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "GBHFacebookImagePicker"
```

## Usage

You need to have set up your application correctly to work with Facebook : https://developers.facebook.com/docs/ios/getting-started

Then, implement the `GBHFacebookImagePickerDelegate` protocol:

```
// MARK: - GBHFacebookImagePicker Protocol

func facebookImagePicker(imagePicker: UIViewController, didSelectImageWithUrl url: String) {
    imagePicker.dismiss(animated: true, completion: nil)

    print("Image URL : \(url)")
}

func facebookImagePicker(imagePicker: UIViewController, didFailWithError error: Error?) {
    print(error.debugDescription)
}

func facebookImagePicker(didCancelled imagePicker: UIViewController) {
    print("Cancelled Facebook Album picker")
}
```

Display picker : 

```
let albumPicker = GBHFacebookImagePicker()
albumPicker.delegate = self
let navi = UINavigationController(rootViewController: albumPicker)
self.present(navi, animated: true)
```

## Translation 

GBHFacebookImagePicker is currently write in english. If you need translation for the permission popup (or whatever thing), just add this line in your localized file  :

```
"Pictures" = "<your_translation>";
"Oups" = "<your_translation>";
"You need to allow photo's permission." =  "<your_translation>";
"Allow" = "<your_translation>";
"Close" = "<your_translation>";
```

## Author

Florian Gabach, contact@floriangabach.fr

## License

GBHFacebookImagePicker is available under the MIT license. See the LICENSE file for more info.
