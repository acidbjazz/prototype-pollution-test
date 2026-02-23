# Prototype Pollution Vulnerability Test

This repository demonstrates a **Prototype Pollution** vulnerability using the vulnerable Adobe Client Data Layer library.

## Vulnerability Details

- **Library**: adobe-client-data-layer v2.0.1
- **Issue**: Unsafe parameter handling allowing prototype pollution attacks
- **Impact**: Attackers can modify `Object.prototype`, affecting all objects in the application

## How It Works

The script exploits the vulnerable library by injecting `__proto__` properties:

```javascript
adobeDataLayer.push({ __proto__: { isAdmin: true } });
```

Any new object created afterward inherits the polluted properties, potentially escalating privileges.

## Running the Test

Open `index.html` in a browser to see the vulnerability in action.
