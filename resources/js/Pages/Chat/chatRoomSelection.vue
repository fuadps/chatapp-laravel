<template>
    <div class="grid grid-cols-2">
        <div class="font-bold text-xl">
            {{ selected.name }} Chat
        </div>
        <div>
            <select class="float-right" v-model="selected" @change="$emit('roomchanged', selected)">
                <option v-for="(room, index) in rooms" :key="index" :value="room">{{ room.name }}</option>
            </select>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['rooms', 'currentRoom'],
        data: function () {
            return {
                selected: {},
            }
        },
        created() {
            this.selected = this.currentRoom
            console.log(this.rooms, this.currentRoom)
        }
    }
</script>

<style scoped>

</style>
