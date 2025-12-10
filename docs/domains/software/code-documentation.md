---
title: Code Documentation
description: Writing effective documentation within source code.
---

# Code Documentation

Code documentation lives alongside the code it describes. Good code documentation helps developers understand, maintain, and extend software.

## Types of Code Documentation

### Comments

Inline explanations within code:

```python
# Calculate the compound interest
# Formula: A = P(1 + r/n)^(nt)
def calculate_interest(principal, rate, time, compounds_per_year):
    return principal * (1 + rate / compounds_per_year) ** (compounds_per_year * time)
```

### Docstrings

Structured documentation for functions, classes, and modules:

```python
def calculate_interest(principal, rate, time, compounds_per_year=12):
    """Calculate compound interest over a period.

    Args:
        principal: Initial investment amount.
        rate: Annual interest rate as a decimal (e.g., 0.05 for 5%).
        time: Investment period in years.
        compounds_per_year: Number of times interest compounds per year.
            Defaults to 12 (monthly).

    Returns:
        The final amount after compound interest.

    Raises:
        ValueError: If principal or rate is negative.

    Example:
        >>> calculate_interest(1000, 0.05, 10)
        1647.01
    """
```

### README Files

Project-level documentation:

```markdown
# Project Name

Brief description of what the project does.

## Installation

pip install project-name

## Usage

from project import Client
client = Client()
result = client.process("data")

## Contributing

See CONTRIBUTING.md for guidelines.

## License

MIT License
```

## When to Comment

### Good Reasons to Comment

**Explain why, not what:**

```python
# Use binary search because the list is always sorted
# and can contain millions of items
index = binary_search(items, target)
```

**Document non-obvious behavior:**

```python
# Sleep briefly to avoid rate limiting from the API
# The API allows 100 requests per minute
time.sleep(0.6)
```

**Clarify complex algorithms:**

```python
# Dijkstra's algorithm for finding shortest path
# Time complexity: O((V + E) log V) with binary heap
```

**Note workarounds:**

```python
# Workaround for bug in library v2.3.1
# TODO: Remove after upgrading to v2.4.0
```

### When Not to Comment

**Don't state the obvious:**

```python
# Bad: Increment counter by one
counter += 1

# Bad: Check if user is admin
if user.is_admin:
```

**Don't compensate for bad names:**

```python
# Bad
x = 86400  # Number of seconds in a day

# Good
SECONDS_PER_DAY = 86400
```

## Docstring Standards

### Python (Google Style)

```python
def fetch_user(user_id, include_deleted=False):
    """Fetch a user by their ID.

    Retrieves user information from the database. Optionally
    includes soft-deleted users.

    Args:
        user_id: The unique identifier for the user.
        include_deleted: If True, include soft-deleted users.
            Defaults to False.

    Returns:
        A User object containing the user's information.
        Returns None if no user is found.

    Raises:
        DatabaseError: If the database connection fails.
        ValidationError: If user_id is not a valid format.
    """
```

### JavaScript (JSDoc)

```javascript
/**
 * Fetch a user by their ID.
 *
 * @param {string} userId - The unique identifier for the user.
 * @param {Object} [options] - Optional parameters.
 * @param {boolean} [options.includeDeleted=false] - Include deleted users.
 * @returns {Promise<User|null>} The user object or null if not found.
 * @throws {DatabaseError} If the database connection fails.
 *
 * @example
 * const user = await fetchUser('usr_123');
 * console.log(user.name);
 */
async function fetchUser(userId, options = {}) {
```

### TypeScript

```typescript
/**
 * Configuration options for the API client.
 */
interface ClientConfig {
  /** API key for authentication. */
  apiKey: string;

  /** Base URL for API requests. Defaults to production. */
  baseUrl?: string;

  /** Request timeout in milliseconds. */
  timeout?: number;
}

/**
 * Creates a new API client instance.
 *
 * @param config - Client configuration options.
 * @returns A configured API client.
 *
 * @example
 * ```ts
 * const client = createClient({ apiKey: 'your-key' });
 * ```
 */
function createClient(config: ClientConfig): ApiClient {
```

## Class Documentation

### Document the Class Purpose

```python
class OrderProcessor:
    """Processes customer orders through the fulfillment pipeline.

    This class handles order validation, inventory checks, payment
    processing, and fulfillment scheduling. It coordinates between
    multiple services to ensure orders are processed correctly.

    Attributes:
        inventory_service: Service for checking product availability.
        payment_service: Service for processing payments.
        notification_service: Service for sending customer updates.

    Example:
        processor = OrderProcessor(
            inventory_service=InventoryService(),
            payment_service=PaymentService(),
            notification_service=NotificationService()
        )
        result = processor.process(order)
    """
```

### Document Public Methods

```python
def process(self, order):
    """Process an order through the fulfillment pipeline.

    Validates the order, checks inventory, processes payment,
    and schedules fulfillment. Sends notifications at each stage.

    Args:
        order: The Order object to process.

    Returns:
        ProcessingResult with status and tracking information.

    Raises:
        InsufficientInventoryError: If items are out of stock.
        PaymentDeclinedError: If payment processing fails.
        ValidationError: If order data is invalid.
    """
```

## README Best Practices

### Essential Sections

```markdown
# Project Name

One-line description of what the project does.

## Features

- Feature one
- Feature two
- Feature three

## Installation

How to install the project.

## Quick Start

Minimal example to get started.

## Documentation

Link to full documentation.

## Contributing

How to contribute to the project.

## License

License information.
```

### Make It Scannable

- Use headings and sections
- Include code examples
- Add badges for build status, version
- Keep paragraphs short

## Generating Documentation

### Tools

- **Sphinx**: Python documentation generator
- **JSDoc**: JavaScript documentation
- **TypeDoc**: TypeScript documentation
- **Doxygen**: Multi-language support
- **Godoc**: Go documentation

### Documentation as Code

```yaml
# Generate docs on every commit
name: Generate Docs
on: [push]
jobs:
  docs:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: pip install sphinx
      - run: sphinx-build docs/ _build/
      - uses: actions/deploy-pages@v2
```

## Summary

Effective code documentation:

- Explains why, not just what
- Follows consistent standards
- Documents public interfaces thoroughly
- Stays current with code changes
- Generates reference documentation automatically

Good code documentation makes software maintainable and helps developers work effectively.
