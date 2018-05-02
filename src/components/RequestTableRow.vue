<template>
    <tr @click="onClick()">
        <td>{{request.request}}</td>
        <td>{{request.submitDate}}</td>
        <td>{{request.status}}</td>
    </tr>
</template>

<script>
    export default {
        name: 'RequestTableRow',
        props: [
            'request'
        ],
        methods: {
            onClick() {
                console.log('clicked', this.request);
                this.$router.push(`/requests/${this.request.requestId}/events`);
            }
        }
    }
</script>

<style scoped>
    tr {
        cursor: pointer;
    }
    tr:hover {
        background-color: grey;
    }
</style>