<template>
    <form @submit.prevent="onSubmit">
        <h2 class="label-wrapper">
        <label for="new-todo-input" class="label__lg">
            What Needs To Be Done?
        </label>
        </h2>
        <input type="text" id="new-todo-input" name="new-todo" autocomplete="off" v-model="label" class="input__lg">
        <button type="submit" class="btn btn__primary btn__lg">Add</button>
    </form>
</template>

<script>    
    export default {
        methods: {
            onSubmit() {
                if(this.label === '') // ne dozvoluva da se pojavi item pri submit na prazno pole
                    return;
                this.$emit("todo-added", this.label)
                this.label = '' // po dodavanjeto na nov element da se brishe input poleto
            }
        },
        data() {
            return {
                label: ""
            }
        }
    };
</script>