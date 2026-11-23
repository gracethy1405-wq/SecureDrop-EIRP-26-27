# SecureDrop: Smart Anti-Theft Food Delivery Locker
**UNM Robotics Society — EIRP 2026/2027**

## Team Members
- Lee Xinyi, Kee Xin Yi, Ho Zi Yi, Tan Hui Ying

## Project Overview
SecureDrop is a battery-powered, single-compartment (1×1) smart anti-theft food delivery locker prototype built for university campuses without requiring delivery platform API integration or a dedicated mobile app. Students request a free locker on a Vercel-hosted web interface to receive a unique Order ID for their delivery note and pair a Telegram Bot (`@BotFather`) for instant alerts. When a rider places food on the floating plate, a 1 kg load cell with HX711 detects the weight and prompts Order ID entry on a 2.8" ILI9341 TFT touchscreen, while an MC-38 reed switch verifies door closure before locking a 12 V solenoid lock via a 3.3 V relay.

The system runs on an ESP32 Dev Module powered from a 12 V / 12.6 V battery pack with buck regulation (`3.3 V` logic and sensor rail, plus IRLZ44N MOSFETs driving a TEC1-06303 Peltier and 12 V fan alongside an AM2302/DHT22 temperature sensor). State and orders are stored on Supabase (PostgreSQL), a Cloudflare Worker cron trigger runs 30-minute reminder and 45-minute auto-open timers, and students unlock the locker by scanning a single-use QR code displayed on the screen.
