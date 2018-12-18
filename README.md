# Rust_RPi_UnicornHatHD_treelights


#Resources

#https://github.com/jhelwig/unicorn-hat-hd-rs

#https://crates.io/crates/rgb

#https://docs.rs/unicorn_hat_hd/0.2.1/src/unicorn_hat_hd/lib.rs.html#125-127

#This will use rust to run pixel changes (easily changeable with RGB values using this example) on the RPi Pimoroni UnicornHat HD model.

main.rs:
```
extern crate unicorn_hat_hd;
extern crate rgb;

use unicorn_hat_hd::UnicornHatHd;

const OFF: rgb::RGB8 = rgb::RGB8 {r: 0, g: 0, b: 0};
const YELLOW: rgb::RGB8 = rgb::RGB8 {r: 255, g: 255, b: 0};
const GREEN: rgb::RGB8 = rgb::RGB8 {r: 0, g: 255, b: 0};
const RED: rgb::RGB8 = rgb::RGB8 {r: 255, g: 0, b: 0};
const BLUE: rgb::RGB8 = rgb::RGB8 {r: 0, g: 0, b: 255};

pub fn main() {
    let mut hat_hd = UnicornHatHd::default();
    loop {
        for y in ((0..16)/2) {
            for x in 0..16 {
                hat_hd.set_pixel(x, y, YELLOW);
                hat_hd.display().unwrap();
                hat_hd.set_pixel(x, y, BLUE);
                hat_hd.display().unwrap();
                hat_hd.set_pixel(x, y, RED);
                hat_hd.display().unwrap();
                hat_hd.set_pixel(x, y, CLEAR);
            }
        }
    }
}
```
