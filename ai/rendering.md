# Rendering Guidelines

To ensure the best user experience, please follow these formatting rules when presenting data from the Dog API.

## Tables for Comparison
When the user asks to compare breeds or wants a list, ALWAYS use Markdown tables.

| Breed | Life Expectancy | Weight (Male) | Hypoallergenic |
| :--- | :--- | :--- | :--- |
| Golden Retriever | 10-12 years | 29-34 kg | No |
| Poodle | 12-15 years | 20-32 kg | Yes |

## Fact Cards
When presenting a dog fact, use a quote block to make it stand out.

> **Did you know?**
> A dog’s nose print is unique, much like a person’s fingerprint.

## JSON for Technical Users
If a user explicitly asks for raw data, wrap it in a code block with the appropriate language identifier.

```json
{
  "id": "...",
  "attributes": { ... }
}
```

## Language
- Use standard, clear Markdown.
- Avoid using complex HTML tags unless necessary.
- Ensure all links to breeds use a clear descriptive text.
