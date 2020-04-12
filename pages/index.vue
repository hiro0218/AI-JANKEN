<template>
  <div class="container">
    <h1>AI JANKEN</h1>
    <p>
      最新のウェブ技術を使って作成された「絶対に負けない『じゃんけん』AI」です。
    </p>

    <section class="ai">
      <div :class="ai_select_class"></div>
    </section>

    <section class="user">
      <p>選択してください</p>
      <ul class="junken-list">
        <li class="junken-list__item--gu">
          <button
            type="button"
            class="junken-list__button"
            @click="selectedJanken('gu')"
          >
            ぐー
          </button>
        </li>
        <li class="junken-list__item--choki">
          <button
            type="button"
            class="junken-list__button"
            @click="selectedJanken('choki')"
          >
            ちょき
          </button>
        </li>
        <li class="junken-list__item--pa">
          <button
            type="button"
            class="junken-list__button"
            @click="selectedJanken('pa')"
          >
            ぱー
          </button>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Janken',
  data: () => {
    return {
      ai_select_class: 'ai__janken'
    }
  },
  computed: {
    WIN_LIST: () => {
      return {
        gu: 'pa',
        choki: 'gu',
        pa: 'choki'
      }
    },
    AI_WIN_CLASS: () => {
      return {
        gu: 'ai__janken--gu',
        choki: 'ai__janken--choki',
        pa: 'ai__janken--pa'
      }
    }
  },
  mounted() {},
  methods: {
    selectedJanken(select) {
      const win = this.WIN_LIST[select]
      this.ai_select_class = this.AI_WIN_CLASS[win]
    }
  }
}
</script>

<style lang="scss">
.container {
  min-height: 100vh;
  padding: 0 5vw;
  text-align: center;
}

.ai {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 20rem;
  background: url('~@/assets/ai.png') no-repeat center / contain;

  &__janken {
    $element: #{&};

    width: 10rem;
    height: 10rem;
    background: url('~@/assets/janken_gu.png') no-repeat 0 0 / contain;

    &--gu {
      @extend #{$element};

      background: url('~@/assets/janken_gu.png') no-repeat 0 0 / contain;
    }

    &--choki {
      @extend #{$element};

      background: url('~@/assets/janken_choki.png') no-repeat 0 0 / contain;
    }

    &--pa {
      @extend #{$element};

      background: url('~@/assets/janken_pa.png') no-repeat 0 0 / contain;
    }
  }
}

.junken-list {
  display: flex;
  justify-content: center;
  margin: 0;
  padding: 0;
  list-style: none;

  &__button {
    color: transparent;
  }

  &__item {
    $element: #{&};

    width: 5rem;
    height: 5rem;

    &:not(:last-child) {
      margin-right: 2rem;
    }

    &--gu {
      @extend #{$element};

      background: url('~@/assets/janken_gu.png') no-repeat 0 0 / contain;
    }

    &--choki {
      @extend #{$element};

      background: url('~@/assets/janken_choki.png') no-repeat 0 0 / contain;
    }

    &--pa {
      @extend #{$element};

      background: url('~@/assets/janken_pa.png') no-repeat 0 0 / contain;
    }
  }
}
</style>
