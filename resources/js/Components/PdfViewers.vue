<script setup lang="ts">
import { VPdfViewer } from '@vue-pdf-viewer/viewer';

const toolbarOptions = false;
const pdfSrc =
    'https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf';
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
