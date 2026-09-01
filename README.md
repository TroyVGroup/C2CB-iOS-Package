#C2CB iOS Library (C2C Icons SDK)

C2CB iOS Library provides a simple and reusable UI component for integrating Click-to-Contact (C2C) features in your iOS app.

It includes ready-to-use icons for:

📞 Call
💬 SMS
📧 Email

These icons can be easily embedded into any screen and connected with your backend (e.g., Twilio or custom APIs).

# Installation


# 1. Swift Package Manager (SPM)

Add the package:

https://github.com/Satyam-ios/C2CB_Package.git
✅ SwiftUI Usage Example
VStack {
    Text("C2C Icons")
        .font(.headline)

    CustomIconsRowView()
        .frame(width: 120, height: 35)
}
struct CustomIconsRowView: UIViewRepresentable {
    func makeUIView(context: Context) -> C2CSdkCustomView {
        let view = C2CSdkCustomView()
        view.channel_id = "6a1847342952bf18bc9a081f"
        view.frame = CGRect(x: 0, y: 0, width: 120, height: 40)
        return view
    }

    func updateUIView(_ uiView: C2CSdkCustomView, context: Context) {
        // Update logic if needed
    }
}





# 2. CocoaPods Installation

Add the following to your Podfile:

pod 'C2CB-iOS-Library', '~> 4.0'

Then run:

pod install
🛠️ UIKit Integration
🔹 Import Library
import C2CB_iOS_Library
🔹 Add UIView in Storyboard
Drag a UIView
Set size (Width: 120, Height: 40)
🔹 Assign Class & Module
Class: C2CSdkCustomView
Module: C2CB_iOS_Library
🔹 Connect IBOutlet
@IBOutlet weak var c2cEmbbedIcons: C2CSdkCustomView!
🔹 Configure in viewDidLoad()
override func viewDidLoad() {
    super.viewDidLoad()
    
    c2cEmbbedIcons.channel_id = "<Enter your channel id>"
}
 Summary
Supports SwiftUI + UIKit
Easy integration via SPM / CocoaPods
Displays Call, SMS, Email (C2C icons)
Requires only channel_id to configure
