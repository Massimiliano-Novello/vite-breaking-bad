<script>
import { store } from '../store';

export default {
    name: "SearchBar",
    data() {
        return {
            store,
            archetypeOption: ["Alien", "Ally of Justice", "Ancient Gear"]
        }
    }
}
</script>

<template>
    <div class="text-center py-4">
        <select name="archetype" id="archetype" v-model="store.archetypeSelect" @change="$emit('search')">
            <option value="">All</option>
            <option :value="type" v-for="(type, index) in archetypeOption" :key="index">{{ type }}</option>
        </select>
    </div>


</template>

<style lang="scss" scoped></style>