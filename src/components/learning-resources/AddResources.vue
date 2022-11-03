<template>
    <base-dialog v-if="inputIsInvalid" title="Invalid Input" @close="confirmError">
        <template #default>
            <p>No Value Entered</p>
            <p>Please check the input field and fill all the inputs</p>
        </template>
        <template #actions>
            <base-button @click="confirmError" mode="active">Okay</base-button>
        </template>
    </base-dialog>

    <ul>
        <li>
            <base-card>
        <form @submit.prevent="submitData">
            <div class="form-control">
                <label for="title">Title</label>
                <input type="text" id="title" name="title" ref="titleinput">
            </div>

            <div class="form-control">
                <label for="description">Description</label>
                <textarea name="description" id="description" cols="30" rows="10" ref="desinput"></textarea>
            </div>

            <div class="form-control">
                <label for="link">Link</label>
                <input type="text" id="link" name="link" ref="linkinput">
            </div>

            <div>
                <base-button type="submit" mode="active">Add Resource</base-button>
            </div>
        </form>
    </base-card>
        </li>
    </ul>
</template>


<script>
    export default {

        inject:['addResource'],
        data() {
            return {
                inputIsInvalid: false
            }

        },
        methods:{
            submitData()
            {
                const titleinput    =   this.$refs.titleinput.value;
                const desinput      =   this.$refs.desinput.value;
                const linkinput     =   this.$refs.linkinput.value;

                if( titleinput.trim()   === '' || desinput.trim()   === '' || linkinput.trim()   === '' )
                {
                    this.inputIsInvalid =   true;
                    return;
                }

                this.addResource(titleinput, desinput, linkinput);
            },

            confirmError()
            {
                this.inputIsInvalid =   false;
            }
        }
    }
</script>

<style>


    input, textarea{
        display: block;
        width: 100%;
        font: inherit;
        padding: 0.15rem;
        border: 1px solid #ccc;
    }


    input:focus,
    textarea:focus{
        outline: none;
        border-color: #3a0061;
        background: #f7ebff;
    }


    .form-control{
        margin: 1rem 0;
    }
</style>