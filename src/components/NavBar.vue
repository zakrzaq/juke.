<script setup lang="ts">
import Logo from "/src/assets/logo-vec.svg";

interface Props {
  activeId?: number;
}

const props = withDefaults(defineProps<Props>(), {
  activeId: undefined,
});

const emit = defineEmits<{
  setActive: [id: number] 
}>()

const links = [
  { id: 2, name: "about", to: "#" },
  { id: 3, name: "services", to: "#" },
  { id: 4, name: "projects", to: "#" },
  { id: 5, name: "clients", to: "#" },
  { id: 6, name: "contact", to: "#" },
];

const setActive = (id: number) => emit("setActive", id)
</script>

<template>
  <nav class="px-12 py-8 flex justify-between">
    <img :src="Logo" alt="juke sites logo" class="w-20" />
    <ul class="flex gap-4">
      <li
        v-for="link in links"
        :key="link.id"
        :class="[
          'flex justify-center items-center hover:text-white',
          link.id === activeId ? 'text-white' : 'text-gray-500',
        ]"
        @click="setActive(link.id)"
      >
        <a :href="link.to">
          {{ link.name }}
        </a>
      </li>
    </ul>
  </nav>
</template>
