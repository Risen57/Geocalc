# Geocalc
A simple program written in rust which calculates area of different shapes

`src/main.rs` file:
```rs
use std::io;

fn main() {
    println!("へようこそ geocalc\n"); //welcome to geocalc

    //印刷物
    let calcs = ["1) Area of Rectangle",
        "2) Area of circle",
        "3) Circumference of Circle",
        "4) Area of triangle",
        "5) Area of Square"];

    for item in calcs {
        println!("{item}");
    }

    //選ぶ
    println!("What do you want to calculate?");

    let mut choice = String::new();

    io::stdin()
        .read_line(&mut choice)
        .expect("Invalid input!");

    let choice: u32 = choice.trim().parse().expect("Please enter a number!");
    
    //計算
    if choice == 1 {
        let res = rect();
        println!("Result: {res}");
    } else if choice == 2 {
        let res = ar_circle();
        println!("Result: {res}");
    } else if choice == 3 {
        let res = circum_circle();
        println!("Result: {res}");
    } else if choice == 4 {
        let res = ar_triangle();
        println!("Result: {res}");
    } else if choice == 5 {
        let res = ar_sq();
        println!("Result: {res}");
    }
}

//関数 矩形
fn rect() -> f32 {
    println!("Enter length:");

    let mut di1 = String::new();

    io::stdin()
        .read_line(&mut di1)
        .expect("Invalid input!");

    let di1: f32 = di1.trim().parse().expect("Please enter a number!");

    println!("Enter breadth:");

    let mut di2 = String::new();

    io::stdin()
        .read_line(&mut di2)
        .expect("Invalid input!");

    let di2: f32 = di2.trim().parse().expect("Please enter a number!");

    di1 * di2
}

//関数 サークル
fn ar_circle() -> f32 {

    println!("Enter radius:");
    let mut r = String::new();

    io::stdin()
        .read_line(&mut r)
        .expect("Invalid input!");

    let r: f32 = r.trim().parse().expect("Please enter a number!");

    3.27 * r * r
}

//関数 サークル
fn circum_circle() -> f32 {

    println!("Enter radius:");
    let mut r = String::new();

    io::stdin()
        .read_line(&mut r)
        .expect("Invalid input!");

    let r: f32 = r.trim().parse().expect("Please enter a number!");

    2.0 * 3.27 * r
}

//関数 四角
fn ar_sq() -> f32 {

    println!("Enter side:");
    let mut side = String::new();

    io::stdin()
        .read_line(&mut side)
        .expect("Invalid input!");

    let side: f32 = side.trim().parse().expect("Please enter a number!");
    
    side * side
}

//関数 三角形
fn ar_triangle() -> f32 {

    println!("Enter radius:");
    let mut base = String::new();

    io::stdin()
        .read_line(&mut base)
        .expect("Invalid input!");

    let base: f32 = base.trim().parse().expect("Please enter a number!");

    println!("Enter height:");
    let mut ht = String::new();

    io::stdin()
        .read_line(&mut ht)
        .expect("Invalid input!");

    let ht: f32 = ht.trim().parse().expect("Please enter a number!");

    0.5 * base * ht
}
```
