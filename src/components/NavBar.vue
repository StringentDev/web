<template>
    <nav class="bg-white dark:bg-gray-100">
        <TabGroup as="div" class="mt-2">
            <div class="border-b border-gray-200">
                <TabList class="-mb-px flex px-4 space-x-8">
                    <Tab v-for="category in navigation.categories" :key="category.name"
                        >
                        <router-link :to="`/${category.path}`">
                            <button
                                :class="[category.selected ? 'text-indigo-600 border-indigo-600' : 'text-gray-900 border-transparent', 'flex-1 whitespace-nowrap py-4 px-1 border-b-2 text-base font-medium']">
                                {{ category.name }}
                            </button>
                        </router-link>
                    </Tab>
                </TabList>
            </div>
        </TabGroup>
    </nav>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import {
    Tab,
    TabGroup,
    TabList,
} from '@headlessui/vue'
const navigation = {
    categories: [
        {
            id: 'home',
            name: 'Home',
            path: '',
            selected: false,
        },
        {
            id: 'blogs',
            name: 'Blogs',
            path: 'b',
            selected: false,
        },
        {
            id: 'contact',
            name: 'Contact Me',
            path: '@me',
            selected: false,
        },
    ],
    pages: [
        { name: 'Company', href: '#' },
        { name: 'Stores', href: '#' },
    ],
}

// on navigation change, set tab with correct path to selected and others not
const router = useRouter()
navigation.categories.forEach(category => {
    if (category.path !== router.path) {
        category.selected = false
    } else {
        category.selected = true
    }
})




</script>