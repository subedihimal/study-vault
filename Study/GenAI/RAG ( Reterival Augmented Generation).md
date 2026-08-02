The technique in which the model first retrieves relevant information from a knowledge source and uses that information to generate an answer.
![[Pasted image 20260802093424.png]]

---
## Types of Data

| **Structured Data**                                           | **Unstructured Data**                                                     |
| ------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Has Fixed Fields.<br><br>Organized in tables rows and Columns | No any Fixed Fields<br><br>No any organizations                           |
| Example:<br>Employee Data<br>Ecommerce Orders<br>Sensor Logs  | Example:<br>Company Policy and Documents<br>Emails<br>Images<br>Audio<br> |

## Structured Data
**Example of converting a Image into structured data**

![[Pasted image 20260802100416.png]]
```json
{
  "location_type": "village",
  "objects": {
    "houses": {
      "count": 25,
      "type": "traditional"
    },
    "trees": {
      "count": 340
    },
    "roads": {
      "count": 1,
      "surface": "dirt"
    },
    "people": {
      "count": 12
    },
    "animals": {
      "cows": 5
    },
    "farmland": {
      "present": true,
      "area": "large"
    }
  },
  "environment": {
    "terrain": "mountainous",
    "weather": "clear",
    "vegetation": "green"
  }
}
```

### When to use Structured Data? 

**Use when you need exact facts, filtering, sorting, or calculations.**

- Data is stored in a fixed format (JSON, tables, SQL).
- Best for **"find by condition"** queries.

**Example:**

Image → JSON

```
{
  "type": "village",
  "houses": 25,
  "terrain": "mountainous",
  "has_road": true
}
```

Query:

> "Find villages with more than 20 houses"

---
## Vector Embedding

Vector Embedding are ==numbers that represent the meaning of unstructured data like text/ audio/ image== so similar meanings have similar numbers. The numbers are calculated using embedding models eg: openAI, microsoft and even open source are available.

### Similarity Search
Similarity search is when you find things that are most similar to a given input based on meaning, not exact words.

### When to use Vector Embedding

**Use when you need similarity search or understanding of meaning.**

- Data is converted into numerical vectors.
- Best for **"find something similar"** queries.

**Example:**

Image → Vector

```
[
  0.23,
 -0.51,
  0.78,
  ...
]
```

Query:

> "Find villages similar to this mountain village image"

The system finds similar villages based on **visual and semantic similarity**, even if they don't have the exact same labels.

---
## Vector Database
A **vector database** is a database that stores and searches **vector embeddings** (lists of numbers) to find data based on **similarity and meaning**.

![[Pasted image 20260802103840.png]]


