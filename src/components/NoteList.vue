<template>
    <b-list-group>
        <b-list-group-item button>{{ note.title }} - {{ note.date }}</b-list-group-item>
    </b-list-group>
</template>
<script>
export default {
    props: {
        note: {
            required: true
        }
    }
}
</script>