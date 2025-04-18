# Hosting a Website Using Apache on Kali Linux

## Step 1: Install Apache

If you haven't installed Apache yet, run:

```bash
sudo apt update
sudo apt install apache2
```

## Step 2: Start Apache Service

Start the Apache service:

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

## Step 3: Replace the Default HTML File

Open the default `index.html` file:

```bash
sudo nano /var/www/html/index.html
```

Replace its content with the following HTML code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Welcome to My Kali Linux Website</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #111;
      color: #eee;
      text-align: center;
      padding: 50px;
    }
    h1 {
      color: #00ffcc;
    }
    p {
      font-size: 18px;
    }
    .box {
      background-color: #222;
      border: 1px solid #00ffcc;
      padding: 20px;
      margin-top: 20px;
      display: inline-block;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <h1>🔥 Kali Linux Web Server 🔥</h1>
  <div class="box">
    <p>This website is being hosted on Kali Linux using Apache!</p>
    <p>Feel free to customize this page and make it your own.</p>
    <p>Happy Hacking!</p>
  </div>
</body>
</html>
```

Save and exit by pressing `Ctrl + O`, `Enter`, and `Ctrl + X`.

## Step 4: Verify the Apache Web Server

Open your browser and go to:

```
http://localhost
```

You should see your new webpage.

## Step 5: Make Apache Accessible on the Network (Optional)

Find your IP address:

```bash
ip a
```

Now open the website in another device's browser:

```
http://<your_kali_ip_address>
```

If needed, allow Apache traffic through the firewall:

```bash
sudo ufw allow 'Apache Full'
```

## Step 6: Check Apache Status

```bash
sudo systemctl status apache2
```

---

# Configure Nagios XI on Kali Linux

## Step 1: Install Nagios XI

Wait for the installation process to finish.

## Step 2: Access the Web Interface

Nagios XI is accessible at:

- `http://<your_kali_ip_address>/nagiosxi`
- Or locally: `http://localhost/nagiosxi`

### Default Login Credentials:

- **Username**: `nagiosadmin`
- **Password**: `nagiosxi`

Change the password after logging in.

## Step 3: Set Up Website Monitoring

1. Go to **Configuration > Monitoring > Add Host**.
2. Provide the hostname or IP.
3. Select appropriate monitoring plugins like **HTTP check**.
4. Set thresholds for uptime/response.

## Step 4: Set Up Alerts

Go to **Configure > Alerting** and set:

- Email
- SMS
- Other notifications

## Step 5: Check Website Monitoring Status

From the dashboard, you can see:

- Website uptime
- Response times
- HTTP/HTTPS status

You can also monitor other services like databases and server resources.

## Step 6: Add More Monitoring Features

- **Network Monitoring**: Add routers, switches, etc.
- **Advanced Plugins**: For cloud, databases, hardware.
- **Reports**: Built-in reporting for performance and trends.
