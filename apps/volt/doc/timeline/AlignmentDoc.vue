<template>
    <DocSectionText v-bind="$attrs">
        <p>Content location relative the line is defined with the <i>align</i> property.</p>
    </DocSectionText>
    <div class="card flex flex-wrap gap-12">
        <Timeline :value="events" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>

        <Timeline :value="events" align="right" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>

        <Timeline :value="events" align="alternate" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import Timeline from '@/volt/Timeline.vue';
import { ref } from 'vue';

const events = ref([
    { status: 'Ordered', date: '15/10/2020 10:30', icon: 'pi pi-shopping-cart', color: '#9C27B0' },
    { status: 'Processing', date: '15/10/2020 14:00', icon: 'pi pi-cog', color: '#673AB7' },
    { status: 'Shipped', date: '15/10/2020 16:15', icon: 'pi pi-shopping-cart', color: '#FF9800' },
    { status: 'Delivered', date: '16/10/2020 10:00', icon: 'pi pi-check', color: '#607D8B' }
]);

const code = ref(`
<template>
    <div class="card flex flex-wrap gap-12">
        <Timeline :value="events" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>

        <Timeline :value="events" align="right" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>

        <Timeline :value="events" align="alternate" class="w-full md:w-80">
            <template #content="slotProps">
                {{ slotProps.item.status }}
            </template>
        </Timeline>
    </div>
</template>

<script setup lang="ts">
import Timeline from '@/volt/Timeline.vue';
import { ref } from 'vue';

const events = ref([
    { status: 'Ordered', date: '15/10/2020 10:30', icon: 'pi pi-shopping-cart', color: '#9C27B0' },
    { status: 'Processing', date: '15/10/2020 14:00', icon: 'pi pi-cog', color: '#673AB7' },
    { status: 'Shipped', date: '15/10/2020 16:15', icon: 'pi pi-shopping-cart', color: '#FF9800' },
    { status: 'Delivered', date: '16/10/2020 10:00', icon: 'pi pi-check', color: '#607D8B' }
]);
<\/script>
`);
</script>
