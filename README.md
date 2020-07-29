Evil Jest SVG Transformer
=========================

Make SVGs work with Jest (just make Jest not error out).

Install with either `yarn` or `npm`

## Yarn

```bash
yarn add --dev @superevilmegaco/jest-evil-svg-transformer
```

## NPM

```bash
npm i --save-dev @superevilmegaco/jest-evil-svg-transformer
```

Put this in your `jest.config.json`:

```json
{
	"transform": {
		"^.+\\.js$": "babel-jest",
		"^.+\\.svg$": "@superevilmegaco/jest-evil-svg-transformer"
	}
}
```

And Jest won't error out on lines like this:

```javascript
import UIIcons from "./icons.svg";

if (!document.getElementById("evil-icons")) {
	const iconContainer = document.createElement("div");
	iconContainer.id = "evil-icons";
	iconContainer.style.display = "none";
	iconContainer.innerHTML = UIIcons;
	document.body.appendChild(iconContainer);
}
```

