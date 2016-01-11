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
