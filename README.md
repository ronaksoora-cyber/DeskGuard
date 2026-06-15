# DeskGuard
 Smart library seat management system to prevent desk hoarding |  Built with HTML, CSS and JavaScript

The Problem :
Students reserve library desks with their bags and disappear for hours - leaving genuine students with nowhere to study. There is no fair,trackable system to manage desk occupancy in real time.

The Solution :
DeskGuard is a web-based Smart Library Seat Management System that tracks desk occupancy in real time and automatically frees abandoned seats — no manual intervention needed

Features:

1.Live Color-Coded Map   --   Green=Free, Red=Occupied, Yellow=Away, Grey=Abandoned
2.QR Check-In Simulation --   Students scan desk QR code to check in
3.Away Mode              --   20-minute pause timer when student steps out briefly
4."Still Here?"Prompt    --   Auto-popup every 2 hours to confirm presence
5.Auto-Abandon           --   Desk automatically freed if student doesn't respond
6.Librarian Dashboard    --   Admin view to monitor and manually reset any desk
7.Server-Side Sweep      --   Background job checks all desks every second
8.Activity Log           --   Every action timestamped and logged in real time

🟢 Free       → Desk available for anyone
🔴 Occupied   → Student actively using the desk
🟡 Away       → Student stepped out (20 min timer running)
⚫ Abandoned  → Timer expired, desk auto-released

Tech Stack :

Fronted           --  HTML5, CSS3, Vanilla, JavaScript
Map Rendering     --  CSS Grid with dynamic color coding
Timer Logic       --  Server-side sweep via setInterval(ls)
State Management  --  JavaScript object array
Production Ready  --  Redis/PostgreSQL for persistent timer state

How to run :
# no installation needed!
# just open the file in any browser:
1. Download index.html
2. Double-click to open in browser
3. Done

Demo Flow

1. Click any GREEN desk → Enter name → QR Check-In
2. Click OCCUPIED desk → Mark Away (20 min timer starts)
3. Wait 30 sec (demo) → "Still Here?" popup appears
4. No response → Desk turns ABANDONED automatically
5. Librarian Dashboard → Reset any desk manually

Production  Architecture

    React Frontend            ────▶  Node.js / Python           ────▶ PostgreSQL 
    (SVG Seat Map)                     Backend API                      + Redis   
   
                                            │
                                      Background Job
                                    (sweeps every 60s,
                                    auto-expires desks)

In production,all timers run server-side  --  desk state presists even if browser is closed.

