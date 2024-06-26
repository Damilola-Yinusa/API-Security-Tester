
---

# API Security Tester

This project provides a framework to test APIs for various security vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), Insecure Direct Object References (IDOR), and Rate Limiting. It also supports testing endpoints that require authentication and logging for debugging and auditing purposes.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Running Tests](#running-tests)
- [Contributing](#contributing)
- [License](#license)

## Features

- **SQL Injection Testing**: Detects SQL injection vulnerabilities.
- **Cross-Site Scripting (XSS) Testing**: Detects XSS vulnerabilities.
- **Insecure Direct Object References (IDOR) Testing**: Detects IDOR vulnerabilities.
- **Rate Limiting Testing**: Checks for rate limiting vulnerabilities.
- **Authentication Support**: Supports APIs that require authentication tokens or keys.
- **Logging**: Logs test results for debugging and audit trails.
- **Configuration Management**: Supports complex scenarios and endpoints through a configuration file.

## Prerequisites

- Python 3.6+
- `requests` library
- `unittest` module (comes with the standard Python library)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/api-security-tester.git
cd api-security-tester
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. **Configuration**: Update the `config.json` file with your API endpoints and authentication details.

2. **Run Tests**: Use the following command to run the tests:

```bash
python -m unittest discover -s tests
```

## Configuration

The configuration file (`config.json`) should be structured as follows:

```json
{
    "base_url": "https://jsonplaceholder.typicode.com",
    "endpoints": [
        {
            "path": "/posts",
            "methods": ["GET", "POST", "PUT", "DELETE"],
            "vulnerability_tests": ["sql_injection", "xss", "idor", "rate_limiting"]
        }
    ],
    "auth": {
        "type": "Bearer",
        "token": "your-auth-token"
    }
}
```

- `base_url`: The base URL of the API you are testing.
- `endpoints`: A list of endpoints to be tested, including the path, methods, and the types of vulnerability tests to perform.
- `auth`: Authentication details, if required by the API.

## Running Tests

To run the tests, use the following command:

```bash
python -m unittest discover -s tests
```

This will discover and run all tests defined in the `tests` directory.

## Contributing

We welcome contributions! Please read our [contributing guidelines](CONTRIBUTING.md) for more information.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

