<script setup>
const supabase = useSupabaseClient();
const router = useRouter();

await supabase.auth.signOut();
router.push('/sign-in');
</script>

<template>
  <div />
</template>
