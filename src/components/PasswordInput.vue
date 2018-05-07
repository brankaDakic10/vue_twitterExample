<template>
    <div>
       <input type="text" v-model="password" />
       <p>{{ status }}</p>
    </div>
</template>

<script>

export default {
    data() {
        return {
           password: '',
           isWeak: true
        }
    },
    methods: {
      
    },
    computed: {
        status() {
            return this.isWeak ? 'Weak' : 'Strong'
        }
    },

   watch: {
        password(newValue) {
            if(newValue.length > 6 && /\d/.test(newValue)) {
                this.isWeak = false
            } else {
                this.isWeak = true;
            }
        }
    }
  
}
</script>