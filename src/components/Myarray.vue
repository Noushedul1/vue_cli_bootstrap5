<template>
    <p v-for="c in myarr" key="c">
        {{c}}
    </p>
</template>
<script>
    export default{
        props: {
            myarr:{
                type: Array,
                required: true
            }
        }
    }
</script>
