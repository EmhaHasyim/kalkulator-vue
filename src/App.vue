<script setup lang="ts">
import { ref } from 'vue';

const arrayInput = ref<Array<string>>([])

const inputToArray: Function = (value: string) => {
  arrayInput.value.push(value)
}

const jumlahKan: Function = () => {
  const arrayString: string = arrayInput.value.join('')
  const hasilPenjumlahan = eval(arrayString)
  arrayInput.value = []
  arrayInput.value.push(hasilPenjumlahan)
}

const hapusAngka: Function = () => {
  arrayInput.value = []
}

</script>

<template>
  <section class="mx-auto h-14 text-center mt-10 text-4xl flex items-center justify-center gap-0.5">
    {{ arrayInput.join('') }}
  </section>
  <section class="grid grid-cols-3 gap-1 h-96 w-80 mx-auto mt-2">
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('1')">
      1
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('2')">
      2
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('3')">
      3
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('4')">
      4
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('5')">
      5
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('6')">
      6
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('7')">
      7
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('8')">
      8
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('9')">
      9
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('0')">
      0
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('+')">
      +
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="inputToArray('-')">
      -
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="jumlahKan()">
      =
    </button>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="hapusAngka()">
      c
    </button>
  </section>
</template>