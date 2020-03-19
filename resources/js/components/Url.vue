<template>
        <div>
            <a :href="field.value"
                :title="field.title || field.value"
                v-if="field.value && clickable"
                class="cursor-pointer dim no-underline text-primary flex"
                :class="`text-${field.textAlign}`"
                :target="field.sameTab ? '_self' : '_blank'"
                :rel="field.rel"
            >
                <span class="block truncate">
                    {{ field.label ? field.label : field.value }}
                </span>
            </a>
            <span v-else-if="field.value" class="block truncate" :class="`text-${field.textAlign}`">{{ field.value }}</span>
            <span v-else :class="`text-${field.textAlign}`">&mdash;</span>
        </div>
</template>

<script>
export default {
    props: ['resource', 'resourceName', 'resourceId', 'field', 'clickable'],
}
</script>
