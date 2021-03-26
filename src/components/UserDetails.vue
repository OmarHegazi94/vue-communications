<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>User ID {{ UserID }}</p>
    <p>User Name: {{ UserData.name }} | Status: {{ UserData.status }}</p>
    <button @click="resetID(newID)">Reset ID</button>
    <button @click="changeUserData(newData)">Change Data</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            newID: 50,
            newData: {
                name: 'KOKO WAWA',
                status: 'Offline'
            }
        }
    },
    props: {
        UserID: {
            type: Number,
            default: 1
        },
        UserData: {
            name: {
                type: String,
                default: 'Omar'
            },
            status: {
                type: String,
                default: 'Unknowen'
            }
        }
    },
    emits: ['update:UserID', 'update:UserData'],
    methods: {
        resetID(newID) {
            this.$emit('update:UserID', newID)
        },
        changeUserData(newData) {
            this.$emit('update:UserData', newData);
        }
    }
}
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
