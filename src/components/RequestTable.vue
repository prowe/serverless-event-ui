
<template>
    <table>
        <thead>
            <tr>
                <th>Request</th>
                <th>Submitted</th>
                <th>Status</th>
            </tr>
        </thead>
        <tbody>
            <request-table-row 
                v-for="req in requests" 
                :key="req.requestId" 
                v-bind:request="req" /> 
        </tbody>
    </table>
</template>

<script>
    import RequestTableRow from './RequestTableRow.vue';

    export default {
        name: 'RequestTable',
        components: {
            RequestTableRow
        },
        data() {
            return {
                requests: []
            };
        },
        async created() {
            const response = await fetch('https://fipc0nsvhg.execute-api.us-east-1.amazonaws.com/Prod/requests');
            if (response.ok) {
                this.requests = await response.json();
            }
        }
    }
</script>

<style scoped>
    table {
        width: 100%;
    }
</style>