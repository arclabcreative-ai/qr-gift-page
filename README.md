# Sweet QR Surprise Page

This is a deliberately simple static landing page for a QR-code surprise. It uses only `index.html` and PNG images, so it can be opened locally or deployed to any static hosting service.

## Files Used By The Page

Keep this deployable structure. Filenames and capitalization must match exactly:

```text
index.html
assets/
  Meow.png
  Forget_Me_Not_&_Iris_Flower.png
  Angie01.png
README.md
```

- `assets/Meow.png` is shown before the visitor taps.
- `assets/Forget_Me_Not_&_Iris_Flower.png` is shown after the visitor taps.
- `assets/Angie01.png` appears further down after the blessing message.

## Place Or Replace The PNG Files

1. Create an `assets` folder beside `index.html` if it does not already exist.
2. Put the first image in `assets/` and name it `Meow.png`.
3. Put the revealed image in `assets/` and name it `Forget_Me_Not_&_Iris_Flower.png`.
4. Put the extra memory image in `assets/` and name it `Angie01.png`.
5. Keep PNG files transparent if transparency is part of the artwork. The page displays images without cropping them.

To use different filenames, edit these two values near the bottom of `index.html`:

```js
const firstImage = "assets/Meow.png";
const afterImage = "assets/Forget_Me_Not_&_Iris_Flower.png";
const memoryImageFile = "assets/Angie01.png";
```

Also update the initial image `src="assets/Meow.png"` in the `<img>` element so the first image appears before JavaScript runs.

## Edit The Messages

Open `index.html` in a text editor.

For the before-tap message, find this comment and edit the text immediately below it:

```html
<!-- Edit the before-tap message below. -->
```

For the after-tap blessing, find this comment and edit the paragraphs inside the blessing card:

```html
<!-- Edit the after-tap blessing below. Keep each thought in its own paragraph. -->
```

Use separate `<p>...</p>` blocks for comfortable spacing, and use `<br>` where a deliberate line break is wanted inside one thought.

## Test Locally

Double-click `index.html`, or drag it into a browser window. Tap or click anywhere on the main card:

- It should first show `assets/Meow.png` with the invitation text.
- On the first tap, it should fade to `assets/Forget_Me_Not_&_Iris_Flower.png` and reveal the blessing card.
- Scrolling down should reveal `assets/Angie01.png` below the blessing message.
- Further taps should not change it back.

Because all file paths are relative and there are no dependencies, opening `index.html` directly works without a local server.

## Deploy With GitHub Pages

1. Create a GitHub repository and upload `index.html`, `README.md`, and the `assets/` folder to its root.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the `main` branch and the `/ (root)` folder, then save.
5. When publishing finishes, open the URL GitHub provides, such as `https://your-name.github.io/your-repository/`.

## Deploy With Netlify

1. Sign in to Netlify and choose **Add new project > Deploy manually**.
2. Drag the project folder containing `index.html`, `README.md`, and `assets/` into the deploy area.
3. Once deployment finishes, open the generated Netlify URL.
4. Optionally set a custom site name or custom domain in Netlify settings.

No build command or publish configuration is required.

## Deploy With Cloudflare Pages

1. In Cloudflare, open **Workers & Pages** and choose **Create > Pages > Upload assets**.
2. Name the project and upload the folder containing `index.html`, `README.md`, and `assets/`.
3. Deploy the site and open its provided `pages.dev` URL.

For a Git-connected Pages project instead, connect the repository and use no build command; set the output directory to the repository root.

## Create The QR Code

1. Deploy the page and open its final public URL on a phone to confirm the image switch works.
2. Copy that exact HTTPS URL.
3. Paste the URL into a trusted QR-code generator or a browser/share tool that creates QR codes.
4. Download the QR image and test-scan it before printing or sharing.

The QR code should point to the deployed website URL, not to `index.html` on your computer.
