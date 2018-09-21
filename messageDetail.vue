  <Icon type=" icon iconfont fcshop-shangpin"></Icon>
        用户留言详情
    </p>
    <div>
      <Form ref="formValidate" :label-width="180">

        <Row>

          <Col span="12" push="6">
          <FormItem label="昵称：">
            <p class="expand">{{ row.User?row.User.nickName:'无' }} </p>
          </FormItem>
          </Col>
        </Row>

        <Row>
          <Col span="12" push="6">
          <FormItem label="留言：">
            <p class="expand">{{ row.content? row.content:"无"}} </p>
          </FormItem>
          </Col>
        </Row>
        <Row>
          <Col span="12" push="6">
          <FormItem label="手机号：">
            <p class="expand">{{row.User.phone?row.User.phone:'无'}}</p>
          </FormItem>
          </Col>
        </Row>

      </Form>
    </div>
  </Card>
</template>
<script>
export default {
  data () {
    return {
      row: {
        Good: null,
        price: null,
        state: null,
        Address: null,
        expressNo: null,
        Express: null,
        province: null,
        city: null,
        area: null,
        width: null,
        refund: null

      }
    }
  },
  created () {
    this.shopDetails()
  },

  methods: {
    async shopDetails () {
      let id = this.$route.query.id
      const data = await this.$http.get({
        url: '/order/' + id
      })
      this.row = data

      // this.row.title = data.Good.title
      // this.row.category = data.Good.GoodsCategory.title
      // this.row.price=data.price
      // this.row.state=data.state
      // row.Address=
    }
  }
}
</script>
<style scoped>

</style>
