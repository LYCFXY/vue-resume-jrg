 <template>
   <div class=page>
     <header>
       <Topbar/>
     </header>
     <main>
       <ResumeEditor/>
       <ResumePreview/>
     </main>
    </div>
</template>

<script>
import 'normalize.css/normalize.css'
import './assets/reset.css'
import './assets/ui.scss'

import Topbar from './components/Topbar'
import ResumeEditor from './components/ResumeEditor'
import ResumePreview from './components/ResumePreview'
import icons from './assets/icons'



import store from './store/index'

export default {
  name: 'app',
  data: function () {
    return {
      text: '你好'
    }
  },
  store,
  components: {Topbar, ResumeEditor, ResumePreview},
  created() {
    document.body.insertAdjacentHTML('afterbegin', icons)

    let state = localStorage.getItem('state');
    if(state) {
      state = JSON.parse(state)
    }
    this.$store.commit('initState', state)
  }
}
</script>

<style lang="scss" scoped>

</style>
