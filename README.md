# playwright_dotnet

End-to-end test automation project using [Playwright](https://playwright.dev/dotnet/) with .NET 9.

## Structure

- **Pages/**: Page Objects (POM)
- **e2e/**: End-to-end tests
- **Fixtures/**: Fixtures for browser/context reuse
- **setup**: Environment variables (URL, user, password)
- **Utils**: Utilities for data generation

## Prerequisites

- [.NET 9 SDK](https://dotnet.microsoft.com/download)
- [Node.js](https://nodejs.org/) (optional, only if you want to run Playwright CLI JS)
- VS Code with **C#** or **C# Dev Kit** extension (recommended)

## Setup

1. **Clone the repository**

2. **Restore dependencies:**
    ```
    dotnet restore
    ```

3. **Install the Playwright CLI for .NET (if necessary):**
    ```
    dotnet tool install --global Microsoft.Playwright.CLI
    ```

4. **Install Playwright browsers:**
    ```
    dotnet playwright install
    ```

## How to run the tests

1. **Run tests in debug mode for creation**
    ```
    PWDEBUG=1 dotnet test
    ```

2. **Run all tests:**
    ```
    dotnet test
    ```

## Notes

- The tests use variables from the `.env` file for environment, user, and password.
- The authentication state is saved in `auth.json` and can be reused in other tests to start already logged in.
- Browser creation is centralized via fixture to facilitate maintenance and browser switching.

## Example structure

```
PlaywrightTests/
├── Pages/
│   └── HomePage.cs
├── e2e/
│   ├── AuthSetup.cs
│   └── HomePageTests.cs
├── Fixtures/
│   └── BrowserFixture.cs
├── setup/.env
├── playwright_dotnet.sln
└── README.md
```

---

**Questions?**  
Open an issue or check the official documentation.