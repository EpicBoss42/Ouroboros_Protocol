<template>
    <Modal v-model="isOpen">
        <template v-slot:header>
            <h2>Changelog</h2>
        </template>
        <template v-slot:body>
            <details open>
                <summary>v1.0 Ourobori Trials - <time>2021-29-05</time></summary>
                Profectus Creation Jam Release
                <ul>
                    <li class="feature">Added 2 new Broken Cycles Upgrades</li>
                    <li class="feature">Added Ouroboros Trials</li>
                    <li class="balancing">Moved endgame to Primitive Self-Eating Snake completion</li>
                </ul>
            </details>
            <details open>
                <summary>v0.2 First Break - <time>2021-27-05</time></summary>
                This is the second release
                <ul>
                    <li class="feature">Added Hypercycles and Broken Cycles</li>
                    <li class="feature">Added 5 Hypercycle Upgrades and a Broken Cycle Upgrade</li>
                    <li class="feature">Added another Cycles Buyable and Challenge</li>
                    <li class="feature">Created a new layer icon used for Hypercycles and Broken Cycles</li>
                    <li class="balancing">Moved endgame to Hypercyclic Mastery purchased</li>
                </ul>
            </details>
            <details open>
                <summary>v0.1 Cyclical Beginnings - <time>2021-25-05</time></summary>
                This is the first release :D
                <ul>
                    <li class="feature">Added the first 10 Cycles Upgrades</li>
                    <li class="feature">Added the first 2 Cycles Buyables</li>
                    <li class="feature">Added the first Cycles Challenge</li>
                    <li class="feature">Created custom layer icon</li>
                    <li class="balancing">Set endgame to 1 Cycle of Difficulties completion</li>
                </ul>
            </details>
        </template>
    </Modal>
</template>

<script setup lang="ts">
import Modal from "components/Modal.vue";
import { ref } from "vue";

const isOpen = ref(false);

defineExpose({
    open() {
        isOpen.value = true;
    }
});
</script>

<style scoped>
details {
    margin: 10px 0;
    padding-left: 18px;
}

summary {
    cursor: pointer;
    margin-bottom: 10px;
    margin-left: -18px;
}

ul {
    margin: var(--feature-margin) 0;
    background: var(--raised-background);
    border: 2px solid rgba(0, 0, 0, 0.125);
    padding: 5px 5px 5px 15px;
    list-style: inside;
}

li {
    margin: 8px 0;
}

li::before {
    padding: 2px 8px;
    margin-right: 8px;
    border-radius: var(--border-radius);
}

.feature::before {
    content: "Feature";
    background: var(--accent1);
}

.fix::before {
    content: "Fix";
    background: var(--accent2);
}

.balancing::before {
    content: "Balancing";
    background: var(--accent3);
}

.breaking::before {
    content: "Breaking";
    background: var(--danger);
}
</style>
