<template>
  <div>
    <b-container>
      <div  class=" row  pt-3  pb-3  justify-content-md-center">


          <b-col class="col-md-6  " style="background-color: white; " >
            <font-awesome-icon icon="fa-sharp fa-solid fa-coins" />
            新增工單
            <b-tabs content-class="mt-3" fill>
              <b-tab title="第一頁" active>
<!--                1.日期-->
<!--                2.維修項目-->
<!--                3.總金額-->
<!--                4.下次保養公里數-->
<!--                5.預計保養公里數-->
<!--                6.機油品項-->
<!--                7.齒輪油-->
<!--                8.機油濾心-->
<!--                9.空氣濾心-->
<!--                10.傳動濾網-->
<!--                11.火星塞-->
<!--                12.煞車油-->
<!--                13.冷卻水-->
<!--                14.電瓶檢查狀態-->
<!--                15.機油精-->
<!--                16.汽油精-->
<!--                17.輪胎-->
<!--                18.改裝-->
                <b-form  class="mt-3 mb-3" @submit="onSubmit" @reset="onReset" v-if="show">
                  <b-row>
                    <div class="col-6">
                      <b-form-group
                          id="input-group-1"
                          label="姓名"
                          label-for="input-1"
                      >
                        <b-form-input
                            id="input-1"
                            v-model="form.amount"
                        ></b-form-input>
                      </b-form-group>
                    </div>
                    <div class="col-6">
                      <b-form-group
                          id="input-group-1"
                          label="電話"
                          label-for="input-1"
                      >
                        <b-form-input
                            id="input-1"
                            v-model="form.amount"
                        ></b-form-input>
                      </b-form-group>
                    </div>
                  </b-row>
                  <b-row>
                    <div class="col-6">
                      <b-form-group id="input-group-2" label="日期" label-for="input-2">
                        <b-form-datepicker id="example-datepicker" v-model="form.datepicker"
                                           class="mb-2"></b-form-datepicker>
                      </b-form-group>
                    </div>
                    <div class="col-6">
                      <b-form-group
                          id="input-group-1"
                          label="車種"
                          label-for="input-1"
                      >
                        <b-form-input
                            id="input-1"
                            v-model="form.amount"
                        ></b-form-input>
                      </b-form-group>
                    </div>
                  </b-row>
                  <b-row>
                    <div class="col-6">
                      <b-form-group
                          id="input-group-1"
                          label="車牌"
                          label-for="input-1"
                      >
                        <b-form-input
                            id="input-1"
                            v-model="form.amount"
                        ></b-form-input>
                      </b-form-group>
                    </div>
                    <div class="col-6">
                      <b-form-group
                          id="input-group-1"
                          label="是否改裝"
                          label-for="input-1"
                      >
                        <b-form-input
                            id="input-1"
                            v-model="form.amount"
                        ></b-form-input>
                      </b-form-group>
                    </div>
                  </b-row>


<!--                  <b-form-group v-if="false" id="input-group-2" label="類型" label-for="input-2">-->
<!--                    <b-form-input-->
<!--                        id="input-2"-->
<!--                        v-model="form.type"-->
<!--                        placeholder="Enter name"-->
<!--                        required-->
<!--                    ></b-form-input>-->
<!--                  </b-form-group>-->

<!--                  <b-form-group id="input-group-3" label="類型" label-for="input-3">-->
<!--                    <b-form-select-->
<!--                        id="input-3"-->
<!--                        v-model="form.category"-->
<!--                        :options="category"-->
<!--                        required-->
<!--                    ></b-form-select>-->
<!--                  </b-form-group>-->
<!--                  <b-form-group id="input-group-2" label="日期" label-for="input-2">-->
<!--                    <b-form-datepicker id="example-datepicker" v-model="form.datepicker" class="mb-2"></b-form-datepicker>-->
<!--                  </b-form-group>-->
<!--                  <b-form-group id="input-group-2" label="備註" label-for="input-2">-->
<!--                    <b-form-input-->
<!--                        id="input-2"-->
<!--                        v-model="form.remark"-->
<!--                        placeholder="備註"-->
<!--                        required-->
<!--                    ></b-form-input>-->
<!--                  </b-form-group>-->


                </b-form>

              </b-tab>
              <b-tab title="第二頁">
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="車牌"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="form.amount"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>

                <b-button type="submit" pill variant="outline-secondary">Submit</b-button>
                <b-button type="reset" pill variant="outline-danger">Reset</b-button>
              </b-tab>
              <b-tab title="Very, very long title"><p>I'm the tab with the very, very long title</p></b-tab>
              <b-tab title="Disabled" disabled><p>I'm a disabled tab!</p></b-tab>
            </b-tabs>
          </b-col>
        </div>


    </b-container>
  </div>

</template>

<script>

import {reactive, ref} from "@vue/composition-api/dist/vue-composition-api";

export default {
  name: "newIncome",
  setup() {
    const form = reactive({
      amount: '',
      type: '',
      category: null,
      remark: '',
      datepicker: ''
    })
    const show = ref(true);
    const category = ref([
      {text: 'Please select an option', value: null},
      {text: '衣服', value: null},
      {text: '伙食', value: null},
      {text: '日用品', value: null},
      {text: '交通', value: null},
      {text: '交際', value: null},
      {text: '其他', value: null},
    ]);


    const onSubmit = () => {

    }
    const onReset = () => {
    }

    return {
      category, form, show, onReset, onSubmit
    }

  }
}
</script>

<style scoped>

</style>