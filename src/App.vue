<template>
  <AppUserList>
    <template #userlist="{list, count}">
      {{ count }}
      <AppUserCardsList :list="list" >
        <template #secondrow="{item:person}">
          {{person.name.last}}
          <button @click="alert(person.name.last)">Display last name</button>
          </template>      
      </AppUserCardsList>
    </template>
  </AppUserList>
</template>

<script>
import AppUserList from "@/components/AppUserList";
import AppUserCardsList from "@/components/AppUserCardsList";
export default {
  components: {
    AppUserList,
    AppUserCardsList    
  },
  methods:{
    alert(prop){
      alert('Last name '+ prop)

    }
  }
};
</script>