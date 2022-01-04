<template>
    <div class="w-full">
        <div class="bg-gradient-to-b from-blue-800 to-blue-600 h-96"></div>
        <div class="max-w-5xl mx-auto px-6 sm:px-6 lg:px-8 mb-12">
            <div class="bg-white w-full shadow rounded p-8 sm:p-12 -mt-72">
                <p class="text-3xl font-bold leading-7 text-center">Contact me</p>
                <form action="" method="post" @submit="submit">
                    <div class="md:flex items-center mt-12">
                        <div class="w-full md:w-1/2 flex flex-col">
                            <label class="font-semibold leading-none">Nome</label>
                            <input v-model="name"  type="text" class="leading-none text-gray-900 p-3 focus:outline-none focus:border-blue-700 mt-4 bg-gray-100 border rounded border-gray-200" />
                            <span>{{nameError}}</span>
                        </div>
                        <div class="w-full md:w-1/2 flex flex-col md:ml-6 md:mt-0 mt-4">
                            <label class="font-semibold leading-none">Email</label>
                            <input v-model="email"  type="email"  class="leading-none text-gray-900 p-3 focus:outline-none focus:border-blue-700 mt-4 bg-gray-100 border rounded border-gray-200"/>
                            <span>{{emailError}}</span>
                        
                        </div>
                    </div>
                    <div class="md:flex items-center mt-8">
                        <div class="w-full flex flex-col" >
                            <label class="font-semibold leading-none">Soggetto</label>
                           
                           
                            <input  v-model ="soggetto"   type="text" class="leading-none text-gray-900 p-3 focus:outline-none focus:border-blue-700 mt-4 bg-gray-100 border rounded border-gray-200"/>
                        <span>{{soggettoError}}</span>
                        </div>
                        
                    </div>
                    <div>
                        <div class="w-full flex flex-col mt-8">
                            <label class="font-semibold leading-none">Messaggio</label>
                            <textarea type="text" class="h-40 text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-blue-700 mt-4 bg-gray-100 border rounded border-gray-200"></textarea>
                        </div>
                    </div>
                    <div class="flex items-center justify-center w-full">
                        <button type="submit"  class="mt-9 font-semibold leading-none text-white py-4 px-10 bg-blue-700 rounded hover:bg-blue-600 focus:ring-2 focus:ring-offset-2 focus:ring-blue-700 focus:outline-none">
                            Invio
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
import {useField , useForm} from 'vee-validate'
export default {
    setup() {
        const required = value => {
  const requiredMessage = 'il campo è richiesto'
  if (value === undefined || value === null) return requiredMessage
  if (!String(value).length) return requiredMessage

  return true
}

const validationSchema = {
  name: required,
  email: required,
  soggetto: required,
}

const { handleSubmit } = useForm({
  validationSchema
})

const submit = handleSubmit(values => {
  console.log('submit', values)
  alert('form inviato')
})


    const { value: email, errorMessage: emailError } = useField('email')
    const {value : name, errorMessage: nameError } = useField('name')
    const {value : soggetto, errorMessage: soggettoError } = useField('soggetto')

    return {
        submit,
        email,
        emailError,
        name,
        nameError,
        soggetto,
        soggettoError,
        
    }
}        
    }
</script>