<template>
    <div class="page_wrap_vue">
        <v-tabs dark v-model="active">
            <v-tabs-bar class="cyan">
                <v-tabs-item href="#files" ripple>
                    Files
                </v-tabs-item>
                <v-tabs-item href="#manage-groups" ripple>
                    Manage File Groups
                </v-tabs-item>
                <v-tabs-item href="#upload" ripple>
                    Upload
                </v-tabs-item>
                <v-tabs-slider class="yellow"></v-tabs-slider>
            </v-tabs-bar>
            <v-tabs-items>
                <v-tabs-content id="files">
                    <v-card flat>
                        <v-card-text>
                            <file-lists></file-lists>
                        </v-card-text>
                    </v-card>
                </v-tabs-content>
                <v-tabs-content id="manage-groups">
                    <v-card flat>
                        <v-card-text>
                            <file-group-lists></file-group-lists>
                        </v-card-text>
                    </v-card>
                </v-tabs-content>
                <v-tabs-content id="upload">
                    <v-card flat>
                        <v-card-text>
                            <file-upload></file-upload>
                        </v-card-text>
                    </v-card>
                </v-tabs-content>
            </v-tabs-items>
        </v-tabs>
    </div>
</template>

<script>
    import FileGroupLists from '../components/file/FileGroupLists.vue';
    import FileUpload from '../components/file/FileUpload.vue';
    import FileLists from '../components/file/FileLists.vue';
    export default {
        components: {
            FileUpload,
            FileGroupLists,
            FileLists
        },
        mounted() {
            console.log('pages.FileManager.vue');

            const self = this;
        },
        data() {
            return {
                active: ''
            }
        },
        watch: {
            active(v) {
                console.log('active tab: ' + v);
            }
        },
        methods: {
        }
    }
</script>

<style scoped="">
    .finder_wrap {
        padding: 0 20px;
    }
</style>