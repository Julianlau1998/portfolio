<template>
    <div class="is-topnav has-text-left p-3 pb-4 pt-4">
        <div class="columns is-mobile">
            <div class="column pl-5 is-pointer">
                <span @click="home">
                    JL
                </span>
            </div>
            <div class="column settingsWrapper">
                <div v-if="settings" class="settingsItems settings">
                    <span v-if="helpAvailable">
                        <span @click="openInfo" class="is-icon-container is-pointer mt-6 setting noselect">
                            <i
                                class="fas fa-info is-smallIcon pr-1"
                            />
                            Info
                        </span>
                    </span>
                </div>
                <i
                    class="fas fa-bars settings-icon is-pointer"
                    @click="settings=!settings"
                />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'TopNav',
    props: {
        helpAvailable: {
            required: false,
            default: true
        }
    },
    data () {
        return {
            settings: false,
            shareAvailable: false,
            playBillingSupported: false
        }
    },
    created () {
        if (navigator.share !== undefined) this.shareAvailable = true
    },
    methods: {
        share () {
            this.$emit('share')
        },
        help () {
            this.$router.push('/help')
        },
        openInfo () {
          this.settings = false
          this.$router.push('/info')
        },
        home () {
            if (this.$route.path === '/') return
            this.$router.push('/')
        }
    }
}
</script>
