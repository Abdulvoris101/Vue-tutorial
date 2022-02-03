<template>
   <div id="modal">
    <div class="modal fade" id="oneModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
        <div class="modal-content">
        <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">{{ title }}</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body"
        @scroll="onBodyScroll"
        ref="modalBody">
            <slot name="default"></slot>
        </div>
        <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary" :disabled="!isRulesReaded">Accepting</button>
        </div>
        </div>
    </div>
    </div>

   </div>
</template>

<script>
export default {
    name: 'Modal',
    props: {
        title: {
            type: String,
            default: ''
        }   
    },
    data() {
        return {
            isRulesReaded: false,
        }
    },
    methods: {
        closeModal() {
            this.$emit('close')
        },
        onBodyScroll() {
            const modalBody = this.$refs.modalBody
            if(modalBody.clientHeight + modalBody.scrollTop >= modalBody.scrollHeight) {
                this.isRulesReaded = true
            }
        }
    }
}
</script>

<style scoped>
    .modal-body {
        height: 200px;
        overflow-y: scroll;
    }
</style>