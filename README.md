CORS = Cross-Origin Resource Sharing

🔥 Problem it solves

Browsers follow something called:

👉 Same-Origin Policy

This means:

Frontend (example.com)
❌ cannot call API (api.other.com)

Why? 👉 Security reasons

🔹 What is “Origin”?

Origin = combination of:

Protocol (http/https)
Domain
Port

Examples:

https://google.com ≠ http://google.com
https://app.com ≠ https://api.app.com

🔹 How CORS works

When frontend calls API from different origin:

Step 1: Browser sends request with Origin header
Origin: https://myapp.com

Step 2: Server responds with headers

If allowed:

Access-Control-Allow-Origin: https://myapp.com

👉 Then browser allows response ✅

If NOT allowed:
👉 Browser blocks it ❌ (even if server responded)

🔹 Preflight Request (IMPORTANT)

For complex requests (POST, PUT, DELETE):

Browser first sends:

OPTIONS request

This checks:

Allowed methods
Allowed headers

Example response:

Access-Control-Allow-Methods: GET, POST

Access-Control-Allow-Headers: Content-Type

🔹 Common CORS Headers
Access-Control-Allow-Origin
Access-Control-Allow-Methods
Access-Control-Allow-Headers
Access-Control-Allow-Credentials

🔹 Real Example

Frontend:

https://myapp.com

API:

https://api.myapp.com

Without CORS:

❌ Blocked

With CORS:

Access-Control-Allow-Origin: *

✔ Works


✔ CORS is browser-enforced, not server-enforced
✔ Backend must enable CORS via headers
✔ Postman/Swagger works even if CORS fails (no browser restriction)
✔ * allows all origins (not safe for secure apps)
