# Customer Management – Feature Scope & Design Decisions

The **Customers** page is one of the core components of the application. Its purpose is to provide a clean and intuitive interface for managing customer information while supporting the accounting functionality required throughout the system.

Rather than replicating Zoho Books, this application selectively adopts design patterns and features that provide meaningful value for a **basic-to-moderate accounting application**. The goal is to maintain a professional user experience without introducing unnecessary enterprise complexity.

---

# General Customer Information

>![[Zoho Books Customers Page Inspiration.png]]
>*(Original Zoho Books customer creation screenshot.)*

The first Zoho Books screenshot represents the **core customer information** that should exist within this application.

The information contained in this section is considered essential and will be implemented in the application. However, the layout itself **will not be copied directly**.

Instead, customer creation will follow the same design philosophy used throughout the application, particularly the **Items** page. This creates a consistent user experience by ensuring that all major management pages share a familiar structure.

The page layout will consist of:

- A customer creation form located at the top of the page.
- A customer list displayed beneath the form.
- A consistent visual style matching the rest of the application.

The objective is to preserve the functionality while presenting it through the application's own design language.

---

# Additional Customer Information

>![[Zoho Books Customers Page Inspiration 2.png]]
> *(Annotated screenshot showing the selected features and design decisions.)*

The second screenshot represents **additional customer-related functionality**. Unlike the first screenshot, **not every feature shown in Zoho Books will be implemented**.

Instead, only the functionality that meaningfully contributes to the project's scope will be included.

The annotated image illustrates the design decisions that will guide this implementation by highlighting certain features.

### Address

Although Zoho Books separates customer addresses into their own dedicated tab, this application intentionally chooses a simpler approach.

Rather than creating a separate Address tab, the essential billing address fields will be integrated directly into the main customer creation page.

This produces a cleaner workflow while still preserving the information necessary for invoices and customer records.

---

### Tax Rate

Tax Rate is considered an important part of customer configuration and will remain part of the customer creation process.

This allows invoices to automatically inherit the customer's default tax configuration whenever appropriate.

The same tax options in the items shall be used in here aswell.

---

### Payment Terms

Payment Terms will also remain part of the customer configuration.

Storing a customer's default payment terms allows invoices to automatically calculate due dates while accurately reflecting common business practices.

---

### Notes

Zoho Books refers to this field as **Remarks**.

Within this application, the feature will instead be named **Notes**.

The functionality remains the same: it serves as an internal area where users can record useful information about a customer that is not directly related to accounting calculations.

---

### Multi-language Support

Although the original Zoho Books interface presents customer currency configuration, this project takes a different approach.

The application **will support multiple interface languages**, including **Kurdish**, as multilingual support is considered an essential feature.

However, **multi-currency support is intentionally outside the scope of this project**.

Supporting exchange rates, currency conversion, and multi-currency accounting introduces significant accounting complexity without providing additional value for a portfolio demonstration. Therefore, the application will operate using a single currency while remaining architecturally clean and focused.