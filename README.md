# PostHog Go Library

![PostHog Go](https://img.shields.io/badge/PostHog-Go-orange)

Welcome to the **PostHog Go Library**! This repository provides an official Go library for event tracking, experimentation, and feature flags with PostHog. 

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Introduction

PostHog is an open-source product analytics platform that helps teams understand user behavior. The Go library allows developers to easily integrate PostHog into their Go applications. With this library, you can track events, conduct experiments, and manage feature flags seamlessly.

## Features

- **Event Tracking**: Capture user interactions and events with ease.
- **Feature Flags**: Control the rollout of features to specific user segments.
- **Experiments**: Run A/B tests to optimize user experience.
- **Lightweight**: Designed for performance and minimal overhead.
- **Easy Integration**: Simple setup process for quick implementation.

## Installation

To install the PostHog Go library, use the following command:

```bash
go get github.com/nikesh-rajbhandari/posthog-go
```

## Usage

To use the PostHog Go library, you need to initialize it with your PostHog API key. Here’s a basic example:

```go
package main

import (
    "github.com/nikesh-rajbhandari/posthog-go"
)

func main() {
    client := posthog.New("YOUR_POSTHOG_API_KEY")

    // Track an event
    client.Track("user_signed_up", map[string]interface{}{
        "plan": "pro",
    })
}
```

## Examples

Here are some common use cases for the PostHog Go library:

### Tracking Events

To track an event, use the `Track` method. Here’s an example:

```go
client.Track("button_clicked", map[string]interface{}{
    "button_name": "signup",
})
```

### Using Feature Flags

To check if a feature is enabled for a user, use the `IsFeatureEnabled` method:

```go
enabled := client.IsFeatureEnabled("new_dashboard", userID)
if enabled {
    // Show the new dashboard
}
```

### Running Experiments

You can run experiments by assigning users to different variants:

```go
variant := client.GetVariant("homepage_experiment", userID)
if variant == "control" {
    // Show control variant
} else {
    // Show experimental variant
}
```

## Contributing

We welcome contributions to the PostHog Go library! To get started:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Submit a pull request with a clear description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

For the latest updates and versions, please visit our [Releases](https://github.com/nikesh-rajbhandari/posthog-go/releases) section. You can download the latest release and execute it as needed.

For further details, check the [Releases](https://github.com/nikesh-rajbhandari/posthog-go/releases) section.

---

Thank you for using the PostHog Go library! We hope it enhances your product analytics experience.