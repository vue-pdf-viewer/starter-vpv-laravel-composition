<script setup lang="ts">
import VPdfAnnotation from "@vue-pdf-viewer/annotation";
import { VPdfViewer, VPVBaseProps } from "@vue-pdf-viewer/viewer";
import { computed, ref, watch } from "vue";

const props = defineProps({
    ...VPVBaseProps,
    title: {
        type: String,
        required: true,
    },
    annotateEnabled: {
        type: Boolean,
        required: false,
        default: false,
    },
} as const);

const viewerRef = ref<InstanceType<typeof VPdfViewer> | null>(null);

const vpvProps = computed(() => {
    // Destructure to exclude title and annotateEnabled from props
    const { title, annotateEnabled, ...baseProps } = props;

    // Create the final props object
    const finalProps = {
        ...baseProps,
    };

    // Add plugins conditionally with proper typing
    if (annotateEnabled) {
        (finalProps as any).plugins = [VPdfAnnotation()];
    }

    return finalProps;
});
watch(viewerRef, (newVal) => {
    if (newVal) {
        console.log("These are VPV instance properties", Object.keys(newVal));
    }
});
</script>
<template>
    <div>
        <h2>
            {{ props.title }}
        </h2>
        <div :style="{ width: '1028px', height: '700px', margin: '0 auto' }">
            <VPdfViewer v-bind="vpvProps" ref="viewerRef" />
        </div>
    </div>
</template>

<style scoped>
h2 {
    font-size: 2.5rem;
    text-align: center;
    font-weight: bold;
}
</style>