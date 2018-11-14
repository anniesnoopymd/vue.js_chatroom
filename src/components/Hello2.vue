<template>
  <div class="hello container">
    <div class="input-group mb-3">
      <input type="text" class="form-control" v-model="message" placeholder="Recipient's username" aria-label="Recipient's username" aria-describedby="button-addon2">
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" @click="submitMessage()" type="button" id="button-addon2">Button</button>
      </div>
    </div>
      <div class="media my-3" v-for="item in messages">
        <img v-if="item.username != username " class="align-self-start mr-3" src="http://lorempixel.com/100/100/sports/" alt="Generic placeholder image">
        <div class="media-body">
            <h5 class="mt-0">{{item.username}}</h5>
            <p>{{item.message}}</p>
        </div>
        <img v-if="item.username == username " class="ml-3" src="http://lorempixel.com/100/100/sports/" alt="Generic placeholder image">
      </div>
        <!-- <div class="media">
            <div class="media-body">
                <h5 class="mt-0 mb-1">Media object</h5>
                Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
            </div>
            <img class="ml-3" src="http://lorempixel.com/100/100/sports/" alt="Generic placeholder image">
        </div> -->
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '',
      username: 'Annie',
      message: '',
      messages: [
        {
          username: 'Annie',
          message: 'Hello'
        },
        {
          username: 'Tsai',
          message: 'HiHi'
        }
        
      ]
    }
  },
  methods: {
    submitMessage(){
      let vm = this
      vm.messages.unshift({
        username: vm.username,
        message: vm.message


      })
      vm.message = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
