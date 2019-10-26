<template>
    <div id="table">
        <div class="w">

            <div class="body">
                <h2>深圳增值税普通发票</h2>
                <div class="date">开票日期: 2019年10月35日</div>
                <div class="head_foot">
                    <div class="head_l">
                        <h3>购<br/><br/>买<br/><br/>方</h3>
                    </div>
                    <div class="head_r">
                        <ul>
                            <li>
                                <div class="justify">名称<span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">纳税人识别号 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">地址电话 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">开户行及账号 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>



                <div class="body_table">
                    <Table></Table>
                </div>


                <div class="money">
                    <div class="top">
                        <div class="moneyLeft">合计</div>
                        <div class="moneyRight"></div>
                    </div>
                    <div class="bottom">
                        <div class="moneyLeft">价税合计( 大写 )</div>
                        <div class="moneyRight">
                            <div class="absRight"><span>( 小写 )</span></div>
                        </div>
                    </div>
                </div>
                <div class="head_foot foot">
                    <div class="head_l">
                        <h3>销<br/><br/>售<br/><br/>方</h3>
                    </div>
                    <div class="head_r">
                        <ul>
                            <li>
                                <div class="justify">名 称 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">纳税人识别号 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">地 址 电 话 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                            <li>
                                <div class="justify">开 户 行 及 账 号 <span></span></div>
                                <div class="ipn">
                                    <span>:</span><input type="text">
                                </div>
                            </li>
                        </ul>

                        <div class="remarks">
                            <div class="remarks_l">备注</div>
                            <div>12345</div>
                        </div>

                    </div>
                </div>
                <div class="pageFoots">
                    <div class="pageFoot">收款人：</div>
                    <div class="pageFoot">复核：</div>
                    <div class="pageFoot">开票人：</div>
                    <div class="pageFoot">销售方： ( 章 )</div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    import Table from './childComponents/Table'
    export default {
        name: "Invoice",
        components: {
            Table
        }
    }
</script>

<style scoped>

    .w {        /*版心*/
        width: 931px;
        /*min-height: 495px;*/
        margin: 10px auto;
        position: relative;
        color: #a86a13;
    }
    .w .body h2 {     /*标题*/
        width: 250px;
        text-align: center;
        top: -95px;
        left: 50%;
        transform: translateX(-50%);
        padding: 15px 5px;
        border-bottom: 2px solid #a86a13;
        position: absolute;
        font-weight: normal;
    }
    .w .body .date {      /*开票日期*/
        position: absolute;
        right: 60px;
        top: -30px;
        font-size: 12px;
    }
    .w h2::after {  /*标题下的两条线*/
        content: "";
        height: 2px;
        width: 100%;
        background-color: #a86a13;
        position: absolute;
        bottom: 2px;
        left: 0;
    }
    .w .body {      /*发票*/
        position: absolute;
        top: 130px;
        width: 99%;
        min-height: 492px;
        height: auto;
        display: flex;
        flex-direction: column;
        border: 2px solid #a86a13;
        border-bottom: 0;
    }




    .head_foot {     /*头部区域 和尾部区域*/
        flex: 3;
        border-bottom: 2px solid #a86a13;
        display: flex;
    }
    .head_foot .head_l {
        flex: 1;
        border-right: 2px solid #a86a13;
        position: relative;
    }
    .head_foot .head_l h3 {
        font-weight: normal;
        width: 100%;
        text-align: center;
        font-size: 12px;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
    }

    .head_foot .head_r {
        flex: 23;
        position: relative;
    }
    .head_foot .head_r li {
        margin-left: 5px;
        font-size: 12px;
        position: relative;
        height: 22px;
    }
    .head_foot .head_r li:first-child {
        margin-top: 8px;
    }
    .head_foot li .ipn {
        position: absolute;
        left: 115px;
        top: 0;
    }
    .head_foot li .ipn span {
        float: left;
        margin-right: 13px;
    }

    .head_foot .head_r li input {
        outline: 0;
        border: 0;
        width: 320px;
    }




    /*div.justify { text-align: justify; width:200px; font-size:15px; color:red; border:1px solid blue; height:18px;}*/
    div.justify > span { display: inline-block /* Opera */; padding-left: 100%; }   /*两端对齐*/

    .head_foot .head_r div.justify {
        display: inline-block;
        width: 115px;
        text-align: justify;
        box-sizing: border-box;

        /*letter-spacing: 2px;*/
    }
    .head_foot .head_r li:first-child div {
        /*letter-spacing: 10px;*/
    }
    .head_foot .head_r .colon {
        display: inline-block;
        text-align: left;
        width: 20px;
    }




    .body_table {
        min-height: 220px;
        border-bottom: 2px solid #a86a13;
    }




    /*合计金额*/
    .money {
        flex: 2;
        border-bottom: 2px solid #a86a13;
        display: flex;
        flex-direction: column;
    }
    .money .top,
    .money .bottom {
        flex: 1;
        display: flex;
    }
    .money .top {
        border-bottom: 2px solid #a86a13;
    }
    .moneyLeft {
        flex: 1;
        border-right: 2px solid #a86a13;
        font-size: 12px;
        text-align: center;
        line-height: 35px;
        letter-spacing: 2px;
    }
    .moneyRight {
        flex: 2.5;
        position: relative;
    }
    .absRight {
        width: 232px;
        position: absolute;
        right: 0;
        font-size: 12px;
        line-height: 35px;
    }



    .remarks {      /*备注*/
        position: absolute;
        right: 0;
        top: 0;
    }

    .remarks div {
        float: left;
    }

    /*尾部*/
    .pageFoot {
        width: 230px;
        float: left;
        padding: 14px;
        font-size: 12px;
        box-sizing: border-box;
        color: #a86a13;
    }
    .pageFoots {
        width: 930px;
        position: absolute;
        bottom: -40px;
    }
</style>
