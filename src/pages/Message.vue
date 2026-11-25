<script setup>
import Message from '../components/Message.vue';

const examples = [
    { color: 'primary', title: 'Primary', text: 'A primary message for general highlights.' },
    { color: 'link', title: 'Link', text: 'A link message for helpful references.' },
    { color: 'info', title: 'Information', text: 'Your changes have been saved.' },
    { color: 'success', title: 'Success', text: 'The operation completed successfully.' },
    { color: 'warning', title: 'Warning', text: 'Please review this information before continuing.' },
    { color: 'danger', title: 'Error', text: 'Something went wrong. Please try again.' },
];
</script>

<template>
    <section>
        <h1 class="title">Message component</h1>
        <p class="mb-5">
            A reusable Bulma message with a validated <code>color</code> prop and an optional
            <code>title</code>. Put the message text or other content in its default slot.
        </p>

        <Message
            v-for="example in examples"
            :key="example.color"
            :color="example.color"
            :title="example.title"
        >
            {{ example.text }}
        </Message>

        <h2 class="subtitle mt-5">Without a title</h2>
        <Message>This message uses the default <code>info</code> color.</Message>

        <div class="content mt-5">
            <h2 class="subtitle">Props</h2>
            <ul>
                <li><code>color</code>: optional string; accepts primary, link, info, success, warning, or danger. Defaults to info.</li>
                <li><code>title</code>: optional string; the header is omitted when it is empty.</li>
                <li>Default slot: message body content.</li>
            </ul>
            <p>Vue reports a development warning if a supplied prop has the wrong type or an unsupported color.</p>
        </div>
    </section>
</template>
