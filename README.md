# EcoCash Android Library

An easy-to-use Android library for integrating **EcoCash mobile payments** into your Android applications.  
This library simplifies initiating payments, handling callbacks, and managing transaction states when working with the EcoCash API.

---

## ✨ Features

- Simple EcoCash payment initiation
- Clean API for transaction requests
- Callback handling for success, failure, and pending states
- Lightweight and easy to integrate
- Kotlin & Java compatible
- Ready for production and sandbox environments

---

## 📦 Installation

### Using JitPack

1. Add JitPack to your root `build.gradle`:

```gradle
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}


dependencies {
    implementation "com.github.isheunesutembo:ecocash-library:1.0.0"
}


## 🚀 Getting Started
### Initialize the Library
EcoCash.initialize(
    context = this,
    merchantId = "YOUR_MERCHANT_ID",
    merchantKey = "YOUR_MERCHANT_KEY",
    environment = EcoCashEnvironment.SANDBOX // or EcoCashEnvironment.PRODUCTION
)

EcoCash.requestPayment(
    amount = 10.0,
    phoneNumber = "0771234567",
    reference = "ORDER_12345",
    description = "Payment for order #12345",
    callback = object : EcoCashCallback {
        override fun onSuccess(transactionId: String) {
            // Payment successful
        }

        override fun onPending() {
            // Payment pending user confirmation
        }

        override fun onFailure(error: String) {
            // Payment failed
        }
    }
)

🔁 Handling Callbacks

The library handles most of the EcoCash API complexity internally, but you should:

Log all transaction states

Store transaction references in your database

Handle retries for pending transactions

⚙️ Configuration
Parameter	Description
merchantId	Your EcoCash merchant ID
merchantKey	Your EcoCash API secret key
environment	SANDBOX or PRODUCTION
🛡️ Permissions

Add the following permission to your AndroidManifest.xml:

<uses-permission android:name="android.permission.INTERNET" />

🧪 Testing

Always use the sandbox environment during development:

EcoCashEnvironment.SANDBOX


Switch to production only after your integration is fully tested.

📌 Versioning

This project follows Semantic Versioning:

MAJOR.MINOR.PATCH


Example:

1.0.0

📄 License
MIT License

Copyright (c) 2026 Isheunesu Tembo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...


(You may replace this with Apache 2.0 if preferred.)

🤝 Contributing

Contributions are welcome and appreciated!

Fork the repository

Create your feature branch

git checkout -b feature/my-feature


Commit your changes

git commit -m "Add new feature"


Push to your branch

git push origin feature/my-feature


Open a Pull Request

📞 Support

For bugs, feature requests, or improvements:

Open an issue on GitHub

Or contact: your-email@example.com

🌍 Why EcoCash Library?

EcoCash is widely used in Zimbabwe and surrounding regions.
This library aims to make EcoCash integration as simple and developer-friendly as modern payment SDKs like Stripe or PayPal.

Built with ❤️ by Isheunesu Tembo
