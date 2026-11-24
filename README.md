# Nexus — Steezy Stunter Cheat

A client-side save editor for **Steezy Stunter**, featuring the VANTA interface.

## Features

- Edit your in-game cash balance.
- Modify bike and stage records.
- Customize wheelie distances and best scores.
- Edit challenge records.
- Animated VANTA mod-menu-style interface.
- Saves changes directly to browser local storage.
- Automatically loads the latest payload from GitHub.

## Installation

1. Open Steezy Stunter in your browser.
2. Open Developer Tools (`F12`).
3. Navigate to the **Console** tab.
4. Paste the loader below and press Enter.

### Auto Loader

The loader automatically downloads and executes the latest version of the payload hosted in this repository.

```javascript
(async () => {
    const url = "https://github.com/furryfemboyuh/Nexus---Steezy-Stunter-Cheat/raw/refs/heads/main/payload";

    try {
        console.log("[NEXUS] Downloading payload...");

        const response = await fetch(url);

        if (!response.ok) {
            throw new Error(`HTTP ${response.status}: ${response.statusText}`);
        }

        const script = await response.text();

        if (!script.trim()) {
            throw new Error("Payload is empty.");
        }

        console.log("[NEXUS] Payload downloaded. Executing...");

        (0, eval)(script);

        console.log("[NEXUS] Successfully executed!");
    } catch (error) {
        console.error("[NEXUS] Failed to load payload:", error);
    }
})();
```

## Repository

**GitHub:** [Nexus — Steezy Stunter Cheat](https://github.com/furryfemboyuh/Nexus---Steezy-Stunter-Cheat)

**Payload:** [View raw payload](https://github.com/furryfemboyuh/Nexus---Steezy-Stunter-Cheat/raw/refs/heads/main/payload)

## Disclaimer

This project is provided for educational and personal customization purposes.

Only execute scripts you trust. The loader executes remotely hosted JavaScript in the current page context, meaning changes to the hosted payload can affect what gets executed.

Nexus is an independently maintained project and is not affiliated with the developers of Steezy Stunter.
