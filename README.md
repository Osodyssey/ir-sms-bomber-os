Of course. Here is a complete and professional `README.md` file for the project, written entirely in English, including a version number and the new banner image link.

---

# 💣 IR SMS Bomber v2.0 [ Developed by osodyssey ]

![Banner](https://github.com/Osodyssey/ir-sms-bomber-os/raw/main/assets/images/smsir-bomber-odyssey.png)

A powerful, multi-threaded SMS bombing script written in Python, designed to send a massive number of OTP (One-Time Password) text messages to Iranian phone numbers. This tool leverages a curated list of public APIs from various Iranian web services.

[![Python Version](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Author](https://img.shields.io/badge/Author-osodyssey-purple.svg)](https://github.com/osodyssey)

---

### **⚠️ Warning & Disclaimer**

**The misuse of this tool can be illegal and unethical.** The author (osodyssey) and any contributors assume no liability and are not responsible for any misuse or damage caused by this script. This project was created solely for **educational purposes and penetration testing**. Please use this tool responsibly and only on your own phone number or with the explicit consent of the target.

---

### ✨ **Key Features**

*   **🚀 High-Speed, Parallel Processing:** Utilizes a `ThreadPoolExecutor` to send multiple HTTP requests concurrently, dramatically increasing the bombing speed.
*   **🎯 Extensive API Collection:** Includes an up-to-date list of APIs from dozens of popular Iranian services.
*   **🎨 Enhanced User Interface:** Features a beautiful progress bar from `alive_progress` and colorful terminal output via `colorama` for a superior user experience.
*   **🛡️ Realistic Request Simulation:** Generates fake headers (`fake_headers`) for each request to mimic legitimate user traffic and bypass simple security measures.
*   **⚙️ Fully Configurable:** Allows users to specify the target number, message count per API, and the number of concurrent threads via command-line arguments.
*   **🌐 Proxy Support:** Capable of routing all requests through an HTTP/HTTPS proxy to conceal the user's IP address.
*   **📈 Detailed Reporting:** Provides a final summary of successful and failed requests at the end of the operation.

---

### **🛠️ Installation & Setup**

To get started with this tool, follow the steps below. You must have `Python 3` and `Git` installed on your system.

**1. Clone the Repository:**

First, open your terminal or command prompt and use the following command to download the source code from the GitHub repository:

```bash
git clone https://github.com/Osodyssey/ir-sms-bomber-os.git
```

**2. Navigate to the Project Directory:**

Use the `cd` command to enter the cloned folder:

```bash
cd ir-sms-bomber-os
```

**3. Install Required Libraries:**

The project depends on several Python libraries listed in the `requirements.txt` file. Install them easily using `pip`:

```bash
pip install -r requirements.txt
```

The tool is now ready to use!

---

### **👨‍💻 How to Use**

This tool is operated from the command-line interface (CLI). The general syntax is as follows:

```bash
python main.py <TARGET_PHONE> [OPTIONS]
```

**Arguments and Options:**

| Short Flag | Long Flag     | Description                                               | Default Value |
| :--------- | :------------ | :-------------------------------------------------------- | :------------ |
| `(Positional)` | `target`      | **(Required)** The target's phone number, e.g., `09xxxxxxxxx` | -             |
| `-c`       | `--count`     | Number of messages to send *per API*                      | `1`           |
| `-t`       | `--threads`   | Number of concurrent threads for sending requests         | `5`           |
| `-v`       | `--verbose`   | Display the status of each request (Success/Fail) in real-time | `False`         |
| `-x`       | `--proxy`     | Set an HTTP/HTTPS proxy for all outgoing requests         | `None`        |

**Practical Examples:**

*   **Standard Attack (one message from each API):**

    ```bash
    python main.py 09123456789
    ```

*   **Increase Message Volume:**
    Send 5 messages from *each* API. If 40 APIs are active, this will send a total of 200 messages.

    ```bash
    python main.py 09123456789 -c 5
    ```

*   **Increase Speed with More Threads:**
    Use 10 concurrent threads for faster execution.

    ```bash
    python main.py 09123456789 -t 10
    ```

*   **Verbose Mode:**
    To monitor the status of each individual request as it happens.

    ```bash
    python main.py 09123456789 -v
    ```

*   **Using a Proxy:**
    To route all requests through a specified proxy server.

    ```bash
    python main.py 09123456789 -x http://127.0.0.1:8080
    ```

*   **A Powerful, Combined Attack:**
    Send 3 messages from each API, using 20 concurrent threads, with verbose output.

    ```bash
    python main.py 09123456789 -c 3 -t 20 -v
    ```

---

### **🏗️ Code Architecture**

*   **`main.py`**: The main entry point of the script. It handles argument parsing, orchestrates the thread pool, and displays the final results.
*   **`send_otp_requests()`**: This function acts as an internal database, holding the list of target API endpoints, including their URLs and required JSON data structures.
*   **`send_request()`**: Responsible for sending a single `POST` request. It generates headers, handles timeouts, manages exceptions, and formats the response message for the user.
*   **`parse_arguments()`**: Configures and parses all command-line arguments using Python's `argparse` library.
*   **`handle_sigint()`**: A signal handler to ensure the program exits gracefully when the user presses `Ctrl+C`.

---

### **🤝 How to Contribute**

Contributions are welcome! If you want to improve this tool, please feel free to fork the repository, make your changes, and submit a pull request.

The easiest way to contribute is by **adding new, working APIs** to the list in the `send_otp_requests` function.

1.  **Fork** the repository.
2.  Create a new branch: `git checkout -b feature/add-new-api`
3.  Add your API details to the `apis` list in `main.py`.
4.  **Commit** your changes: `git commit -m 'Add new API for [Service Name]'`
5.  **Push** to the branch: `git push origin feature/add-new-api`
6.  Open a **Pull Request**.

---

### **📜 License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---
> Authored and developed by **osodyssey**.
