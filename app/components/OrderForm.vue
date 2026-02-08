<script setup lang="ts">
import { z } from 'zod';
import { useForm } from "react-hook-form"
import { zodResolver } from '@hookform/resolvers/zod';
import { defaultOrderValue } from '~/constants';

const formSchema = z.object({
    order: z.string('Invalid order'),
})

type FormSchemaValues = z.output<typeof formSchema>

const state = reactive<Partial<FormSchemaValues>>({
    order: undefined,
})


async function onSubmit(event: SubmitEvent) {
    event.preventDefault()
    console.log(event.target)
}

const {
    register,
    handleSubmit,
    formState: { errors, isValid },
} = useForm<FormSchemaValues>({
    resolver: zodResolver(formSchema),
    mode: "onChange",
    defaultValues: {
        order: defaultOrderValue
    }
})

</script>


<template>
    <form @submit="onSubmit" class="space-y-4">
        <fieldset label="Email" name="email">
            <label for="order">
                Orden
            </label>
            <Input v-bind="{ ...register('order' as keyof FormSchemaValues) }" v-model="state.order" id="order" />
        </fieldset>
        <button type="submit">
            Enviar
        </button>
    </form>
</template>