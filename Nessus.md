# Installing and setting up Kali Linux

**Prerequisites:**

- **Internet connection:** Nessus requires an internet connection during installation and activation.

**Steps:**

1. **Download Nessus:**

   - Visit the Tenable Nessus downloads page: [https://www.tenable.com/downloads/nessus?loginAttempted=true](https://www.tenable.com/downloads/nessus?loginAttempted=true)
   - Locate the **Linux - Debian - amd64** version (assuming you're using a 64-bit Kali system).
   - Download the `.deb` file.
   - Agree to the License Agreement.
   - Click Checksum next to the download button and copy the SHA256 checksum into `mousepad`.

2. **Verify Download Integrity (Optional but Recommended):**

   - Open a terminal window.
   - Navigate to your Downloads directory:
     ```Bash
     cd ~/Downloads
     ```
   - Read the directory with the following command to show the `downloaded_file_name`:
     ```Bash
     ls
     ```
   - Copy the SHA256 checksum from the Nessus website. This ensures the downloaded file is not corrupted.
   - Use the `sha256sum` command to verify the checksum: `sha256sum [downloaded_file_name]`

     Replace `[downloaded_file_name]` with the actual filename (e.g., `Nessus-10.6.3-debian10_amd64.deb`). The output should match the checksum provided on the Tenable website.

5. **Install Nessus:**

   - Run the following command in the terminal:

     ```bash
     sudo apt install ./[downloaded_file_name]
     ```

     Replace `[downloaded_file_name]` with the actual filename.

   - Enter your password when prompted. This command will download and install Nessus using the package manager.

6. **Start Nessus Service:**

   - Run the following command in the terminal:

     ```bash
     sudo systemctl start nessusd
     ```

7. **Activate Nessus:**

   - Open a web browser and navigate to `https://localhost:8834`.
   - You might encounter a security warning about the SSL certificate. Click "Advanced" and then "Accept the Risk and Continue" if you trust the connection.
   - Choose the appropriate registration option (Nessus Essentials for personal use) and follow the on-screen instructions to register and activate Nessus using a license key.
   - You can obtain a free Nessus Essentials license for personal use from Tenable's website ([https://www.tenable.com/tenable-for-education/nessus-essentials](https://www.tenable.com/tenable-for-education/nessus-essentials)).

**Additional Notes:**

- If you encounter firewall issues, you may need to adjust your firewall rules to allow Nessus to function properly.
- For further configuration options and advanced usage, refer to the Nessus documentation: [invalid URL removed]
- Nessus updates are typically available through the Kali package manager. You can update Nessus with `sudo apt update && sudo apt upgrade`.

**Congratulations! You've successfully installed and activated Nessus on your Kali Linux system.** You can now use Nessus to perform vulnerability scans on target systems. Refer to the Nessus documentation for instructions on launching scans and interpreting results.
