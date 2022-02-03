<template>
    <div id="user-page" class="container">
        <button type="button"
        class="btn btn-primary" 
        data-bs-toggle="modal" 
        data-bs-target="#oneModal"
        @click="openModal">
            Launch demo modal
        </button>
        <modal  
        v-if="isModalOpen"
        title="Important Message for You"
        @close="isModalOpen = false">
            <!-- <template v-slot:footer>
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close 1</button>
                <button type="button" class="btn btn-primary">Save changes 1</button>
            </template>  -->
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Assumenda, quo enim. Cupiditate, sunt magni iure illo ipsam, eligendi sint quos numquam officiis consectetur veniam debitis dicta provident, explicabo reprehenderit iusto.</p>
            <p>Laudantium, iste similique? Odio laudantium, inventore ipsa dicta nemo, sapiente laboriosam magnam maxime fugit animi vero, veritatis vitae similique! Officiis esse eos reiciendis. Blanditiis iste atque minima quis inventore omnis.</p>
            <p>Tempora voluptatum blanditiis fugiat a dicta ut molestias ratione exercitationem aperiam totam impedit suscipit quidem voluptatibus quod cupiditate aliquam est, vitae pariatur nostrum saepe provident. Error, repudiandae. Aut, nostrum quam.</p>               
        </modal>
    </div>
</template>

<script>
import Modal from '@/components/Modal'

export default {
    name: 'UserPage',
    components: {Modal},
    data() {
        return {
            isModalOpen: false
        }
    },
    methods: {
        openModal() {
            this.isModalOpen = true
        }
    }
}
</script>

<style scoped>
    #user-page {
        margin-top: 30px;
    }
</style>