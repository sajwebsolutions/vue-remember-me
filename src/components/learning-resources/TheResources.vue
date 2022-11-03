<template>
    <ul>
        <li>
            <base-card>
                <base-button @click="setSelectedTab('stored-resources')" :mode="storedSelected">Stored Resources</base-button>
                <base-button @click="setSelectedTab('add-resources')" :mode="addSelected">Add Resources</base-button>
                <div id="gitId"><a href="https://github.com/sajwebsolutions/vue-remember-me" target="_blank">View Code on GitHub</a></div>
            </base-card>
        </li>
    </ul>

    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
</template>


<script>
    import StoredResources from "./StoredResources";
    import AddResources from "./AddResources"

    export default {
        components:{
            StoredResources,
            AddResources
        },
        data(){
            return {
                selectedTab: 'stored-resources',
                storedResources     :   [
                    {
                        "id"            :   "official-guide",
                        "title"         :   "Official Guide",
                        "description"   :   "The Official Vue Js Documentation",
                        "link"          :   "https://vuejs.org"
                    },
                    {
                        "id"            :   "google",
                        "title"         :   "Google",
                        "description"   :   "Learn to Google...",
                        "link"          :   "https://www.google.com"
                    }
                ],
            }
        },
        provide(){
            return {
                resources: this.storedResources,
                addResource:this.addNewResource,
                deleteResource: this.removeResource
            }
        },
        computed:{
            storedSelected(){
                return this.selectedTab === 'stored-resources' ? 'active' : 'inactive';
            },

            addSelected(){
                return this.selectedTab === 'add-resources' ? 'active' : 'inactive';
            }
        },
        methods: {
            setSelectedTab(tab)
            {
                this.selectedTab    =   tab;
            },

            addNewResource(title, des, url)
            {
                const newResource    =  {
                    id: new Date().toISOString(),
                    title: title,
                    description: des,
                    link: url
                };

                this.storedResources.unshift(newResource);
                this.selectedTab = 'stored-resources';
            },

            removeResource(resId)
            {
                /*this.storedResources    =   this.storedResources.filter( (res) => res.id != resId );
                console.log(this.storedResources.length);*/

                //New work-around
                const resIdx        =       this.storedResources.findIndex( (res) => res.id === resId );
                this.storedResources.splice(resIdx, 1);
            }
        }
    }
</script>


<style>
    li{
        list-style-type: none;
        width: 80%;
        margin: 0 auto;
    }

    #gitId{
        float: right;
        margin-top: 10px;
    }
</style>