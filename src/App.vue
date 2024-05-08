<script setup lang="ts">
import { ref } from 'vue';
import { PhBackspace } from '@phosphor-icons/vue';
import * as math from 'mathjs';

const arrayInput = ref<string[]>([])

const inputToArray = (value: string): void => {
  arrayInput.value.push(value)
}

const jumlahKan = (): void => {
  const arrayString: string = arrayInput.value.join('')
  const result: number = math.evaluate(arrayString)
  arrayInput.value = result.toString().split('')
}

const hapusAngka = (): void => {
  arrayInput.value.pop()
}

</script>

<template>
  <section class="mx-auto h-14 text-center mt-10 text-4xl flex items-center justify-center gap-0.5">
    {{ arrayInput.join('').replace('.', ',').replace('*', ' x ').replace('/ 100', ' % ') }}
  </section>
  <section class="grid grid-cols-4 gap-1 h-96 w-80 mx-auto mt-2">
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray('( ')">
      (
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray(' )')">
      )
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray(' / 100')">
      %
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray(' / ')">
      /
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('1')">
      1
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('2')">
      2
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('3')">
      3
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray('*')">
      X
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('4')">
      4
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('5')">
      5
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('6')">
      6
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray(' - ')">
      -
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('7')">
      7
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('8')">
      8
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('9')">
      9
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="inputToArray(' + ')">
      +
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('0')">
      0
    </button>
    <button class="bg-zinc-800 rounded text-3xl" @click.prevent="inputToArray('.')">
      ,
    </button>
    <button class="bg-zinc-800 rounded text-3xl flex justify-center items-center" @click.prevent="hapusAngka()">
      <ph-backspace :size="32" />
    </button>
    <button class="bg-sky-800 rounded text-3xl" @click.prevent="jumlahKan()">
      =
    </button>
  </section>
</template>