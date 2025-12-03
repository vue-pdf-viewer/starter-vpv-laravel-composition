<script setup lang="ts">
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { VPdfViewer } from '@vue-pdf-viewer/viewer';

const toolbarOptions = false;
const pdfSrc =
    'https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2
                class="text-xl font-semibold leading-tight text-gray-800 dark:text-gray-200"
            >
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div
                    class="overflow-hidden bg-white shadow-sm sm:rounded-lg dark:bg-gray-800"
                >
                    <div class="p-6 text-gray-900 dark:text-gray-100">
                        You're logged in!
                    </div>
                </div>
            </div>
        </div>
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
    </AuthenticatedLayout>
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
