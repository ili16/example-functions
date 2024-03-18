# Technical Debt

In this section, we'll examine different types of technical debt present in our codebase.

## Task 1: Find technical flaws in the following function
1. Use a custom prompt
2. Select a pre-defined prompt

```Java
public class ShoppingCart {

    private List<Item> items;

    // Constructor
    public ShoppingCart() {
        this.items = new ArrayList<>();
    }

    // Method to add item to cart
    public void addItem(Item item) {
        this.items.add(item);
    }

    // Method to calculate total price
    public double calculateTotalPrice() {
        double totalPrice = 0.0;
        for (Item item : items) {
            totalPrice += item.getPrice();
        }
        return totalPrice;
    }

    // Method to apply discount
    public void applyDiscount(double discountPercentage) {
        for (Item item : items) {
            double discountedPrice = item.getPrice() * (1 - discountPercentage / 100);
            item.setPrice(discountedPrice);
        }
    }

    // Getter for items
    public List<Item> getItems() {
        return items;
    }

    // Setter for items
    public void setItems(List<Item> items) {
        this.items = items;
    }
}
```

## Task 2: Find technical flaws in the following function
1. Use a custom prompt
2. Select a pre-defined prompt

```Javascript
class User {
    constructor(name, email) {
        this.name = name;
        this.email = email;
        this.isLoggedIn = false;
    }

    login() {
        // Simulate login process
        this.isLoggedIn = true;
        console.log(`${this.name} logged in.`);
    }

    logout() {
        // Simulate logout process
        this.isLoggedIn = false;
        console.log(`${this.name} logged out.`);
    }

    sendEmail(subject, message) {
        // Simulate sending email
        if (this.isLoggedIn) {
            console.log(`Email sent to ${this.email}: ${subject} - ${message}`);
        } else {
            console.log(`User ${this.name} is not logged in. Cannot send email.`);
        }
    }

    // Function to check if user is logged in
    isLoggedIn() {
        return this.isLoggedIn;
    }

    // Function to update user's email
    updateEmail(newEmail) {
        this.email = newEmail;
    }
}

// Usage
const user1 = new User('Alice', 'alice@example.com');
user1.login();
user1.sendEmail('Hello', 'This is a test email.');
```

While writing code is the most metioned and upfront task of a developer, it's just a subset of the necessary process to deliver software to a customer. Let's look at this example of a Makefile.

#### Task 3: Find out what this Makefile accomplishes and why its bad

```Makefile
.PHONY: clean-pyc develop lint-server lint-client lint-docs lint format-server format-client format test coverage

help:
	@echo "clean-pyc - remove Python file artifacts"
	@echo "develop - install development dependencies"
	@echo "lint - check style with black, ruff, sort python with ruff, indent html, and lint frontend css/js"
	@echo "format - enforce a consistent code style across the codebase, sort python files with ruff and fix frontend css/js"
	@echo "test - run tests"
	@echo "coverage - check code coverage"

clean-pyc:
	find . -name '*.pyc' -exec rm -f {} +
	find . -name '*.pyo' -exec rm -f {} +
	find . -name '*~' -exec rm -f {} +

develop: clean-pyc
	pip install -e .[testing,docs]
	npm install --no-save && npm run build

lint-server:
	black --target-version py37 --check --diff .
	ruff check .
	semgrep --config .semgrep.yml --error .
	curlylint --parse-only wagtail
	git ls-files '*.html' | xargs djhtml --check

lint-client:
	npm run lint:css --silent
	npm run lint:js --silent
	npm run lint:format --silent

lint-docs:
	doc8 docs

lint: lint-server lint-client lint-docs

format-server:
	black --target-version py37 .
	ruff check . --fix
	git ls-files '*.html' | xargs djhtml -i

format-client:
	npm run format
	npm run fix:js

format: format-server format-client

test:
	python runtests.py

coverage:
	coverage run --source wagtail runtests.py
	coverage report -m
	coverage html
	open coverage_html_report/index.html
```