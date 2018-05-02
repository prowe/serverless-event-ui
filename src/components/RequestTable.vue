
<template>
    <table>
        <tbody>
            <tr v-for="r in requests" :key="r.id">
                <td>{{r.status}}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        name: 'RequestTable',
        data() {
            return {
                requests: [
                    {
                        id: 'a',
                        status: 'A'
                    },
                    {
                        id: 'b',
                        status: 'B'
                    }
                ]
            };
        },

    }
</script>