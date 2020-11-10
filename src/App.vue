<template>
<AppLayout>
  <template #header>Slot are awesome</template>
  <div class="page">
 <AppButton>Hello</AppButton>
    <select v-model="selected">
      <option 
        v-for="option in options" 
        :value="option.value" 
        :key="option.value">
        {{option.label}}
      </option>
    </select>


    <AppUserList>
      <template #loading>
        <AppSpinner></AppSpinner>
        </template>
      <template #userlist="{list}">
        <AppUserCardsList :list="list">
          <template #[selected]="{text}">
            <h2>{{text}}</h2>
          </template>
        </AppUserCardsList>
      </template>
    </AppUserList>    
  </div>
  </AppLayout>
</template>

<script>
import AppLayout from "@/components/AppLayout";
import AppSpinner from "@/components/AppSpinner";
import AppUserList from "@/components/AppUserList";
import AppButton from "@/components/AppButton";
import AppUserCardsList from "@/components/AppUserCardsList";
export default {
  components: {
    AppSpinner,
    AppLayout,
    AppButton,
    AppUserList,
    AppUserCardsList
  },
  data() {
    return {
      selected: 'first',
      options: [
        { value: 'first',  label: 'first name'},
        { value: 'last',  label: 'last name'},
        { value: 'full',  label: 'fullname'},
        { value: 'fullWithTitle',  label: 'fullname with title'},
      ]
    }
  }
};
</script>

<style>
.page {
  padding: 2rem;
}

.page > * + * {
  margin-top: 2rem;
}
</style>