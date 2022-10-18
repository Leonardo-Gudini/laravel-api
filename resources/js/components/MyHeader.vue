<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <a class="navbar-brand" href="#">Boolpress</a>

            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarNav">
                <ul v-for="(item, index) in navItems" class="navbar-nav" :key="index">
                    <li class="nav-item">
                        <a class="nav-link" :href="item.link">{{ item.name }}</a>
                    </li>
                </ul>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'MyHeader',
    data() {
        return{
            navItems: [
                {
                    name: 'home',
                    link: '#'
                },
                {
                    name: 'blog',
                    link: '#'
                },
                {
                    name: 'info',
                    link: '#'
                },
            ]
        }
    }
}
</script>

<style>

</style>