# Rust_RPi_UnicornHatHD_treelights


#Resources

-https://github.com/jhelwig/unicorn-hat-hd-rs

-https://crates.io/crates/rgb


#This will use rust to run pixel changes (easily changeable with RGB values using this example) on the RPi Pimoroni UnicornHat HD model.

```
extern crate unicorn_hat_hd; extern crate rgb; extern crate rand;

use unicorn_hat_hd::UnicornHatHd;
use std::{thread, time};

pub enum Rotate {
    RotCW90,
}

pub fn main() {
    let mut hat_hd = UnicornHatHd::default();
    loop {
            const OFF: rgb::RGB8 = rgb::RGB8 {r: 0, g: 0, b: 0};
            const YELLOW: rgb::RGB8 = rgb::RGB8 {r: 255, g: 255, b: 0};
            const GREEN: rgb::RGB8 = rgb::RGB8 {r: 0, g: 255, b: 0};
            const RED: rgb::RGB8 = rgb::RGB8 {r: 255, g: 0, b: 0};
            const BLUE: rgb::RGB8 = rgb::RGB8 {r: 0, g: 0, b: 255};
            const BROWN: rgb::RGB8 = rgb::RGB8 {r: 125, g: 112, b: 76};
            //const WHITE: rgb::RGB8 = rgb::RGB8 {r: 255, g: 255, b: 255};

            //Row 1
            hat_hd.set_pixel(0, 0, OFF);  
            hat_hd.set_pixel(1, 0, OFF);
            hat_hd.set_pixel(2, 0, OFF);
            hat_hd.set_pixel(3, 0, OFF);
            hat_hd.set_pixel(4, 0, OFF);
            hat_hd.set_pixel(5, 0, OFF);
            hat_hd.set_pixel(6, 0, OFF);
            hat_hd.set_pixel(7, 0, YELLOW);
            hat_hd.set_pixel(8, 0, YELLOW);
            hat_hd.set_pixel(9, 0, OFF);
            hat_hd.set_pixel(10, 0, OFF);
            hat_hd.set_pixel(11, 0, OFF);
            hat_hd.set_pixel(12, 0, OFF);
            hat_hd.set_pixel(13, 0, OFF);
            hat_hd.set_pixel(14, 0, OFF);
            hat_hd.set_pixel(15, 0, OFF);
            //Row 2
            hat_hd.set_pixel(0, 1, OFF);
            hat_hd.set_pixel(1, 1, OFF);
            hat_hd.set_pixel(2, 1, OFF);
            hat_hd.set_pixel(3, 1, OFF);
            hat_hd.set_pixel(4, 1, OFF);
            hat_hd.set_pixel(5, 1, OFF);
            hat_hd.set_pixel(6, 1, GREEN);
            hat_hd.set_pixel(7, 1, YELLOW);
            hat_hd.set_pixel(8, 1, YELLOW);
            //hat_hd.set_pixel(9, 1, XMAS);
            hat_hd.set_pixel(10, 1, OFF);
            hat_hd.set_pixel(11, 1, OFF);
            hat_hd.set_pixel(12, 1, OFF);
            hat_hd.set_pixel(13, 1, OFF);
            hat_hd.set_pixel(14, 1, OFF);
            hat_hd.set_pixel(15, 1, OFF);
            //Row 3
            hat_hd.set_pixel(0, 2, OFF);
            hat_hd.set_pixel(1, 2, OFF);
            hat_hd.set_pixel(2, 2, OFF);
            hat_hd.set_pixel(3, 2, OFF);
            hat_hd.set_pixel(4, 2, OFF);
            hat_hd.set_pixel(5, 2, GREEN);
            //hat_hd.set_pixel(6, 2, XMAS);
            hat_hd.set_pixel(7, 2, GREEN);
            hat_hd.set_pixel(8, 2, GREEN);
            hat_hd.set_pixel(9, 2, GREEN);
            hat_hd.set_pixel(10, 2, GREEN);
            hat_hd.set_pixel(11, 2, OFF);
            hat_hd.set_pixel(12, 2, OFF);
            hat_hd.set_pixel(13, 2, OFF);
            hat_hd.set_pixel(14, 2, OFF);
            hat_hd.set_pixel(15, 2, OFF);
            //Row 4
            hat_hd.set_pixel(0, 3, OFF);
            hat_hd.set_pixel(1, 3, OFF);
            hat_hd.set_pixel(2, 3, OFF);
            hat_hd.set_pixel(3, 3, OFF);
            hat_hd.set_pixel(4, 3, GREEN);
            hat_hd.set_pixel(5, 3, GREEN);
            hat_hd.set_pixel(6, 3, GREEN);
            hat_hd.set_pixel(7, 3, GREEN);
            hat_hd.set_pixel(8, 3, GREEN);
            //hat_hd.set_pixel(9, 3, XMAS);
            hat_hd.set_pixel(10, 3, GREEN);
            hat_hd.set_pixel(11, 3, GREEN);
            hat_hd.set_pixel(12, 3, OFF);
            hat_hd.set_pixel(13, 3, OFF);
            hat_hd.set_pixel(14, 3, OFF);
            hat_hd.set_pixel(15, 3, OFF);
            hat_hd.set_pixel(16, 3, OFF);
            //Row 5
            hat_hd.set_pixel(0, 4, OFF);
            hat_hd.set_pixel(1, 4, OFF);
            hat_hd.set_pixel(2, 4, OFF);
            hat_hd.set_pixel(3, 4, GREEN);
            hat_hd.set_pixel(4, 4, GREEN);
            //hat_hd.set_pixel(5, 4, XMAS);
            hat_hd.set_pixel(6, 4, GREEN);
            hat_hd.set_pixel(7, 4, GREEN);
            hat_hd.set_pixel(8, 4, GREEN);
            hat_hd.set_pixel(9, 4, GREEN);
            hat_hd.set_pixel(10, 4, GREEN);
            //hat_hd.set_pixel(11, 4, XMAS);
            hat_hd.set_pixel(12, 4, GREEN);
            hat_hd.set_pixel(13, 4, OFF);
            hat_hd.set_pixel(14, 4, OFF);
            hat_hd.set_pixel(15, 4, OFF);
            //Row 6
            hat_hd.set_pixel(0, 5, OFF);
            hat_hd.set_pixel(1, 5, OFF);
            hat_hd.set_pixel(2, 5, GREEN);
            //hat_hd.set_pixel(3, 5, XMAS);
            hat_hd.set_pixel(4, 5, GREEN);
            hat_hd.set_pixel(5, 5, GREEN);
            hat_hd.set_pixel(6, 5, GREEN);
            hat_hd.set_pixel(7, 5, GREEN);
            //hat_hd.set_pixel(8, 5, XMAS);
            hat_hd.set_pixel(9, 5, GREEN);
            hat_hd.set_pixel(10, 5, GREEN);
            hat_hd.set_pixel(11, 5, GREEN);
            hat_hd.set_pixel(12, 5, GREEN);
            hat_hd.set_pixel(13, 5, GREEN);
            hat_hd.set_pixel(14, 5, OFF);
            hat_hd.set_pixel(15, 5, OFF);
            //Row 7
            hat_hd.set_pixel(0, 6, OFF);
            hat_hd.set_pixel(1, 6, GREEN);
            hat_hd.set_pixel(2, 6, GREEN);
            hat_hd.set_pixel(3, 6, GREEN);
            hat_hd.set_pixel(4, 6, GREEN);
            hat_hd.set_pixel(5, 6, GREEN);
            hat_hd.set_pixel(6, 6, GREEN);
            //hat_hd.set_pixel(7, 6, XMAS);
            hat_hd.set_pixel(8, 6, GREEN);
            hat_hd.set_pixel(9, 6, GREEN);
            hat_hd.set_pixel(10, 6, GREEN);
            hat_hd.set_pixel(11, 6, GREEN);
            hat_hd.set_pixel(12, 6, GREEN);
            hat_hd.set_pixel(13, 6, GREEN);
            hat_hd.set_pixel(14, 6, GREEN);
            hat_hd.set_pixel(15, 6, OFF);
            //Row 8
            hat_hd.set_pixel(0, 7, GREEN);
            hat_hd.set_pixel(1, 7, GREEN);
            hat_hd.set_pixel(2, 7, GREEN);
            hat_hd.set_pixel(3, 7, GREEN);
            //hat_hd.set_pixel(4, 7, XMAS);
            hat_hd.set_pixel(5, 7, GREEN);
            hat_hd.set_pixel(6, 7, GREEN);
            hat_hd.set_pixel(7, 7, GREEN);
            hat_hd.set_pixel(8, 7, GREEN);
            hat_hd.set_pixel(9, 7, GREEN);
            hat_hd.set_pixel(10, 7, GREEN);
            //hat_hd.set_pixel(11, 7, XMAS);
            hat_hd.set_pixel(12, 7, GREEN);
            hat_hd.set_pixel(13, 7, GREEN);
            hat_hd.set_pixel(14, 7, GREEN);
            hat_hd.set_pixel(15, 7, GREEN);
            //Row 9
            hat_hd.set_pixel(0, 8, OFF);
            hat_hd.set_pixel(1, 8, OFF);
            hat_hd.set_pixel(2, 8, GREEN);
            hat_hd.set_pixel(3, 8, GREEN);
            hat_hd.set_pixel(4, 8, GREEN);
            //hat_hd.set_pixel(5, 8, XMAS);
            hat_hd.set_pixel(6, 8, GREEN);
            hat_hd.set_pixel(7, 8, GREEN);
            hat_hd.set_pixel(8, 8, GREEN);
            hat_hd.set_pixel(9, 8, GREEN);
            hat_hd.set_pixel(10, 8, GREEN);
            hat_hd.set_pixel(11, 8, GREEN);
            hat_hd.set_pixel(12, 8, GREEN);
            hat_hd.set_pixel(13, 8, GREEN);
            hat_hd.set_pixel(14, 8, OFF);
            hat_hd.set_pixel(15, 8, OFF);
            //Row 10
            hat_hd.set_pixel(0, 9, OFF);
            hat_hd.set_pixel(1, 9, GREEN);
            hat_hd.set_pixel(2, 9, GREEN);
            hat_hd.set_pixel(3, 9, GREEN);
            //hat_hd.set_pixel(4, 9, XMAS);
            hat_hd.set_pixel(5, 9, GREEN);
            hat_hd.set_pixel(6, 9, GREEN);
            hat_hd.set_pixel(7, 9, GREEN);
            hat_hd.set_pixel(8, 9, GREEN);
            hat_hd.set_pixel(9, 9, GREEN);
            hat_hd.set_pixel(10, 9, GREEN);
            //hat_hd.set_pixel(11, 9, XMAS);
            hat_hd.set_pixel(12, 9, GREEN);
            hat_hd.set_pixel(13, 9, GREEN);
            hat_hd.set_pixel(14, 9, GREEN);
            hat_hd.set_pixel(15, 9, OFF);
            //Row 11
            hat_hd.set_pixel(0, 10, GREEN);
            hat_hd.set_pixel(1, 10, GREEN);
            //hat_hd.set_pixel(2, 10, XMAS);
            hat_hd.set_pixel(3, 10, GREEN);
            hat_hd.set_pixel(4, 10, GREEN);
            hat_hd.set_pixel(5, 10, GREEN);
            hat_hd.set_pixel(6, 10, GREEN);
            hat_hd.set_pixel(7, 10, GREEN);
            hat_hd.set_pixel(8, 10, GREEN);
            //hat_hd.set_pixel(9, 10, XMAS);
            hat_hd.set_pixel(10, 10, GREEN);
            hat_hd.set_pixel(11, 10, GREEN);
            hat_hd.set_pixel(12, 10, GREEN);
            hat_hd.set_pixel(13, 10, GREEN);
            hat_hd.set_pixel(14, 10, GREEN);
            hat_hd.set_pixel(15, 10, GREEN);
            //Row 12
            hat_hd.set_pixel(0, 11, OFF);
            hat_hd.set_pixel(1, 11, OFF);
            hat_hd.set_pixel(2, 11, GREEN);
            hat_hd.set_pixel(3, 11, GREEN);
            hat_hd.set_pixel(4, 11, GREEN);
            hat_hd.set_pixel(5, 11, GREEN);
            //hat_hd.set_pixel(6, 11, XMAS);
            hat_hd.set_pixel(7, 11, GREEN);
            hat_hd.set_pixel(8, 11, GREEN);
            hat_hd.set_pixel(9, 11, GREEN);
            hat_hd.set_pixel(10, 11, GREEN);
            hat_hd.set_pixel(11, 11, GREEN);
            hat_hd.set_pixel(12, 11, GREEN);
            //hat_hd.set_pixel(13, 11, XMAS);
            hat_hd.set_pixel(14, 11, OFF);
            hat_hd.set_pixel(15, 11, OFF);
            //Row 13
            hat_hd.set_pixel(0, 12, OFF);
            //hat_hd.set_pixel(1, 12, XMAS);
            hat_hd.set_pixel(2, 12, GREEN);
            hat_hd.set_pixel(3, 12, GREEN);
            hat_hd.set_pixel(4, 12, GREEN);
            hat_hd.set_pixel(5, 12, GREEN);
            hat_hd.set_pixel(6, 12, GREEN);
            hat_hd.set_pixel(7, 12, GREEN);
            hat_hd.set_pixel(8, 12, GREEN);
            hat_hd.set_pixel(9, 12, GREEN);
            hat_hd.set_pixel(10, 12, GREEN);
            //hat_hd.set_pixel(11, 12, XMAS);
            hat_hd.set_pixel(12, 12, GREEN);
            hat_hd.set_pixel(13, 12, GREEN);
            hat_hd.set_pixel(14, 12, GREEN);
            hat_hd.set_pixel(15, 12, OFF);
            //Row 14
            hat_hd.set_pixel(0, 13, GREEN);
            hat_hd.set_pixel(1, 13, GREEN);
            hat_hd.set_pixel(2, 13, GREEN);
            hat_hd.set_pixel(3, 13, GREEN);
            //hat_hd.set_pixel(4, 13, XMAS);
            hat_hd.set_pixel(5, 13, GREEN);
            hat_hd.set_pixel(6, 13, GREEN);
            hat_hd.set_pixel(7, 13, GREEN);
            hat_hd.set_pixel(8, 13, GREEN);
            hat_hd.set_pixel(9, 13, GREEN);
            //hat_hd.set_pixel(10, 13, XMAS);
            hat_hd.set_pixel(11, 13, GREEN);
            hat_hd.set_pixel(12, 13, GREEN);
            hat_hd.set_pixel(13, 13, GREEN);
            hat_hd.set_pixel(14, 13, GREEN);
            hat_hd.set_pixel(15, 13, GREEN);
            //Row 15
            hat_hd.set_pixel(0, 14, OFF);
            hat_hd.set_pixel(1, 14, OFF);
            hat_hd.set_pixel(2, 14, OFF);
            hat_hd.set_pixel(3, 14, OFF);
            hat_hd.set_pixel(4, 14, OFF);
            hat_hd.set_pixel(5, 14, OFF);
            hat_hd.set_pixel(6, 14, OFF);
            hat_hd.set_pixel(7, 14, BROWN);
            hat_hd.set_pixel(8, 14, BROWN);
            hat_hd.set_pixel(9, 14, OFF);
            hat_hd.set_pixel(10, 14, OFF);
            hat_hd.set_pixel(11, 14, OFF);
            hat_hd.set_pixel(12, 14, OFF);
            hat_hd.set_pixel(13, 14, OFF);
            hat_hd.set_pixel(14, 14, OFF);
            hat_hd.set_pixel(15, 14, OFF);
            //Row 16
            hat_hd.set_pixel(0, 15, OFF);
            hat_hd.set_pixel(1, 15, OFF);
            hat_hd.set_pixel(2, 15, OFF);
            hat_hd.set_pixel(3, 15, OFF);
            hat_hd.set_pixel(4, 15, OFF);
            hat_hd.set_pixel(5, 15, OFF);
            hat_hd.set_pixel(6, 15, OFF);
            hat_hd.set_pixel(7, 15, BROWN);
            hat_hd.set_pixel(8, 15, BROWN);
            hat_hd.set_pixel(9, 15, OFF);
            hat_hd.set_pixel(10, 15, OFF);
            hat_hd.set_pixel(11, 15, OFF);
            hat_hd.set_pixel(12, 15, OFF);
            hat_hd.set_pixel(13, 15, OFF);
            hat_hd.set_pixel(14, 15, OFF);
            hat_hd.set_pixel(15, 15, OFF);
            
            loop {
		let _xmas = RED;
		let threefitty_millis = time::Duration::from_millis(350);
		let now = time::Instant::now();
		
		hat_hd.set_pixel(9, 1, _xmas);
		hat_hd.set_pixel(6, 2, _xmas);
		hat_hd.set_pixel(9, 3, _xmas);
		hat_hd.set_pixel(5, 4, _xmas);
		hat_hd.set_pixel(11, 4, _xmas);
		hat_hd.set_pixel(3, 5, _xmas);
		hat_hd.set_pixel(8, 5, _xmas);
		hat_hd.set_pixel(7, 6, _xmas);
		hat_hd.set_pixel(4, 7, _xmas);
		hat_hd.set_pixel(11, 7, _xmas);
		hat_hd.set_pixel(5, 8, _xmas);
		hat_hd.set_pixel(4, 9, _xmas);
		hat_hd.set_pixel(11, 9, _xmas);
		hat_hd.set_pixel(9, 10, _xmas);
		hat_hd.set_pixel(2, 10, _xmas);
		hat_hd.set_pixel(6, 11, _xmas);
		hat_hd.set_pixel(13, 11, _xmas);
		hat_hd.set_pixel(1, 12, _xmas);
		hat_hd.set_pixel(11, 12, _xmas);
		hat_hd.set_pixel(4, 13, _xmas);
		hat_hd.set_pixel(10, 13, _xmas);
		hat_hd.set_rotation(unicorn_hat_hd::Rotate::RotCW90);
		hat_hd.display().unwrap();

		thread::sleep(threefitty_millis);
		assert!(now.elapsed() >= threefitty_millis);
		

		let _xmas2 = BLUE;
		hat_hd.set_pixel(9, 1, _xmas2);
		hat_hd.set_pixel(6, 2, _xmas2);
		hat_hd.set_pixel(9, 3, _xmas2);
		hat_hd.set_pixel(5, 4, _xmas2);
		hat_hd.set_pixel(11, 4, _xmas2);
		hat_hd.set_pixel(3, 5, _xmas2);
		hat_hd.set_pixel(8, 5, _xmas2);
		hat_hd.set_pixel(7, 6, _xmas2);
		hat_hd.set_pixel(4, 7, _xmas2);
		hat_hd.set_pixel(11, 7, _xmas2);
		hat_hd.set_pixel(5, 8, _xmas2);
		hat_hd.set_pixel(4, 9, _xmas2);
		hat_hd.set_pixel(11, 9, _xmas2);
		hat_hd.set_pixel(2, 10, _xmas2);
		hat_hd.set_pixel(9, 10, _xmas2);
		hat_hd.set_pixel(6, 11, _xmas2);
		hat_hd.set_pixel(13, 11, _xmas2);
		hat_hd.set_pixel(1, 12, _xmas2);
		hat_hd.set_pixel(11, 12, _xmas2);
		hat_hd.set_pixel(4, 13, _xmas2);
		hat_hd.set_pixel(10, 13, _xmas2);
		hat_hd.set_rotation(unicorn_hat_hd::Rotate::RotCW90);
		hat_hd.display().unwrap();
		
		thread::sleep(threefitty_millis);
		assert!(now.elapsed() >= threefitty_millis);
            }
            //hat_hd.set_rotation(unicorn_hat_hd::Rotate::RotCW90);
            //hat_hd.display().unwrap();
         }

    }
```
