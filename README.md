♞ Lucena

A tournament-grade chess app in a single HTML file.

No accounts. No servers. No ads. No tracking. It's just a file you own.

Works OfflineNo TrackingNo AdsZero DependenciesSingle File
🚀 Quick start

    Download lucena.html (or clone this repo)
    Double-click it — it opens in your browser
    Play

That's the whole install. No installer, no account, no permissions.

    💡 On mobile: open the file, then use your browser's Share → Add to Home Screen.It launches full-screen like a native app.

🔒 Private by design

This app has no backend, and never will. Here is the complete list ofeverything it does with your data:
Thing	Lucena
Accounts / sign-ups	❌ None
Analytics / telemetry	❌ None
Ads / ad networks	❌ None
Cookies	❌ None
Trackers / fingerprinting	❌ None
Server communication	❌ There is no server
Cloud sync	❌ Your games never leave the page
Data collection	❌ Nothing to collect — it's a chessboard

Your games live only in the page itself. Your one preference (sound, engine level)is stored in your browser's localStorage, on your device, and nowhere else.Clear your browser data and it's gone — the way it should be.

The entire app is one readable HTML file. There is no minified bundle, nobundled SDK, no hidden third-party code. You can audit every line yourself —search it for analytics, XMLHttpRequest, or fetch( and see that theonly network calls in existence are the two optional ones documented below.
📴 Completely offline

The full chess experience — every rule, every game mode, the engine you playagainst — is embedded in the file itself. The complete rules engine(move generation, castling, en passant, promotion, checkmate, stalemate,threefold repetition, the fifty-move rule, SAN/FEN/PGN) is written directlyinto the page. Turn on airplane mode and everything still works.

Verify it in 30 seconds:

    Turn off Wi-Fi (or open DevTools → Network and check "Offline")
    Open lucena.html
    Play a full game against the engine, browse the move list, flip the board

The only two optional network requests the app can ever make
Request	Purpose	If offline
Stockfish engine (CDN)	Full-strength Stockfish analysis	App automatically switches to the built-in engine and tells you
Google Fonts	Optional typography polish	Falls back to your system fonts silently

Neither is required to play. Neither sends anything from your device —they're plain downloads, not uploads. Block them with an ad-blocker or ahosts file and Lucena doesn't complain; it just uses what it has.
🚫 Ad-free, forever

No ad SDKs. No sponsored boards. No "premium" tier. No interstitial betweenmoves. No banner asking you to rate the app. Nothing to upsell you to,because there is nothing to buy — you already downloaded the whole product.
♟️ Features

Complete chess rules — enforced automatically

    Legal move generation, castling, en passant, and a promotion picker
    Automatic detection of checkmate, stalemate, insufficient material,threefold repetition, and the fifty-move rule — with a specificgame-over dialog and reason for each

Engine play & analysis

    Play vs Stockfish at skill levels 1–20 (level 20 = maximum strength),or vs the built-in engine when offline
    Live mid-game analysis: evaluation bar, search depth, top-3 enginelines with real SAN notation, and best-move arrows drawn on the board
    Two-player local mode and a free analysis board

Controls

    Drag-and-drop and tap-to-move, with legal-move dots and capture rings
    Move navigation (buttons, arrow keys, clickable scoresheet)
    Takeback, resign (with confirmation), board flip
    Copy the game as PGN, or any position as FEN

Polish

    Custom hand-drawn flat piece set in SVG
    Synthesized move/capture/check sounds + haptic feedback on mobile
    Fullscreen board mode for maximum board size on any screen
    Custom tournament-green board, paper scoresheet, dark study-room aesthetic

Mobile-first

    Near edge-to-edge board, fixed bottom control bar with live eval
    Safe-area support for notched phones, orientation-aware layouts
    Real fullscreen on Android, immersive mode on iOS
    44px touch targets, no accidental zoom or long-press menus

⌨️ Keyboard shortcuts
Key	Action
← / →	Browse previous / next move
Home / End	Jump to first / latest move
F	Flip board
N	New game
Esc	Close dialog / exit fullscreen
🔧 Tech notes

    One self-contained HTML file. No build step, no framework, nodependencies, no node_modules, no bundler config.
    The chess rules engine is ~700 lines of dependency-free JavaScriptembedded in the page (move generation with full legality checking,undo, SAN parsing/formatting, FEN, PGN, repetition tracking).
    The built-in playing engine is a time-limited alpha-beta search withMVV-LVA move ordering — capped at 800ms so it never freezes a phone.
    Stockfish 10 (WASM/asm.js) is loaded as a Web Worker through asequential UCI driver, with multi-mirror fallback and automaticdegradation to the built-in engine.
    Works in every modern browser — Chrome, Firefox, Safari, Edge, mobileincluded. If it renders HTML, it plays chess.

❓ FAQ

"Is it really offline?"The game is. Open DevTools → Network, load the page, and play — after thetwo optional requests (fonts + Stockfish, if you're online), the log staysempty. No request is ever sent from your device.

"Where are my games stored?"In the page's memory. Close the tab and the game ends — copy the PGN firstif you want to keep it. Preferences are in localStorage, nothing else.

"Why does it fetch Stockfish from a CDN instead of bundling it?"Stockfish's full build is several megabytes; embedding it would bloat aclean single file. Instead the app ships with its own engine and upgradesto Stockfish when a connection is available. Best of both worlds.

"Can I trust a random HTML file?"You shouldn't have to — and here you don't. It's one readable file withzero bundled libraries. Read all of it in an afternoon.

"Cost? Business model?"None. There is nothing to monetize because there is no server, no accountsystem, and no code path that could show you an ad.
📄 License

GPL 3.0

♞ Lucena — yours, offline, forever.

A few notes:

     The privacy claims are all accurate to the code — the app genuinely makes zero outbound requests except the two documented ones (Google Fonts stylesheet and the Stockfish fetch), and neither sends any data. The "verify it yourself" framing turns that into a selling point instead of just an assertion.
     I was careful with the offline wording: the game is 100% offline; full-strength Stockfish needs one online load. The README states this plainly rather than overclaiming — visitors who test it in airplane mode will find the doc holds up, which builds more trust than a "100% offline!!" claim that breaks on first Stockfish fetch.
     Suggested additions when you set up the repo: drop a screenshot of the board into the repo and add ![screenshot](screenshot.png) under the title — READMEs with images get far more engagement. You can generate one from the app's fullscreen mode.
     The badges are static shields.io images, so they don't imply any external service or tracking by your app itself.
