# Rust

[Document](https://doc.rust-lang.org/book/title-page.html)

## Variable

1. An immutable variable `let x = 42;`
2. A mutable variable `let mut x = 42;`
3. Constant `const MY_CONSTANT = 42;`
4. Type hinting for variable `let x: u32 = 42;`
5. Shadowing

    ```rust
    fn main() {
        let x = 5;

        let x = x + 1;

        {
            let x = x * 2;
            println!("The value of x in the inner scope is: {x}");
        }

        println!("The value of x is: {x}");
    }
    ```

## Data type

1. Scalar Types
   1. Integers
 
         |         Length         | Signed | Unsigned |
         | ---------------------- | ------ | -------- |
         | 8-bit                  | i8     | u8       |
         | 16-bit                 | i16    | u16      |
         | 32-bit                 | i32    | u32      |
         | 64-bit                 | i64    | u64      |
         | 128-bit                | i128   | u128     |
         | Architecture-dependent | isize  | usize    |

       1. `i` is integer, `u` for unsigned
   2. Floating-Point Types
   3. The Boolean Type
   4. Character Type
2. Compound types
   1. Tuple
   
     ```rust
     fn main() {
         let tup = (500, 6.4, 1);

         let (x, y, z) = tup;

         println!("The value of y is: {y}");
     }
     ```

   2. Array

     ```rust
     fn main() {
         let a = [1, 2, 3, 4, 5];

         let first = a[0];
         let second = a[1];
     }
     ```

## Statements and Expressions

1. Not OK
     
     ```rust
     fn main() {
         let x = (let y = 6);
     }
     ```

2. OK
     
     ```rust
     fn main() {
         let y = {
             let x = 3;
             x + 1
         };

         println!("The value of y is: {y}");
     }
     ```
 
 3. Function returns value

     ```rust
     fn five() -> i32 {
         5
     }

     fn main() {
         let x = five();

         println!("The value of x is: {x}");
     }

     // OR

     fn main() {
         let x = plus_one(5);

         println!("The value of x is: {x}");
     }

     fn plus_one(x: i32) -> i32 {
         x + 1
     }
    ```

## Comments

1. `//` is a comment
2. `/*... */` is a block comment
3. `///` is an Outer doc comment
4. `//!` is an Inner doc comment