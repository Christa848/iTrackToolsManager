<template>

 
  <b-row  align-v="center">
  
    <b-col cols="1"> 
        <h2> <b-badge>K</b-badge></h2>
    </b-col>
    <b-col cols="7" @click="showModal">
        <b-badge v-if="status === 'Unsolved'" variant= "light">{{status}}</b-badge>
        <b-badge v-else-if="status === 'Unassigned'" variant= "secondary">{{status}}</b-badge>
        <b-badge v-else-if="status === 'Open'" variant= "success">{{status}}</b-badge>
        <b-badge v-else-if="status === 'Overdue'" variant= "danger">{{status}}</b-badge>
        <b-badge v-else-if="status === 'Due today'" variant= "warning">{{status}}</b-badge>
        <b-badge v-else-if="status === 'Onhold'" variant= "primary">{{status}}</b-badge>
        <div>
        <h6  @click="showModal" id="my-nav-dropdown" style="color:black" v-b-popover.hover="{title:'Elvin Kakokmo', content:'My vehicle have been offline for a while'}" >{{massage}}</h6>
       <p>{{name}} .<small>Received On:{{date}}</small> .<small>Due in 2 days</small></p>


    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
      <div class="d-block text-center">
        
<div id="ticket">
    <b-col cols="">
        <b-row>
            <b-col cols="3" >
<b-icon icon="envelope"></b-icon>
            </b-col>

            <b-col>
                <h5>{{subject}} Car is offline</h5>
                </b-col>
        </b-row>

 <b-row>
            <b-col cols="3">
 <span class="badge badge-success">K</span>
            </b-col>

            <b-col cols="">
                 {{name}}   <i>via email </i>
                <p><i>14 days ago</i></p>
                </b-col>
        </b-row>

        <b-row>
            <b-col cols="3">
<b-icon icon="envelope"></b-icon>
            </b-col>

            <b-col>
               <p><i>Hie iTrack Zim</i></p>
            <p>{{massage}}  </p> 
           <p><i>Regards</i></p> {{name}}
                </b-col>
        </b-row>


    </b-col>
    </div>

     <div class="d-block text-center">
        <div>
  <b-form-textarea
    id="textarea-no-resize"
    placeholder=" Reply"
    rows="3"
    no-resize
     v-model="message"
  ></b-form-textarea>
 
</div>
<b-row id="butto">
  <b-col cols="2">
 <b-button variant="outline-success">Send</b-button>
 </b-col>
 <b-col></b-col>
 </b-row>
      </div>

      </div>
      
     
    </b-modal>
  </div>
    </b-col>
    <b-col>  <b-badge variant="success">New</b-badge>  </b-col>
    </b-row>
     
</template>
<script>
export default {
  props: ['status','name','massage','date','id'],
   methods: {
      showModal() {
        this.$refs['my-modal'].show()
      },
      hideModal() {
        this.$refs['my-modal'].hide()
      },
   
    }
}
</script>
<style>
.ticket-card{
  border: limegreen 1px solid;
  margin: 0.5rem;
  padding: 0.5rem;
  background-color: white;
  margin-right: 1rem;
  max-height: 150px;

}
#checkbox-1{
  margin-top: 8rem!important;

}
</style>