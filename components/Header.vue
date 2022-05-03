<template>
    <header>
        <div class="container">
            <nav class="click-dropdown">
                <NuxtLink to="/" class="navbar-brand"><img src="/img/logo.png" alt="Kondiční jízdy v Praze"></NuxtLink>
                
                <button class="my-navbar-toggler toggler-menu open-drop" @click="open = !open" type="button" aria-label="Menu">
                    <div></div>
                    <div></div>
                    <div></div>
                </button>
                
                <div class="click-dropdown-content navbar-expand" :class="[open? 'open' : '']">
                    <ul>                        
                        <li v-for="hamItem in menu" :key="hamItem.name" @click="open = false"> 
                            <NuxtLink :to="hamItem.link" class=" close-drop">{{ hamItem.name }}</NuxtLink>
                        </li>
                    </ul>
                </div>
                
            </nav>
        </div>
    </header>
</template>

<script>
  export default {
    data() {
      return {
        menu: [
            {
                name: 'O nás',
                link: '#o-nas'
            },
            {
                name: 'Ceník',
                link: '#cenik'
            },
            {
                name: 'Rezervace',
                link: '#rezervace'
            },
            {
                name: 'Kontakt',
                link: '#kontakt'
            }
        ],
        open: false
      }
    },
  }
</script>