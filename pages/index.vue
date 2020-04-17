<template>
  <v-layout>
    <v-container fluid>
      <v-card flat>
        <v-subheader>Media volume</v-subheader>
        <v-card-text>
          <v-slider
            v-model="volume"
            prepend-icon="mdi-volume-high"
            max="1"
            min="0"
            step="0.01"
          />
        </v-card-text>
      </v-card>
      <v-card flat>
        <v-list rounded>
          <v-list-item-group v-model="item" color="primary">
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
              @click="playSound(item.sound)"
            >
              <v-list-item-icon>
                <v-icon v-text="item.icon" />
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title v-text="item.text" />
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-card>
    </v-container>
  </v-layout>
</template>

<script>
export default {
  data: () => ({
    volume: 0.5,
    items: [
      { text: 'Aye aye', icon: 'mdi-album', sound: 'aye-aye.ogg' },
      { text: 'Aye aye, squeel', icon: 'mdi-album', sound: 'aye-aye-squeel.ogg' },
      { text: 'Bleh / No', icon: 'mdi-album', sound: 'bleh.ogg' },
      { text: 'Curious', icon: 'mdi-album', sound: 'curious.ogg' },
      { text: 'Distracted humming', icon: 'mdi-album', sound: 'distracted-humming.ogg' },
      { text: 'Here', icon: 'mdi-album', sound: 'here.ogg' },
      { text: 'Hey, hey! Look at this', icon: 'mdi-album', sound: 'hey-hey-look-at-this.ogg' },
      { text: 'I\'m thinking', icon: 'mdi-album', sound: 'im-thinking.ogg' },
      { text: 'Oh my!', icon: 'mdi-album', sound: 'oh-my.ogg' },
      { text: 'Oh shit.', icon: 'mdi-album', sound: 'oh-shit.ogg' },
      { text: 'Oh wow!', icon: 'mdi-album', sound: 'oh-wow.ogg' },
      { text: 'OVERLOAD', icon: 'mdi-album', sound: 'overload.ogg' },
      { text: 'Processing data', icon: 'mdi-album', sound: 'processing-data.ogg' },
      { text: 'SCREAM', icon: 'mdi-album', sound: 'scream.ogg' },
      { text: 'Squeel', icon: 'mdi-album', sound: 'squeel.ogg' },
      { text: 'Thinking', icon: 'mdi-album', sound: 'thinking.ogg' },
      { text: 'What do you mean', icon: 'mdi-album', sound: 'what-do-you-mean.ogg' },
      { text: 'Whatever', icon: 'mdi-album', sound: 'whatever.ogg' },
      { text: 'What is going on?', icon: 'mdi-album', sound: 'what-is-going-on.ogg' },
      { text: 'Yes', icon: 'mdi-album', sound: 'yes.ogg' },
    ],
  }),
  methods: {
    playSound (snd) {
      const audio = new Audio('/r2/sounds/' + snd)
      audio.volume = this.volume
      audio.play()
    }
  }
}
</script>
