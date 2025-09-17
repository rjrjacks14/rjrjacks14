### Web folder
What I built

A login flow in Gluu Agama Lab.

If the password is correct and risk is LOW → login finishes (no OTP).

If the password is correct and risk is HIGH → user sees an OTP page and must enter a code.

How the decision works (for the demo)

I set a simple variable called riskLevel to LOW or HIGH to show the two paths.

LOW → password only.

HIGH → password + OTP (code 123456 in the demo).

What I’d use as real risk signals (in production)

Where the login comes from (impossible travel / far-away sudden change).

Device (known device = safer; brand-new/odd device = riskier).

Network (Tor/VPN/data center IPs are riskier).
These keep normal users fast and only add OTP when something looks off.

How I’d plug in Relock (concept, not implemented)

After the password is correct, I’d ask Relock if this device/session looks safe or risky.

If Relock says safe → treat as LOW (password only).

If Relock says risky or doesn’t respond → treat as HIGH (ask for OTP).

Later, Relock can also send signals during a session; if risk goes up, we can ask for OTP again.