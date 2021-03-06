# image_to_static_vec

This creates rs file that defines static Vec<u8> by lazy_static for mono image data.

# Usage

```
cargo run "./tmp/nums.json" > "./tmp/vec.rs"
```

## Command

```json
{
  "img_path": "./tmp/nums.png",
  "array_length": 50,
  "prefix": "vec_num",
  "height": 10,
  "mode": "bool",
  "x_list": [
    3,
    ..
  ],
  "labels": [
    "1",
    ..
  ]
}
```

```rust
const VEC_NUM_1: (usize, usize, [bool; 50]) = (3, 10, [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 1, 0, 0, 1, 0, 0, 1, 0, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]);
const VEC_NUM_2: (usize, usize, [bool; 50]) = (5, 10, [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]);
// snip
const VEC_NUM_PERIOD: (usize, usize, [bool; 50]) = (2, 10, [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]);
```

## Command for u8

```json
{
  "img_path": "./tmp/nums.png",
  "array_length": 7,
  "prefix": "vec_num",
  "height": 10,
  "mode": "u8",
  "x_list": [
    3,
    ..
  ],
  "labels": [
    "1",
    ..
  ]
}
```

```rust
const VEC_NUM_1: (usize, usize, [u8; 7]) = (3, 10, [0, 44, 151, 0, 0, 0, 0]);
const VEC_NUM_2: (usize, usize, [u8; 7]) = (5, 10, [0, 0, 232, 136, 159, 0, 0]);
// snip
const VEC_NUM_PERIOD: (usize, usize, [u8; 7]) = (2, 10, [0, 15, 0, 0, 0, 0, 0]);
```
