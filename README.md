# TheXCode.org Website

A modern, hacker-style website for TheXCode.org, built with Vue.js and featuring cutting-edge animations and effects.

## Features

- Modern Vue.js 3 implementation
- Hacker-style design with glitch effects
- Responsive and interactive UI
- GSAP animations
- Dark theme with matrix-inspired elements
- SpaceX-inspired layout and components

## Technologies Used

- Vue.js 3
- Vite
- GSAP (GreenSock Animation Platform)
- SCSS
- Vue Router
- Three.js (for advanced animations)

## Development

1. Install dependencies:
```bash
npm install
```

2. Run development server:
```bash
npm run dev
```

3. Build for production:
```bash
npm run build
```

## Deployment on DigitalOcean App Platform

1. Create a DigitalOcean account if you don't have one
2. Go to App Platform in the DigitalOcean dashboard
3. Select "Create App"
4. Connect your GitHub repository or upload files directly
5. Select "Static Site" as the application type
6. Configure the following options:
   - Build Command: `npm run build`
   - Output Directory: `dist`
   - HTTP Port: 8080
7. Click "Launch App"

## Project Structure

```
.
├── src/
│   ├── components/     # Vue components
│   ├── views/         # Page components
│   ├── assets/        # Static assets
│   ├── App.vue        # Root component
│   └── main.js        # Entry point
├── public/            # Public assets
├── index.html         # HTML template
├── vite.config.js     # Vite configuration
└── package.json       # Project dependencies
```

## Local Development

To run the site locally:

1. Clone this repository
2. Open `index.html` in your browser

## Contributing

Contributions are welcome. Please open an issue to discuss proposed changes.

## License

All rights reserved © 2024 TheXCode.org 