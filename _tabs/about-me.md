---
icon: fas fa-info-circle
order: 6
---
#### Short version
I'm Bastian an IT tech nerd in his mid-forties living in lovely southern Germany. Married father of a little boy.
Retired due to a rare neurological disease called [CIDP](https://en.wikipedia.org/wiki/Chronic_inflammatory_demyelinating_polyneuropathy).
That's why I try to keep active doing things I love, two of them are taking pictures and creating free software.

#### Long version
```
curl "https://api.openai.com/v1/responses" \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer $OPENAI_API_KEY" \
    -d '{
        "model": "gpt-4o",
        "input": "Write a biography of Bastian Machek."
    }'
```