<template>
    <div class="table">
        <el-table
                :data="tableData"
                border
                :header-cell-style="{color: '#a86a13'}"
                style="width: 99.8%;font-size: 12px; margin-left: 1px">


            <el-table-column
                    align="center"
                    width="25">
                <template slot-scope="scope">
                    <i class="el-icon-circle-plus-outline" @click="add(scope)"></i>
                    <i class="el-icon-remove-outline" @click="del(scope)"></i>
                </template>


            </el-table-column>
            <el-table-column
                    align="center"
                    label="货物或应税劳务、服务名称"
                    width="210">

                <template slot-scope="scope">
                    <el-input v-model="scope.row.name"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="规格型号">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.type"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="单位">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.unit"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="数量">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.num"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="单价(含税)">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.price"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="金额(含税)">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.money"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="税率">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.shuilv"></el-input>
                </template>
            </el-table-column>
            <el-table-column
                    align="center"
                    label="税额">
                <template slot-scope="scope">
                    <el-input v-model="scope.row.shuie"></el-input>
                </template>
            </el-table-column>
        </el-table>
    </div>
</template>

<script>
    export default {
        name: "Table",
        data () {
            return {
                tableData: [
                    {
                        id: this.randomId,
                        name: '123',
                        type: '12',
                        unit: '12',
                        num: '12',
                        price: '12',
                        money: '12',
                        shuilv: '12',
                        shuie: '12'
                    }
                ]
            }
        },
        methods: {
            add(scope) {
                let data = {
                    id: '',
                    name: '',
                    type: '',
                    unit: '',
                    num: '',
                    price: '',
                    money: '',
                    shuilv: '',
                    shuie: ''
                }
                data.id = this.randomId();
                let index = this.tableData.indexOf(scope.row);
                this.tableData.splice(index + 1, 0, data);

            },
            del(scope) {
                if (this.tableData.length > 1 ) {
                    this.tableData = this.tableData.filter( item => item.id !== scope.row.id )
                }
            },
            randomId() {
                let Num = "";
                for (let i = 0; i < 6; i++) {
                    Num += Math.floor(Math.random() * 10);
                }
                return Num;
            }
        },


        mounted() {
            this.tableData[0].id = this.randomId();
        }
    }
</script>

<style>
    .el-table th, .el-table td {
        padding: 0!important;
    }
    .el-input__inner {
        border: 0!important;
        height: 22px!important;
        font-size: 12px!important;
    }
    .el-icon-circle-plus-outline,
    .el-icon-remove-outline {
        position: absolute;
        opacity: .35;
    }
    .el-icon-circle-plus-outline {
        top: 0;
        left: 50%;
        transform: translateX(-50%);

    }
    .el-icon-remove-outline {
        left: 50%;
        transform: translateX(-50%);
        bottom: 0;
    }
</style>