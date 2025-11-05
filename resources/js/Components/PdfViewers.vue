<script setup lang="ts">
import { VPdfViewer, useLicense } from '@vue-pdf-viewer/viewer';
import { onBeforeMount } from 'vue';

const toolbarOptions = false;
const pdfSrc =
    'https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf';

// `useLicense` is recommended to be used in the app.ts file
// this is just an example of using the license in component which is not recommended
// because it will be loaded on every component mount
// onBeforeMount(() => {
//     useLicense(
//         'YOUR_LICENSE_TOKEN',
//     );
// });
</script>

<template>
    <h2>Default Toolbar</h2>
    <div class="pdf-viewer-wrapper">
        <VPdfViewer :src="pdfSrc" />
    </div>
    <h2>Without Toolbar</h2>
    <div class="pdf-viewer-wrapper">
        <VPdfViewer :src="pdfSrc" :toolbar-options="toolbarOptions" />
    </div>
    <h2>Mobile</h2>
    <div class="pdf-viewer-wrapper-mobile">
        <VPdfViewer :src="pdfSrc" />
    </div>
</template>
<style scoped>
h2 {
    font-size: 2.5rem;
    text-align: center;
    font-weight: bold;
}
.pdf-viewer-wrapper {
    width: 1028px;
    height: 700px;
    margin: 0 auto;
}

.pdf-viewer-wrapper-mobile {
    width: 768px;
    height: 700px;
    margin: 0 auto;
}
</style>
