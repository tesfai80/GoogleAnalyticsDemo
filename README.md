
# Google Analytics MVC Application

This application demonstrates how to integrate **Google Analytics** with an ASP.NET MVC application and test it using **ngrok**.

## Prerequisites

1. **Visual Studio** or **.NET SDK** installed.
2. A **Google Analytics** account and property set up.
3. **ngrok** installed ([Download here](https://ngrok.com/download)).

## Getting Started

### 1. Clone and Run the Application
- Clone this repository to your local machine.
- Open the project in Visual Studio or any preferred IDE.
- Run the application using the following command (if using CLI):
  ```bash
  dotnet run
  ```
- The app will run on `http://localhost:5000` and `https://localhost:5001`.

### 2. Configure Google Analytics
1. Log in to [Google Analytics](https://analytics.google.com/).
2. Create a new property and copy the **Measurement ID** (e.g., `G-XXXXXXXXXX`).
3. Add the following snippet to `_Layout.cshtml` (inside the `<head>` tag):
   ```html
   <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
   <script>
       window.dataLayer = window.dataLayer || [];
       function gtag() {
           dataLayer.push(arguments);
       }
       gtag('js', new Date());
       gtag('config', 'G-XXXXXXXXXX');
   </script>
   ```

### 3. Install and Run ngrok
1. Download ngrok from [ngrok's official website](https://ngrok.com/download).
2. Extract and navigate to the ngrok directory.
3. Run the following command to expose your local application:
   ```bash
   ngrok http https://localhost:5001
   ```
4. Copy the **Forwarding URL** (e.g., `https://<random>.ngrok-free.app`).

### 4. Update Google Analytics with Public URL
- Go to your Google Analytics property settings.
- Replace the website URL with the ngrok forwarding URL.

### 5. Test Events in Google Analytics
1. Open the ngrok public URL in a browser.
2. Perform actions (e.g., button clicks) in the app to trigger events.
3. In Google Analytics:
   - Go to **Admin > DebugView** to see real-time events.
   - Check **Reports > Realtime > Events** for logged events.

## Commands Summary

### Run the Application
```bash
dotnet run
```

### Start ngrok
```bash
ngrok http https://localhost:5001
```

## Troubleshooting
- Ensure your local server is running before starting ngrok.
- Check ngrok logs at `http://127.0.0.1:4040` for any errors.
- Make sure Google Analytics is configured with the correct Measurement ID.

---

Happy coding!
