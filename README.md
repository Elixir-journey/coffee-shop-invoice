# Coffee shop invoicing

![Build Status](https://github.com/Elixir-journey/coffee-shop-invoice/actions/workflows/ci.yml/badge.svg)
![Code Style](https://img.shields.io/badge/style-credo-green)
![License](https://img.shields.io/github/license/Elixir-journey/coffee-shop-invoice)

An Elixir-based inventory and invoicing system that simulates processing customer orders in a coffee shop until the inventory is depleted. An interview challenge inspires this project and serves as a case study in Elixir software design, with features such as inventory management, order validation, and real-time billing.

## Features to implement

- Dynamic inventory setup: defining various item types (Donuts, Bagels, Pastries, etc.) with attributes like name, price, size, and quantity. As a bonus, set up a randomized initial inventory to simulate a live coffee shop environment.
- Order validation: Check if each requested item exists in the inventory and whether there’s sufficient stock.
- Unsupported items message: Flag any items not present in the inventory with a clear message for the customer.
- Volume Check: Ensure the requested quantity doesn’t exceed available stock, allowing partial fulfillment or a clear message if the order cannot be met.
- Invoicing & billing: Calculate the bill's total for each order based on the price and requested quantities.
- Adjust inventory quantities as items are "sold."
- Return a detailed bill with each item’s price, total cost, and total.
- Inventory management: Notify when items are out of stock or low in quantity, preventing further sales of unavailable items.

Running this as a CLI app would give it an interactive, real-world feel, allowing a user (or even a test script) to process customer orders and see inventory updates in real-time.

## Getting Started

This project uses the [Elixir kickoff](https://github.com/Elixir-journey/elixir-kickoff) template to handle developer setup such as Docker containerization, devcontainers, or setting up a CI pipeline with GitHub Actions.

### Prerequisites
- [Elixir and Erlang](https://elixir-lang.org/install.html): Install Elixir to run the project.
- [Docker](https://docs.docker.com/engine/install/) (optional): Install Docker if you wish to use the Docker setup.
- [Visual Studio Code](https://code.visualstudio.com/download) with Remote - [Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) (optional): For development in a devcontainer.

## Development

### Provided setup with [repository template](https://github.com/Elixir-journey/elixir-kickoff)

This project includes a set of tools to ensure code quality and consistency. These tools are configured to run automatically on save, giving you immediate feedback as you work.

1. Code formatting with [Elixir Formatter](https://hexdocs.pm/mix/main/Mix.Tasks.Format.html)

It ensures any code follows a consistent style. The Elixir Formatter is set to run automatically on save, formatting your code to follow standard Elixir conventions.

The .formatter.exs file controls settings, and auto-formatting is enabled in .vscode/settings.json.

2. Linting with [Credo](https://hexdocs.pm/credo/overview.html)

It enforces best practices and code consistency by highlighting potential readability and maintainability issues. Credo runs automatically on save through ElixirLS, displaying warnings and suggestions directly in the editor. You can also run ```mix credo``` in the terminal for a complete linting check.

3. Type Checking and Error Reporting with [Dialyzer](https://www.erlang.org/doc/apps/dialyzer/dialyzer_chapter.html)

It analyzes code for type errors and potential bugs, offering an additional layer of safety. Dialyzer is integrated with ElixirLS, running in the background and reporting issues as you work.
The initial setup may take a few minutes as it builds a PLT (Persistent Lookup Table) with necessary type information.

### Development with devcontainer

For an easy and consistent development environment, you can use the provided .devcontainer setup.

1. Open the Project in Visual Studio Code:
    - Make sure the Remote - Containers extension is installed.
    - Open the project folder in VS Code.
2. Reopen in Container:
    - VS Code will detect the .devcontainer configuration and prompt you to "Reopen in Container." This sets up a Docker-based development environment tailored for Elixir.
3. Development:
    - With the container running, you can work on the project without worrying about local dependencies.
    - Run commands like mix test to ensure tests pass or iex -S mix to interact with the application.

#### Customization and configuration

The Dev Container uses a pre-built Docker image for faster setup and consistent environments across all sessions. The image is hosted on GitHub Container Registry at [ghcr.io/elixir-journey/elixir-kickoff:latest](https://github.com/orgs/Elixir-journey/packages/container/package/elixir-kickoff).

Extensions: The following VS Code extensions are automatically installed:
- Elixir Language Server (Elixir LS)
- Docker
- GitLens
- Spell Checker
- Prettier (for code formatting)
- Material Icon Theme

You can modify the .devcontainer/devcontainer.json file to add extensions or dependencies.

#### Code style & editor configuration
This project uses an .editorconfig file to ensure consistent coding standards across different editors and environments. The .editorconfig file helps maintain consistent formatting for:

- Indentation: Spaces with a width of 4.
- Line endings: LF (Line Feed) for cross-platform compatibility.
- Trimming trailing whitespace and final newline insertion for cleaner diffs.

##### How It Works

If you’re using Visual Studio Code or another modern editor, the settings will be applied automatically if you have [EditorConfig support](https://editorconfig.org). The VS Code Dev Container setup includes this support by default, so no extra setup is needed.

### Development without devcontainer

1. Clone the repository:

```bash
git clone https://github.com/Elixir-journey/coffee-shop-invoicing.git
cd coffee-shop-invoicing
```

2. Install dependencies:

```bash
mix deps.get
```

3. Open your favorite editor (ex: VS Code)

## Running the application

### With Docker

A Dockerfile is included to run the app in an isolated container.

1. Build the Docker image:
```bash
docker build -t coffee-shop-invoicing .
```

2. Run the Docker container:

```bash
docker run -it coffee-shop-invoicing
```

This command runs the app interactively, allowing you to use the CLI within the container.

### Without Docker

1. Run the app in iex:
```bash
iex -S mix
```

2. Start the CLI app:

```bash
CoffeeShopCLI.run()
```

## Development Notes

- Environment Variables: Use .env files to manage environment variables. Make sure they are listed in .gitignore to keep sensitive information secure.
- Linting and Formatting: Run Credo for linting and mix format to ensure code consistency.
Contributing

## Contributing
Feel free to submit a pull request or open an issue if you have suggestions for improvement.
