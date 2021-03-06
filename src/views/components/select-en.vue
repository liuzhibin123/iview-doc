<style lang="less">
    .ivu-article .ivu-select li{
        margin-bottom: 0;
    }
    .ivu-article .ivu-select ul{
        padding-left: 0 !important;
        list-style-type: none;
    }
</style>
<template>
    <i-article>
        <article>
            <h1>Select</h1>
            <Anchor title="Brief Introduction" h2></Anchor>
            <p>A dropdown select , alternative to the native select component.</p>
            <p>Select supports single, multiple, search and keyboard.</p>
            <blockquote>Notice: If not template/render mode, you need to use<code>i-select</code>, <code>i-option</code>.</blockquote>
            <Anchor title="Examples" h2></Anchor>
            <Demo title="Basic Usage">
                <div slot="demo">
                    <Select v-model="model1" style="width:200px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                    <span class="demo-data">{{ model1 }}</span>
                </div>
                <div slot="desc">
                    <p>Basic usage. You can use v-model to enable two-way data bindings.</p>
                    <p>In the single select, value only accept String and Number type.In the multiple select, value only accept Array type.Select Component will return selected data from <code>Option</code>'s <code>value</code> automately.</p>
                    <p>You can add style css for <code>Select</code>，such as width.</p>
                    <p>After expanding select, you can select up and down with the <code>Up</code>and<code>Down</code> key, Press<code>Enter</code>to confirm，press<code>Esc</code>to collapse.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.base }}</i-code>
            </Demo>
            <Demo title="Size">
                <div slot="demo">
                    <Select v-model="model2" size="small" style="width:100px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                    <Select v-model="model3" style="width:100px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                    <Select v-model="model4" size="large" style="width:100px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                </div>
                <div slot="desc">
                    <p>There are three size of select: large, medium(default), small.</p>
                    <p>Set<code>size</code>property to <code>large</code>or<code>small</code>.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.size }}</i-code>
            </Demo>
            <Demo title="Disable">
                <div slot="demo">
                    <Select v-model="model5" disabled style="width:200px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                    <Select v-model="model6" style="width:200px">
                        <Option value="beijing">北京市</Option>
                        <Option value="shanghai" disabled>上海市</Option>
                        <Option value="shenzhen">深圳市</Option>
                    </Select>
                </div>
                <div slot="desc">
                    <p>Add <code>disabled</code> property to <code>Select</code> can disable the select.</p>
                    <p>Add <code>disabled</code> property to <code>Option</code> can disable that option.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.disabled }}</i-code>
            </Demo>
            <Demo title="clearable">
                <div slot="demo">
                    <Select v-model="model8" clearable style="width:200px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                    <span class="demo-data">{{ model8 }}</span>
                </div>
                <div slot="desc">
                    <p>Add <code>clearable</code> property can clear the selected option，which only used for single select.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.clearable }}</i-code>
            </Demo>
            <Demo title="Group">
                <div slot="demo">
                    <Select v-model="model7" style="width:200px">
                        <Option-group label="热门城市">
                            <Option v-for="item in cityList1" :value="item.value" :key="item">{{ item.label }}</Option>
                        </Option-group>
                        <Option-group label="其它城市">
                            <Option v-for="item in cityList2" :value="item.value" :key="item">{{ item.label }}</Option>
                        </Option-group>
                    </Select>
                    <span class="demo-data">{{ model7 }}</span>
                </div>
                <div slot="desc">
                    <p>Using <code>Option-group</code> component can group the options.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.group }}</i-code>
            </Demo>
            <Demo title="Customize Template">
                <div slot="demo">
                    <Select v-model="model9" style="width:200px">
                        <Option value="beijing" label="北京市">
                            <span>北京</span>
                            <span style="float:right;color:#ccc">Beiing</span>
                        </Option>
                        <Option value="shanghai" label="上海市">
                            <span>上海</span>
                            <span style="float:right;color:#ccc">ShangHai</span>
                        </Option>
                        <Option value="shenzhen" label="深圳市">
                            <span>深圳</span>
                            <span style="float:right;color:#ccc">ShenZhen</span>
                        </Option>
                    </Select>
                    <span class="demo-data">{{ model9 }}</span>
                </div>
                <div slot="desc">
                    <p>Customize the option content. When using <code>label</code> property in <code>Option</code>, the option will show the label preferentially. Otherwise the selected content will be same with the customise content and that is not what we want.</p>
                    <p>The logic of showing the option content：show slot content firstly.If there is no slot, it will show the content of <code>label</code>. If there is no label property, it will show the <code>value</code></p>
                </div>
                <i-code lang="html" slot="code">{{ code.label }}</i-code>
            </Demo>
            <Demo title="Multiple">
                <div slot="demo">
                    <p class="demo-data">{{ model10 }}</p>
                    <Select v-model="model10" multiple style="width:260px">
                        <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                    </Select>
                </div>
                <div slot="desc">
                    <p>Add <code>multiple</code> property can support multiple select. In the multiple mode model accept an Array and return an Array.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.multiple }}</i-code>
            </Demo>
            <Demo title="Searchable">
                <div slot="demo">
                    <Row>
                        <Col span="12" style="padding-right:10px">
                            <Select v-model="model11" filterable>
                                <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                            </Select>
                        </Col>
                        <Col span="12">
                            <Select v-model="model12" filterable multiple>
                                <Option v-for="item in cityList" :value="item.value" :key="item">{{ item.label }}</Option>
                            </Select>
                        </Col>
                    </Row>
                </div>
                <div slot="desc">
                    <p>Add <code>filterable</code> property can set search mode.Single and Multiple Mode both support search. When using multiple mode to search, using <code>Delete</code> key can delete the last option.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.filterable }}</i-code>
            </Demo>
            <Demo title="Remote Search">
                <div slot="demo">
                    <Row>
                        <Col span="12" style="padding-right:10px">
                            <Select
                                v-model="model13"
                                filterable
                                remote
                                :remote-method="remoteMethod1"
                                :loading="loading1">
                                <Option v-for="option in options1" :value="option.value" :key="new Date()">{{option.label}}</Option>
                            </Select>
                        </Col>
                        <Col span="12">
                        <Select
                            v-model="model14"
                            multiple
                            filterable
                            remote
                            :remote-method="remoteMethod2"
                            :loading="loading2">
                            <Option v-for="option in options2" :value="option.value" :key="new Date()">{{option.label}}</Option>
                        </Select>
                        </Col>
                    </Row>
                </div>
                <div slot="desc">
                    <p>Remote search need set <code>filterable</code>, <code>remote</code>, <code>remote-method</code>, <code>loading</code> four props, which loading is to show searching status and remote-method is the methods of searching remotely.</p>
                    <p>Notice：Option need to set key，the example set the current time to the key。</p>
                    <p>The example is America state, try to input some.</p>
                </div>
                <i-code lang="html" slot="code">{{ code.remote }}</i-code>
            </Demo>
            <div class="api">
                <Anchor title="API" h2></Anchor>
                <Anchor title="Select props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>Property</th>
                            <th>Description</th>
                            <th>Type</th>
                            <th>Default</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <td>value</td>
                            <td>The value of the selected item. Use v-model to enable a two-way binding. It only accepts String or Number in single-choice mode. And it only accepts Array in mutli-choices mode.</td>
                            <td>String | Number | Array</td>
                            <td>empty</td>
                        </tr>
                        <tr>
                            <td>multiple</td>
                            <td>set select to support multiple</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>disabled</td>
                            <td>set select to disable</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>clearable</td>
                            <td>set select to clear option where used in single mode</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>filterable</td>
                            <td>set select to support filter</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>remote</td>
                            <td>set select to support remote data</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>remote-method</td>
                            <td>the mothod of getting remote data</td>
                            <td>Function</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td>loading</td>
                            <td>set select to remote search data loading state.</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>loading-text</td>
                            <td>the loading text tip for remote searching.</td>
                            <td>String</td>
                            <td>loading</td>
                        </tr>
                        <tr>
                            <td>label</td>
                            <td>use for init in the remote mode. It should set 手动 because  it can't get the option label by the value.</td>
                            <td>String | Number | Array</td>
                            <td>empty</td>
                        </tr>
                        <tr>
                            <td>size</td>
                            <td>The size of select. The value could be <code>large</code>和<code>small</code>or none.</td>
                            <td>String</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td>placeholder</td>
                            <td>the text for placeholder</td>
                            <td>String</td>
                            <td>select</td>
                        </tr>
                        <tr>
                            <td>not-found-text</td>
                            <td>The context to show when the select is null.</td>
                            <td>String</td>
                            <td>Nothing matched.</td>
                        </tr>
                        <tr>
                            <td>label-in-value</td>
                            <td>set select return value what include label and value, which default return value.</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>placement</td>
                            <td>The direction of pop-ups. The value could be <code>bottom</code> or <code>top</code></td>
                            <td>String</td>
                            <td>bottom</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Select events" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>Event Name</th>
                            <th>Description</th>
                            <th>Return Value</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <td>on-change</td>
                            <td>Emitted when selected <code>Option</code>change.It will return value. See the label-in-value property if need return label</td>
                            <td>The current selected item.</td>
                        </tr>
                        <tr>
                            <td>on-query-change</td>
                            <td>Emitted when query word is changed.</td>
                            <td>query</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Select methods" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>Method Name</th>
                            <th>Description</th>
                            <th>Arguments</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>setQuery</td>
                            <td>It will set search key and clear when the key is null, only when <code>filterable="true"</code>.</td>
                            <td>query</td>
                        </tr>
                        <tr>
                            <td>clearSingleSelect</td>
                            <td>It will clear single select when <code>clearable="true"</code></td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Option props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>Property</th>
                            <th>Description</th>
                            <th>Type</th>
                            <th>Default</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <td>value</td>
                            <td>the option value, filter by the property, required</td>
                            <td>String | Number</td>
                            <td>empty</td>
                        </tr>
                        <tr>
                            <td>label</td>
                            <td>The content of the option, read slot default. If not have slot, it will show the label. If not have label, show the value.Mostly just write slot, but for cumtomized option, this is useful.</td>
                            <td>String</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td>disabled</td>
                            <td>set to disable the option.</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="OptionGroup props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>Property</th>
                            <th>Description</th>
                            <th>Type</th>
                            <th>Default</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <td>label</td>
                            <td>Group Name</td>
                            <td>String</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </article>
    </i-article>
</template>
<script>
    import iArticle from '../../components/article.vue';
    import iCode from 'iCode';
    import Demo from '../../components/demo.vue';
    import Code from '../../code/select';
    import Anchor from '../../components/anchor.vue';

    export default {
        components: {
            iArticle,
            iCode,
            Demo,
            Anchor
        },
        data () {
            return {
                code: Code,
                cityList: [
                    {
                        value: 'beijing',
                        label: '北京市'
                    },
                    {
                        value: 'shanghai',
                        label: '上海市'
                    },
                    {
                        value: 'shenzhen',
                        label: '深圳市'
                    },
                    {
                        value: 'hangzhou',
                        label: '杭州市'
                    },
                    {
                        value: 'nanjing',
                        label: '南京市'
                    },
                    {
                        value: 'chongqing',
                        label: '重庆市'
                    }
                ],
                cityList1: [
                    {
                        value: 'beijing',
                        label: '北京市'
                    },
                    {
                        value: 'shanghai',
                        label: '上海市'
                    },
                    {
                        value: 'shenzhen',
                        label: '深圳市'
                    }
                ],
                cityList2: [
                    {
                        value: 'hangzhou',
                        label: '杭州市'
                    },
                    {
                        value: 'nanjing',
                        label: '南京市'
                    },
                    {
                        value: 'chongqing',
                        label: '重庆市'
                    }
                ],
                model1: '',
                model2: '',
                model3: '',
                model4: '',
                model5: '',
                model6: '',
                model7: '',
                model8: '',
                model9: '',
                model10: [],
                model11: '',
                model12: [],
                list: ['Alabama', 'Alaska', 'Arizona', 'Arkansas', 'California', 'Colorado', 'Connecticut', 'Delaware', 'Florida', 'Georgia', 'Hawaii', 'Idaho', 'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky', 'Louisiana', 'Maine', 'Maryland', 'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi', 'Missouri', 'Montana', 'Nebraska', 'Nevada', 'New hampshire', 'New jersey', 'New mexico', 'New york', 'North carolina', 'North dakota', 'Ohio', 'Oklahoma', 'Oregon', 'Pennsylvania', 'Rhode island', 'South carolina', 'South dakota', 'Tennessee', 'Texas', 'Utah', 'Vermont', 'Virginia', 'Washington', 'West virginia', 'Wisconsin', 'Wyoming'],
                model13: '',
                loading1: false,
                options1: [],
                model14: [],
                loading2: false,
                options2: []
            }
        },
        methods: {
            remoteMethod1 (query) {
                if (query !== '') {
                    this.loading1 = true;
                    setTimeout(() => {
                        this.loading1 = false;
                        const list = this.list.map(item => {
                            return {
                                value: item,
                                label: item
                            };
                        });
                        this.options1 = list.filter(item => item.label.toLowerCase().indexOf(query.toLowerCase()) > -1);
                    }, 200);
                } else {
                    this.options1 = [];
                }
            },
            remoteMethod2 (query) {
                if (query !== '') {
                    this.loading2 = true;
                    setTimeout(() => {
                        this.loading2 = false;
                        const list = this.list.map(item => {
                            return {
                                value: item,
                                label: item
                            };
                        });
                        this.options2 = list.filter(item => item.label.toLowerCase().indexOf(query.toLowerCase()) > -1);
                    }, 200);
                } else {
                    this.options2 = [];
                }
            }
        }
    }
</script>