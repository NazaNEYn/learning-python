| Method | Direction (Conversion) | Target/Source | Purpose (Use Case) | Analogy |
| :--- | :--- | :--- | :--- | :--- |
| `json.dumps()` | Python $\rightarrow$ JSON (Encode/Serialize) | String | To convert a **Python object** (like a dict) into a single **JSON-formatted string**, typically for sending over a network. | Placing your data into a sealed shipping box ready for transit. |
| `json.load()` | JSON $\rightarrow$ Python (Decode/Deserialize) | File | To convert data read from a **JSON file** into a **Python object** (like a dict) so you can use it in your program. | Receiving a shipping box (the file) and opening it to access the data inside. |
| `json.dump()` | Python $\rightarrow$ JSON (Encode/Serialize) | File | To convert a **Python object** (like a dict) and write it directly into an open **file** in JSON format for storage. | Writing your data down neatly onto a permanent ledger (the file). |
| `json.loads()` | JSON $\rightarrow$ Python (Decode/Deserialize) | String | To convert a **JSON-formatted string** you received (e.g., from an API response) back into a **Python object**. | Taking a sealed shipping box (the string) and immediately opening it to access the data. |
