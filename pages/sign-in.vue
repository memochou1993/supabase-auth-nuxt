<script setup>
definePageMeta({
  middleware: [
  'guest',
  ],
});

const supabase = useSupabaseClient();
const router = useRouter();

const state = reactive({
  email: '',
  password: '',
});

const signIn = async () => {
  const { error } = await supabase.auth.signInWithPassword({
    email: state.email,
    password: state.password,
  })
  if (error) alert(error);
  router.push('/');
};
</script>

<template>
  <form @submit.prevent="signIn">
    <input v-model="state.email" type="email" />
    <input v-model="state.password" type="password" />
    <button type="submit">Sign In</button>
    &nbsp;or
    <NuxtLink to="/sign-up">Sign Up</NuxtLink>
  </form>
</template>
