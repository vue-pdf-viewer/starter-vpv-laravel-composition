# VPV Starter Toolkit in Laravel and Vue 3 (Composition API)

Welcome to the Vue PDF Viewer (VPV) starter toolkit! This repository provides a comprehensive guide on how to use VPV with Vue 3 in Laravel project via the Composition API. This repo showcases how VPV can be integrated and rendered as part of a Laravel and Vue project.

## Table of Contents

-   [Installation](#installation)
-   [Usage](#usage)
    -   [Project Setup](#project-setup)
    -   [Running the Example Project](#running-the-example-project)
-   [Examples](#examples)

## Installation

To get started, please clone this repo to your local machine and install the dependencies:

```bash
git clone https://github.com/your-username/starter-vpv-laravel.git
cd starter-vpv-laravel
composer install

npm install

```

## Usage

### Project Setup

1. **Clone the Repository**: If you haven't already, clone the repository and navigate into the project directory.

    ```bash
    git clone https://github.com/your-username/starter-vpv-laravel.git
    cd starter-vpv-laravel
    ```

2. **Install Dependencies**: Install the necessary dependencies using npm

    ```bash
    npm install
    ```

### Running the Example Project

This repo includes an example project to demonstrate how to use VPV. To run the example project:

1. **Prepare Laravel**: Ensure Laravel is properly configured before running the application

    - Ensure there is an `APP_KEY` by running:

    ```bash
    php artisan key:generate
    ```

    - Ensure the database exists by creating a `database.sqlite` file in the `database/` folder, then run migrations:

    ```bash
    touch database/database.sqlite
    php artisan migrate
    ```

2. **Serve the Application**: Use the following command to start the development server

    ```bash

    npm run dev
    # Open another terminal
    php artisan serve
    ```

3. **Open in Browser**: Open your browser and navigate to `http://localhost:8000` (or the port specified in your terminal) to see the example project in action

### Using the VPV Component

Once the example project is running, you may explore the source code to see how the VPV component is integrated. Here is a brief overview:

1. **Import the component**: Import the desired VPV component into your Vue file

    ```js
    <script setup>import {VPdfViewer} from '@vue-pdf-viewer/viewer';</script>
    ```

2. **Use the component in the template**: Add the VPV component to your template section

    ```html
    <template>
        <div :style="{ width: '1028px', height: '700px'}">
            <VPdfViewer
                src="https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf"
            />
        </div>
    </template>
    ```

### Using the Vue PDF Viewer Component with Annotation

In this starter, we provide `resources/js/components/AppPdfViewer.vue` as an example of how to use the annotation features within the viewer. Here’s a brief overview:

1. **Import the component and plugin**: Import the Vue PDF Viewer component along with the annotation plugin into your Vue file.

   ```vue
   <script setup lang="ts">
    import { VPdfViewer } from '@vue-pdf-viewer/viewer'
    import VPdfAnnotation from "@vue-pdf-viewer/annotation"
   </script>
   ```

2. **Use the component with the plugin in your template**: Add the Vue PDF Viewer component to the template and pass the annotation plugin through the `plugins` prop.

   ```html
   <template>
      <div :style="{ width: '1028px', height: '700px'}">
        <VPdfViewer
          src="https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf"
          :plugins="[VPdfAnnotation()]"
        />
      </div>
   </template>
   ```

## Examples

For more examples, please refer to the `/resources/js/Components/PdfViewers.vue` file in this repository:

-   Default Toolbar
-   Without Toolbar
-   Mobile View

_Remark: If you would like more examples, feel free to open an issue._

For more configurations, please check the [documentation](https://docs.vue-pdf-viewer.dev) site.

---

Thank you for using VPV! We hope this toolkit helps you build amazing Vue 3 applications. If you have any questions or need further assistance on this example, please feel free to open an issue. Happy coding!
