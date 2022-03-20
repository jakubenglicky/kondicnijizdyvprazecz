<template>
    <header>
        <div class="container">
            <nav class="click-dropdown">
                <NuxtLink to="/" class="navbar-brand"><img src="/img/logo.png" alt="Kondiční jízdy v Praze"></NuxtLink>
                
                <button class="my-navbar-toggler open-drop" type="button" aria-label="Menu">
                <svg class="icon" width="21" height="21"><use xlink:href="#hamburger"></use></svg>
                </button>
                
                <div class="click-dropdown-content navbar-expand">
                    <ul>                        
                        <li v-for="hamItem in menu" :key="hamItem.name"> 
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
      }
    },
  }
</script>