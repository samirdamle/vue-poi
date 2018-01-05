<template>
    <div id="app">
        Hello {{ msg }}
        <div>
            Computed message: {{ someComputedMsg }}
        </div>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue'
    import Component from 'vue-class-component';

    @Component({
        props: {
            age: {
                type: Number,
                required: false
            }
        }
    })
    export default class App extends Vue {
        msg: string;

        constructor () {
            super();
            this.msg = 'Vue'
        }

        mounted () {
            this.msg = 'mounted!'
            this.greet('Bob')
        }

        // computed
        get someComputedMsg () {
            return 'computed ' + this.msg
        }

        greet (name: string) {
            console.log('Hello ' + name + '!');
        }
    }

    /*
    export default Vue.extend({
        props: {
            age: {
                type: Number,
                required: false
            }
        },
        data() {
            return {
                msg: 'World'
            }
        },
        computed: {

        },
        methods: {

        }
    })
    */
</script>
