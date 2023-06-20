**Router**

Endpoint: `GET /api/inscriptions`

**Query Parameters**

Request query parameters:
- `page` (required): Current page number (e.g., 1, 2, 3, ...)
- `size` (required): Number of results per page

**Structs**

- `ApiArgs`:

```rust
#[derive(Serialize, Deserialize)]
struct ApiArgs {
    page: usize,
    size: usize,
}
```

- `ApiResponse<T>`:

```
#[derive(Serialize, Deserialize)]
struct ApiResponse<T> {
    code: i32,
    msg: String,
    count: usize,
    total: usize,
    page_count: usize,
    data: T,
}
```

*** Example Response ***
```
{
  "code": 200,
  "msg": "ok",
  "count": 5,
  "total": 13398,
  "page_count": 2680,
  "data": [
    "45b2ccb6339b3d469ab5814dd305508ed2c420b875af580be175026e69c220e4i0",
    "51b13c39ce889c02455da4df9ea0458a619e366bbe4ef97bb7420c26a258cfe1i0",
    "095f21be73f95f2389639472ab20fbfc5480ab88459b2fb43cc3f1445148eec2i0",
    "77f6c393cb3483ce8a6209ce4c66f1f84b1773c5e204edb7477f58142607765fi0",
    ...
  ]
}
```