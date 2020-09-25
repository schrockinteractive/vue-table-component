<template>
    <tr @click="$emit('rowClick', row)">
        <table-cell
            v-for="column in visibleColumns"
            :row="row"
            :column="column"
            :key="column.id"
             :pStyle="row.data.colorBakground"
        ></table-cell>
    </tr>
</template>

<script>
    import TableCell from './TableCell';

    export default {
         props: ['columns', 'row', 'pStyle'],

        components: {
            TableCell,
        },

        computed: {
            visibleColumns() {
                return this.columns.filter(column => ! column.hidden);
            },
        },
    };
</script>
