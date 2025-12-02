# SMTP module


## smtplib Class and Method Reference

This table summarizes the core class and methods of the Python built-in `smtplib` module, focusing on what a beginner needs to know for basic email sending.

---

### 1. SMTP Client Classes

| Class | Description | Usage Context |
| :--- | :--- | :--- |
| `smtplib.SMTP(host='', port=0, ...)` | The main **SMTP client object**. It establishes a connection to the mail server. You can initialize it without arguments and connect later, or provide the **`host`** and **`port`** directly for immediate connection. | Use this when connecting on Port **25** (unencrypted) or Port **587** (for use with `starttls()`). |
| `smtplib.SMTP_SSL(host='', port=465, ...)` | A subclass of `SMTP` that automatically wraps the connection in **SSL/TLS encryption** immediately upon establishment. | Use this when connecting on the dedicated secure Port **465**. |

---

### 2. Connection and Setup Methods

These methods are used to establish and secure the communication channel with the mail server.

| Method | Description | Usage Context |
| :--- | :--- | :--- |
| `connect(host='...', port=0)` | Manually connects to the specified **`host`** and **`port`**. This is useful if you didn't connect during the class initialization. | Used with `smtplib.SMTP` if the connection details weren't provided when the object was created. |
| `ehlo()` | A method that identifies the client (your script) to the mail server using the **ESMTP** (Extended SMTP) standard. It's often called internally, but can be useful to manually check server capabilities. | Standard initial step after connecting, often optional. |
| `starttls()` | Upgrades the connection to use **TLS encryption**. The communication switches from plain text to secure. | **Crucial** when connecting on Port **587**. Must be called *before* `login()`. |
| `login(user, password)` | **Authenticates** the connection by sending the email **`user`** (username/email address) and **`password`** (often an App Password) to the server. | Must be called after `starttls()` (for Port 587) or after `connect()` (for Port 465/`SMTP_SSL`). |

---

### 3. Sending and Termination Methods

These methods are used to deliver the email content and close the session.

| Method | Description | Usage Context |
| :--- | :--- | :--- |
| `sendmail(from_addr, to_addrs, msg)` | **The core sending method.** It sends the complete email message. | The primary method used to send the email. |
| | - **`from_addr`**: A string containing the sender's email address. |
| | - **`to_addrs`**: A list of strings containing all recipient email addresses. |
| | - **`msg`**: A string containing the entire formatted email content (including headers like Subject, To, From, and the body). |
| `quit()` | Sends the proper **`QUIT`** command to the SMTP server and gracefully closes the connection. | **Best practice** to call this when finished sending emails, or use a `with` statement. |
| `close()` | Terminates the socket connection without sending the SMTP `QUIT` command. | Generally, `quit()` is preferred for a clean server transaction. |


# Common SMTP server addresses

| Provider | Host Address (Server) | Port 587 (Recommended) | Port 465 (SSL) | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Gmail (Google)** | `smtp.gmail.com` | 587 (STARTTLS) | 465 (SSL) | Requires App Password for Python scripts. |
| **Outlook/Hotmail (Microsoft)** | `smtp-mail.outlook.com` | 587 (STARTTLS) | 465 (SSL) | |
| **Yahoo Mail** | `smtp.mail.yahoo.com` | 587 (STARTTLS) | 465 (SSL) | |
| **AOL** | `smtp.aol.com` | 587 (STARTTLS) | 465 (SSL) | |
| **AT&T** | `smpt.mail.att.net` | | 465 (SSL) | Sometimes defaults to SSL. |


------


```python
import smtplib

# type your emailhere
my_email = "fake@gmail.com"

# type your password here
password = "fakepassword"

# SMTP server addresses
with smtplib.SMTP("smtp.gmail.com") as connection:
    connection.starttls()
    connection.login(user=my_email, password=password)
    connection.sendmail(
        from_addr=my_email,
        to_addrs="anotherfake@gamail.com",
        msg="Subject:Hey there\n\nThis is just a text",
    )
```
