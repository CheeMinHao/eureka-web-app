<template>
  <div className="card">
    <h3>{{ subjectPrettier(feedback.subject) }}</h3>
    <small>{{datePrettier(feedback.created_at)}} • {{ feedback.user_name }}</small>
    <p>{{ feedback.message }}</p>
  </div>
</template>

<script>
export default {
  name: "FeedBackListTile",
  props: {
    feedback: {
      type: Object,
      required: true,
    },
  }, 
  methods:{
    datePrettier(date){
      return date.toDate().toDateString()
    },
    subjectPrettier(subject){          
      return subject[0].toUpperCase() + subject.substring(1).replace("_"," ")
    }
  }
};

</script>

<style lang='scss' scoped>
.card {
  display: flex;
  flex-direction: column;
  width: 100%;
  align-items: flex-start;
  padding-top: 15px;
  padding-bottom: 15px;  
  border-bottom: 1px solid rgba(0,0,0,0.1);
}
</style>