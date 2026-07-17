<template>
  // <q-form ref="myFormRef">

setup () {
  const myFormRef = useTemplateRef('myFormRef')

  function validate () {
    myFormRef.value.validate().then(success => {
      if (success) {
        // yay, models are correct
      }
      else {
        // oh no, user has filled in
        // at least one invalid value
      }
    })
  }

  // to reset validations:
  function reset () {
    myFormRef.value.resetValidation()
  }

  return {
    // ...
  }
}
</template>

<script setup>
//
</script>
