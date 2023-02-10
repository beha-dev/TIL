# Tailwind 정리

## Get started with Tailwind CSS
- Install Tailwind CSS
```
npm install -D tailwindcss -> make package.json
npx tailwindcss init -> make tailwind.config.js
```
- Configure your template paths
    - Add the paths to all of your template files in your tailwind.config.js file.
    ```
    content: ["./src/**/*.{html,js}"],
    ```
- Add the Tailwind directives to your CSS
    - Add the @tailwind directives for each of Tailwind’s layers to your main CSS file.
    ```
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
- Start the Tailwind CLI build process
    - Run the CLI tool to scan your template files for classes and build your CSS.
    ```
    npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
    ```
- Start using Tailwind in your HTML
    - Add your compiled CSS file to the ```<head>``` and start using Tailwind’s utility classes to style your content.