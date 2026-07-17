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
import { useQuasar } from 'quasar'
import { ref } from 'vue'

const $q = useQuasar()

const name = ref(null)
const age = ref(null)
const accept = ref(false)

function onSubmit() {
  if (accept.value !== true) {
    $q.notify({
      color: 'red-5',
      textColor: 'white',
      icon: 'warning',
      message: 'You need to accept the license and terms first'
    })
  } else {
    $q.notify({
      color: 'green-4',
      textColor: 'white',
      icon: 'cloud_done',
      message: 'Submitted'
    })
  }
}

function onReset() {
  name.value = null
  age.value = null
  accept.value = false
}
</script>
