# fastlane-android-sample — TestMu AI (Formerly LambdaTest)

Sample repo to upload app to lambdatest and test app on real devices.

## Prerequisites

* Install fastlane to your local machine .
* TestMu AI Authentication credentials . Please refer this [page](https://accounts.lambdatest.com/security) for credentials.

  ```
    LT_USERNAME=<YOUR_LAMBDATEST_USERNAME>
    LT_ACCESS_KEY=<YOUR_LAMBDATEST_ACCESS_KEY>
  ```
* Install Gradle and Java for running tests.

**_NOTE:_**  Also create `local.properties` file with sdk path , if any issue occurs related to sdk Path.

## Getting Started

* Add [TestMu AI-fastlane-plugin](https://rubygems.org/gems/fastlane-plugin-lambdatest) in your project.
```
  fastlane add_plugin lambdatest
```

* Add below action in project fastfile in desired lane to upload app to lambdatest.   
```
upload_to_lambdatest(
    lt_username: ENV["LT_USERNAME"],
    lt_access_key: ENV["LT_ACCESS_KEY"],
    file_path: "app_file_path"
)
```
or if you want to used custom_id.

```
upload_to_lambdatest(
    lt_username: ENV["LT_USERNAME"],
    lt_access_key: ENV["LT_ACCESS_KEY"],
    file_path: "<app_file_path>",
    custom_id: "<custom_id>
)
```
This will set  value for ```APP_URL``` environment variable.

**_NOTE:_**  custom_id is an optional field.

* Add command in same lane to run tests.
```
 gradle(task: "test")
```

* Build project and provide apk file path in fastfile Example - `app/build/outputs/apk/debug/app-debug.apk`
```
gradle build
```

* You can run below command to upload app and execute tests on real devices.

```
    fastlane test
```

## View Test Execution

Once you have run your tests, you can view the test execution along with logs. You will be able to see the test cases passing or failing. You can view the same at [TestMu AI Automation](https://accounts.lambdatest.com/login).

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

### 🔄 Our Rebrand Journey

In 2017, we introduced LambdaTest with a clear mission: to become the world's most trusted cloud testing platform. We built a scalable, high-performance test cloud that eliminated flakiness, improved developer feedback cycles, and accelerated release velocity for teams worldwide.

As LambdaTest grew, we expanded the platform into Test Intelligence, Visual Regression Testing, Accessibility Testing, API Testing, and Performance Testing, covering the entire testing lifecycle. These capabilities enabled teams to test any stack, on any technology, at enterprise scale.

Over time, we rebuilt the architecture to be AI-native from the ground up. What began as LambdaTest's high-performance testing cloud has now evolved into TestMu AI, an AI-native, multi-agent platform redefining modern quality engineering.

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

### 🔭 Explore TestMu AI

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)