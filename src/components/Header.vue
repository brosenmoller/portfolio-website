<template>
    <header class="sticky z-[5] top-0 duration-200 px-6 flex items-center justify-between
     border border-solid py-6 bg-slate-900 border-transparent"
     @mouseleave="HideAllMenus()">
        
        <a href="/" class="font-medium">
            <b class="font-bold">Ben</b> Rosenmöller
        </a>

        <HeaderLinksDesktop :tabs="tabs" :tabsWithChildren="tabsWithChildren" />
        <HeaderLinksMobile :tabs="tabs" :tabsWithChildren="tabsWithChildren" />

    </header>
</template>

<script setup>
    import { ref } from 'vue';
    import HeaderLinksDesktop from './HeaderLinksDesktop.vue';
    import HeaderLinksMobile from './HeaderLinksMobile.vue';

    const tabs = ref([
        {
            name: 'Intro', 
            link: '/#intro' 
        },
        {
            name: 'Skills', 
            link: '/#skills' 
        },
        {
            name: 'Background', 
            link: '/#about' 
        },
        {
            name: 'Timeline', 
            link: '/#timeline' 
        },
        {
            name: 'References', 
            link: '/#refrences' 
        },
    ]);

    const tabsWithChildren = ref([
        {
            active: false,
            name: 'Projects', 
            link: '/#projects',
            children: [
                {
                    name: 'Voxel Smith',
                    link: "/voxel-smith"
                },
                {
                    name: 'Terrain Generation',
                    link: "/terrain-generation"
                },
                {
                    name: 'Enigma Escape',
                    link: "/enigma-escape"
                },
                {
                    name: 'Paint Over War',
                    link: "/paint-over-war"
                },
                {
                    name: 'Under Our Wing',
                    link: "/#under-our-wing"
                },
            ]
        },
        {
            active: false,
            name: 'Hobbies', 
            link: '/#hobbies',
            children: [
                {
                    name: 'Nevas Buildings',
                    link: "/#nevas-buildings"
                },
                {
                    name: 'Music',
                    link: "/#hobby-music"
                },
            ]
        },
    ]);
    
    function HideAllMenus(){
        for (let i = 0; i < tabsWithChildren.value.length; i++) {
            const element = tabsWithChildren.value[i];
            element.active = false;
        }
    }
    
</script>