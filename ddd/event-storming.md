# Event storming

Event storming is a technic used withing DDD to brainstorm ideas and discover the domain.

It also allow developper to understand the domain, because each developer comes with its own understanding of the domain.

## How to
According to Khalil Stemmler in his SOLID book.

# Step 0 
Define the legend for the following items:
- Domain event, (Orange)
- Command, (Blue)
- Aggregates, (Yellow)
- Issues, (Red)
- Actor/Roles, (Yellow)
- Views, (Green)
- Bounded context, (Pink + circle)
- Subdomain, (Pink + circle dashed)
- Event flow, (Arrows)

# Step 1 Event storm
Chronologically map of the story of the business logic in events (Orange stickers)

It should be written in a way that is accessible to non-technical folks.

- Domain events are past tensed, such as AccountCreated

- Alternative/Parallel event can be placed vertically.

// ? What is a process?

# Step 2 Command
For each event, write the associated command.

# Step 3 Aggregate