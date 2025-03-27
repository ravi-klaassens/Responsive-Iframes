# Responsive iFrame

A lightweight, dependency-free JavaScript solution that makes iframes fully responsive by dynamically calculating width and height based on the user's viewport.

## Features

- Makes iframes scale to fill the entire container regardless of screen size
- No dependencies, just pure JavaScript (only ~1KB minified)
- Handles viewport resizing automatically
- Confirmed compatibility with Vimeo embeds
- Works with 16:9 aspect ratio videos by default (customizable)

## Demo

See the [live demo](https://ravi-klaassens.github.io/responsive-iframes/) or check out the `demo.html` file in this repository.

## Installation

### Option 1: Direct download

Download either the full or minified version:
- [responsive-iframe.js](responsive-iframe.js)
- [responsive-iframe.min.js](responsive-iframe.min.js)

### Option 2: CDN

```html
<!-- Full version -->
<script src="https://cdn.jsdelivr.net/gh/ravi-klaassens/responsive-iframes@main/responsive-iframe.js"></script>

<!-- Minified version -->
<script src="https://cdn.jsdelivr.net/gh/ravi-klaassens/responsive-iframes@main/responsive-iframe.min.js"></script>
```

## Usage

1. Add the script to your HTML file:

```html
<script src="responsive-iframe.js"></script>
```

2. Structure your HTML with the proper class names:

```html
<div class="responsive-iframe">
    <div class="embed-container">
        <iframe src="https://player.vimeo.com/video/VIMEO_ID?background=1&autoplay=1&loop=1&byline=0&title=0"
            frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
    </div>
</div>
```

3. Add some basic CSS to your container (optional, as the script adds most needed styles):

```css
.hero {
    position: relative;
    width: 100%;
    height: 100vh;
    overflow: hidden;
}
```

### Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive iFrame Example</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        .hero {
            position: relative;
            width: 100%;
            height: 100vh;
            overflow: hidden;
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="responsive-iframe">
            <div class="embed-container">
                <iframe src="https://player.vimeo.com/video/76979871?background=1&autoplay=1&loop=1&byline=0&title=0"
                    frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
    </section>
    
    <script src="responsive-iframe.js"></script>
</body>
</html>
```

## How It Works

The script:

1. Finds elements with the `.responsive-iframe` class
2. Calculates the optimal dimensions to completely fill the viewport
3. Sets proper CSS positioning to center the iframe
4. Applies a 20% buffer to ensure no edges are visible during transitions
5. Updates dimensions automatically when the browser is resized

## Customization

To modify the script behavior, you can edit the following variables in the source code:

- `aspectRatio`: Change the default 16:9 ratio if needed
- Safety margin: Adjust the `width *= 1.2` and `height *= 1.2` lines to change the overflow buffer

## Browser Compatibility

Works in all modern browsers, including:
- Chrome
- Firefox
- Safari
- Edge

## License

MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Feel free to submit a Pull Request.

## Author

Ravi Klaassens at Paramor©, (paramor.nl) - [GitHub](https://github.com/ravi-klaassens) 