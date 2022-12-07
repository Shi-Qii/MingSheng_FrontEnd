<template>
  <div>
    <b-container>
      <div class=" row  pt-3  pb-3  justify-content-md-center">
        <b-col class="col-md-6  " style="background-color: white; ">
          <div class="pb-3 titleCustomize">
            <font-awesome-icon icon="fa-sharp fa-solid fa-coins"/>
            快速查詢
          </div>
          <b-tabs content-class="mt-3" fill>

            <b-tab title="基本查詢" active>
              <b-form class="mt-3 mb-3" @submit="onSubmit" @reset="onReset" v-if="show">
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="選單"
                        label-for="input-1"
                    >
                      <b-form-select v-model="inputData.selected"
                                     :options="inputData.options"></b-form-select>

                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="輸入"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="firstPage.tele"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>


                <b-row class="mt-3" align-h="between">
                  <b-col cols="4"></b-col>
                  <b-col cols="4">
                    <div>
                      <b-button type="submit" pill variant="outline-secondary">Submit</b-button>
                      <b-button type="reset" pill variant="outline-danger">Reset</b-button>
                    </div>
                  </b-col>
                </b-row>
              </b-form>
            </b-tab>
            <b-tab title="進階查詢" >
              <b-form class="mt-3 mb-3" @submit="onSubmit" @reset="onReset" v-if="show">
                <b-row>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="待新增"
                        label-for="input-1"
                    >
                      <b-form-select v-model="inputData.selected"
                                     :options="inputData.options"></b-form-select>

                    </b-form-group>
                  </div>
                  <div class="col-6">
                    <b-form-group
                        id="input-group-1"
                        label="輸入"
                        label-for="input-1"
                    >
                      <b-form-input
                          id="input-1"
                          v-model="firstPage.tele"
                      ></b-form-input>
                    </b-form-group>
                  </div>
                </b-row>


                <b-row class="mt-3" align-h="between">
                  <b-col cols="4"></b-col>
                  <b-col cols="4">
                    <div>
                      <b-button type="submit" pill variant="outline-secondary">Submit</b-button>
                      <b-button type="reset" pill variant="outline-danger">Reset</b-button>
                    </div>
                  </b-col>
                </b-row>
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
  name: "newExpenditure",
  setup() {
    const form = reactive({
      amount: '',
      type: '',
      category: null,
      remark: '',
      datepicker: ''
    })
    const show = ref(true);
    const category = ref([{text: 'Please select an option', value: null},
      {text: '薪水', value: null},
      {text: '股票', value: null},
      {text: '紅利', value: null},
      {text: '發票', value: null},
      {text: '運彩', value: null},
      {text: '其他', value: null},]);
    const firstPage = reactive({
      name: null,
      tele: null,
      date: null,
      carModel: null,
      licensePlate: null,
      isCarModified: null,
    })
    const inputData = reactive({
      selected: null,
      options: [{text: 'Please select an option', value: null},
        {text: '姓名', value: null},
        {text: '車牌', value: null},
        {text: '聯絡方式', value: null},
      ],

    })

    const onSubmit = () => {

    }
    const onReset = () => {
    }

    return {
      category, form, show, onReset, onSubmit, firstPage, inputData
    }

  }
}
</script>

<style scoped>
.titleCustomize {
  color: white;
  background-color: rgba(33, 81, 128, 0.97);
  border-radius: 60px;
  display: flex;
  /* 水平置中 */
  justify-content: center;
  /* 垂直置中 */
  align-content: center;
  flex-wrap: wrap;
}
</style>