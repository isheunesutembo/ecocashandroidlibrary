# 💳 EcoCash Android Library

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

name: "EcoCash Android SDK"
description: |
  A simple Android SDK for integrating EcoCash C2B (Customer-to-Business) Payments 
  into your mobile applications. Supports both Sandbox and Live environments.

features:
  - "Easy initialization with API Key"
  - "Built-in support for Sandbox and Live environments"
  - "Asynchronous network calls using OkHttp"
  - "Callback-based success & error handling"

installation:
  option1_local_maven:
    repositories: |
      repositories {
          mavenLocal()
          google()
          mavenCentral()
      }
    dependency: |
      dependencies {
          implementation "com.github.yourusername:ecocashsdk:1.0.0"
      }
  option2_jitpack:
    step1_add_repo: |
      dependencyResolutionManagement {
          repositories {
              maven { url 'https://jitpack.io' }
              google()
              mavenCentral()
          }
      }
    step2_add_dependency: |
      dependencies {
          implementation 'com.github.yourusername:EcoCashSDK:1.0.0'
      }

usage:
  init_sdk: |
    EcoCash.init(
        key = "YOUR_API_KEY",
        environment = EcoCash.Environment.SANDBOX // or LIVE
    )
  make_payment: |
    EcoCash.makePayment(
        customerMsisdn = "263771234567",
        amount = 10.0,
        reason = "Payment for Order",
        currency = "USD",
        sourceReference = "ORDER123",
        callback = object : EcoCash.PaymentCallback {
            override fun onSuccess(response: String) {
                Log.d("EcoCash", "Payment success: $response")
            }

            override fun onError(error: PaymentError) {
                Log.e("EcoCash", "Payment failed: $error")
            }
        }
    )

environments:
  sandbox: "EcoCash.init(\"YOUR_API_KEY\", EcoCash.Environment.SANDBOX)"
  live: "EcoCash.init(\"YOUR_API_KEY\", EcoCash.Environment.LIVE)"

error_handling:
  description: |
    The SDK provides structured error handling via the PaymentError class:
  types:
    - "NetworkError → No internet / request failure"
    - "ServerError → API responded with an error code"

requirements:
  - "Android 5.0 (API 21) or higher"
  - "Kotlin 1.8+"
  - "OkHttp"

contributing: |
  Pull requests are welcome! For major changes, please open an issue first 
  to discuss what you would like to change.

license: "MIT License"


Built with ❤️ by Isheunesu Tembo
