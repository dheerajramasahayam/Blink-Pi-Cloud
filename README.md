blink-pi-cloud

Automate Blink Sync Module Footage Storage and Cloud Upload with Raspberry Pi Zero
Overview

This repository provides scripts and documentation to transform a Raspberry Pi Zero into a USB Mass Storage Device for the Blink Sync Module, formatted with exFAT, and automate the upload of footage to Google Drive using Rclone.

The setup enables seamless local and cloud storage integration for Blink cameras, creating a reliable backup system for your recordings.
Features

    Configures the Raspberry Pi Zero as a USB mass storage device using exFAT, compatible with Blink Sync Module.
    Automates footage upload to Google Drive with Rclone.
    Allows for scheduled cloud synchronization using cron jobs.
    Provides easy-to-use setup scripts and detailed instructions.

Requirements
Hardware

    Raspberry Pi Zero W (or Zero 2 W)
    MicroSD card (32GB or larger)
    USB cable for connecting to the Blink Sync Module
    Blink Sync Module
    Wi-Fi Network

Software

    Raspberry Pi OS (Lite or Full version)
    exFAT Utilities
    Rclone for cloud sync

Installation and Setup
1. Flash Raspberry Pi OS

    Flash Raspberry Pi OS onto your SD card using Raspberry Pi Imager.

2. Enable SSH

    Create an empty file named ssh in the boot partition of the SD card.

3. Clone This Repository

SSH into your Raspberry Pi Zero and clone this repository:

git clone https://github.com/yourusername/blink-pi-cloud.git
cd blink-pi-cloud

4. Run the Setup Scripts

    Set up USB mass storage with setup_usb_storage.sh:

    ./setup_usb_storage.sh

    Configure Rclone for Google Drive with rclone config.

5. Automate Cloud Upload

    Run upload_to_cloud.sh to upload footage manually or automate it with a cron job:

    ./upload_to_cloud.sh

6. Schedule Automatic Uploads

    Edit the cron table to run uploads periodically:

crontab -e

Add the following line to upload footage every hour:

    0 * * * * /home/pi/blink-pi-cloud/upload_to_cloud.sh

Usage

    Insert the SD card into the Raspberry Pi Zero and connect it to the Blink Sync Module.
    Footage will automatically save to the Pi’s storage.
    The upload script will sync footage to Google Drive periodically.

Troubleshooting

    Ensure the Raspberry Pi is powered and connected to Wi-Fi.
    Check the Blink Sync Module recognizes the storage (format as exFAT if required).
    Verify Rclone is configured correctly with rclone listremotes.

Contributing

Contributions are welcome! Feel free to submit issues or pull requests to improve this project.
License

This project is licensed under the MIT License.
