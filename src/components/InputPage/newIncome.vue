<template>
  <div>
    <b-container>
      <div class=" row  pt-3  pb-3  justify-content-md-center">


        <b-col class="col-md-6  " style="background-color: white; ">
          <div class="pb-3 titleCustomize">
            <font-awesome-icon icon="fa-sharp fa-solid fa-coins"/>
            新增工單
          </div>

          <b-tabs content-class="mt-3" fill>
            <b-tab title="第一頁" active>

              <b-form class="mt-3 mb-3" @submit="onSubmit" @reset="onReset" v-if="show">
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="姓名"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="firstPage.name"
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
                          v-model="firstPage.tele"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group id="input-group-2" label="日期" label-for="input-2">
                      <b-form-datepicker id="example-datepicker" v-model="firstPage.date"
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
                          v-model="firstPage.carModel"
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
                          v-model="firstPage.licensePlate"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="是否改裝"
                        label-for="input-1"
                    >

                      <b-form-radio-group class="mt-3 ml-3">
                        <b-form-radio v-model="firstPage.isCarModified" value="true" name="radio-size">是</b-form-radio>
                        <b-form-radio v-model="firstPage.isCarModified" value="false" name="radio-size">否</b-form-radio>
                      </b-form-radio-group>


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
              <b-form class="mt-3 mb-3" @submit="onSubmit" @reset="onReset" v-if="show">

                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="維修項目"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['1']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="總金額"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['2']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="下次保養公里數"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['3']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="預計保養公里數"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['4']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="機油品項"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['5']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="齒輪油"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['6']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="機油濾心"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['7']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="空氣濾心"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['8']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="傳動濾網"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['9']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="火星塞"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['10']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="煞車油"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['11']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="冷卻水"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['12']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="電瓶檢查狀態"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['13']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="機油精"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['14']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="汽油精"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['15']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="輪胎"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="secondPage['16']"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>


                <b-button type="submit" pill variant="outline-secondary">Submit</b-button>
                <b-button type="reset" pill variant="outline-danger">Reset</b-button>
              </b-form>
            </b-tab>

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
    const firstPage = reactive({
      name: null,
      tele: null,
      date: null,
      carModel: null,
      licensePlate: null,
      isCarModified: null,
    })
    const secondPage = reactive({
      '1': null,
      '2': null,
      '3': null,
      '4': null,
      '5': null,
      '6': null,
      '7': null,
      '8': null,
      '9': null,
      '10': null,
      '11': null,
      '12': null,
      '13': null,
      '14': null,
      '15': null,
      '16': null,
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
      category, firstPage, secondPage, show, onReset, onSubmit
    }

  }
}
</script>

<style scoped>
.titleCustomize{
  color: white ;
  background-color: rgba(33, 81, 128, 0.97);
  border-radius:60px;
  display: flex;
  /* 水平置中 */
  justify-content: center;
  /* 垂直置中 */
  align-content: center;
  flex-wrap: wrap;
}
</style>