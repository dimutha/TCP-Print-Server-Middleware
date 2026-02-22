# TCP-Print-Server-Middleware
Lightweight middleware print server built using .NET Core.
It was developed to resolve a production bottleneck where:

 - Direct network printing was required
 - Dot-matrix printer was used
 - RJ45 network port was unavailable
 - Raw printing over TCP Port 9100 was needed

The service acts as a TCP listener on port 9100 and forwards incoming print data to the default Windows printer.

🏗 Architecture
Client System → TCP Port 9100 → Middleware Service → Default Printer → Dot-Matrix Printer

🔧 Technologies Used

 - .NET BackgroundService
 - TcpListener
 - System.Drawing.Printing
 - Async/Await
 - Windows Print Spooler

⚙ How It Works

 - The service listens on TCP port 9100.
 - A client sends raw print data.
 - The middleware receives the content.
 - The content is forwarded to the default printer.
 - The printer outputs via dot-matrix device.

🎯 Why This Solution?

 - Avoid hardware replacement cost
 - Eliminate production bottleneck
 - Provide quick middleware workaround
 - Maintain legacy printer compatibility
 - Simple, maintainable design

📈 Real-World Impact

This solution reduced dependency on hardware constraints and restored uninterrupted production printing without infrastructure redesign.
