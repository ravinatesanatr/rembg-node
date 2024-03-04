# Rembg Node


```bash
yarn add sharp rembg-node

npm install sharp rembg-node
```

## Example

<img height="180" src="https://user-images.githubusercontent.com/8362329/178584133-4aa2483a-8b9c-4f7b-a785-ddcba800e57f.png"/>

```ts
import { Rembg } from "rembg-node";
import sharp from "sharp";

// const { Rembg } = require("rembg-node");
// const sharp = require("sharp");

(async () => {
	const input = sharp("test-input.jpg");

	// optional arguments
	const rembg = new Rembg({
		logging: true,
	});

	const output = await rembg.remove(input);

	await output.webp().toFile("test-output.webp");

	// optionally you can use .trim() too!
	await output.trim().webp().toFile("test-output-trimmed.webp");
})();
```
