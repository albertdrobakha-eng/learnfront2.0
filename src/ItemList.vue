

<script setup>
import { computed } from 'vue';

const props = defineProps(['items', 'title']);

const importanceOrder = {
    high: 1,
    medium: 2,
    low: 3
};

const sortedItems = computed(() =>
    [...props.items].sort((a, b) =>
        importanceOrder[a.importance] - importanceOrder[b.importance]
    )
);
</script>

<template>
    <h1>{{ title }}</h1>
    <ul>
        <li
            v-for="item in sortedItems"
            :key="item.id"
            :class="['importance-' + item.importance, { done: item.isDone }]"
        >
            {{ item.text }}

            <input type="checkbox" v-model="item.isDone">

            <select v-model="item.importance">
                <option value="high">🔴 High</option>
                <option value="medium">🟠 Medium</option>
                <option value="low">🟢 Low</option>
            </select>
        </li>
    </ul>
</template>

<style scoped>
li {
    padding: 8px;
    margin-bottom: 5px;
    border-left: 5px solid;
}

.importance-high {
    background-color: #ffcccc;
    border-color: #e53935;
}

.importance-medium {
    background-color: #ffe0b2;
    border-color: #fb8c00;
}

.importance-low {
    background-color: #c8e6c9;
    border-color: #43a047;
}

.done {
    opacity: 0.7;
}
</style>