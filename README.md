# Default value(aka: go style)

```rust
#[derive(Debug)]
enum Kind {
    A,
    B,
    C,
}

impl Default for Kind {
    fn default() -> Kind { Kind::A }
}

#[derive(Default, Debug)]
struct DefaultObject {
    o: Option<i64>,
    foo: i32,
    bar: f32,
    baz: Kind,
}

fn main() {
    let objs: Vec<DefaultObject> = vec![
            DefaultObject{foo: 42, ..Default::default()},
            DefaultObject{bar:1.0, ..Default::default()}
    ] ;
    print!("{:?}", objs)
}
```

# Table driven tests
```rust
 #[test]
    fn test_maybe_first_index() {
        // a, b, c, d, e,
        let tests: Vec<(Option<int>, u64, bool, u64)> = vec![  
            (Some(30), 5, false, 0),
            (None, 0, false, 0),
            // and more
        ];

        for (age, b, c, d) in tests {
            assert(age < 100);
            // and more check
        }
    }

```
