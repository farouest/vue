<template>
    <JqxSplitter :theme="'material'"
        :width="850" :height="400" :panels="[{ size: 250 }]">
        <div>

            <JqxTree :theme="'material'"
                @select="select($event)"
                :width="'100%'" :height="'100%'">
                <ul>
                    <li id="Mail" item-expanded='true'>
                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/mailIcon.png' /><span item-title="true">Mail</span>
                        <ul>
                            <li id="Calendar" item-expanded='true'>
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/calendarIcon.png' /><span item-title="true">Calendar</span>
                            </li>
                            <li id="Contacts">
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/contactsIcon.png' /><span item-title="true">Contacts</span>
                            </li>
                            <li id="Inbox">
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true"><span>Inbox</span><span style='color: Blue;'> (3)</span></span>
                                <ul>
                                    <li id="jQWidgets">
                                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">jQWidgets</span>
                                        <ul>
                                            <li id="Admin">
                                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Admin</span>
                                            </li>
                                            <li id="Corporate">
                                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Corporate</span>
                                            </li>
                                            <li id="Finance">
                                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Finance</span>
                                            </li>
                                            <li id="Other">
                                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Other</span>
                                            </li>
                                        </ul>
                                    </li>
                                    <li id="Personal">
                                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Personal</span>
                                    </li>
                                </ul>
                            </li>
                            <li id="Deleted Items" item-expanded='true'>
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/recycle.png' /><span item-title="true"><span>Deleted Items</span><span style='color: Blue;'> (10)</span></span>
                                <ul>
                                    <li id="Today">
                                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Today</span>
                                    </li>
                                    <li id="Last Week">
                                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Last Week</span>
                                    </li>
                                    <li id="Last Month">
                                        <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/folder.png' /><span item-title="true">Last Month</span>
                                    </li>
                                </ul>
                            </li>
                            <li id="Notes">
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/notesIcon.png' /><span item-title="true">Notes</span>
                            </li>
                            <li id="Settings">
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/settings.png' /><span item-title="true">Settings</span>
                            </li>
                            <li id="Favorites">
                                <img style='float: left; margin-right: 5px;' src='https://www.jqwidgets.com/vue/images/favorites.png' /><span item-title="true">Favorites</span>
                            </li>
                        </ul>
                    </li>
                </ul>
            </JqxTree>
        </div>
        <div ref="ContentPanel"></div>
    </JqxSplitter>
</template>

<script>
    import JqxSplitter from 'jqwidgets-scripts/jqwidgets-vue/vue_jqxsplitter.vue';
    import JqxTree from 'jqwidgets-scripts/jqwidgets-vue/vue_jqxtree.vue';

    export default {
        components: {
            JqxSplitter,
            JqxTree
        },
        methods: {
            select: function (event) {
                this.$refs.ContentPanel.innerHTML = '<div style="margin: 10px;">' + event.args.element.id + '</div>';
            }
        }
    }
</script>

<style>
  
    .jqx-tree {
        border: none;
    }
  
</style>