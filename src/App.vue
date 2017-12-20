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

import Topbar from './components/Topbar'
import ResumeEditor from './components/ResumeEditor'
import ResumePreview from './components/ResumePreview'
import icons from './assets/icons'

import './assets/ui.scss'

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
  }
}
</script>

<style lang="scss" scoped>
    .page{
       height: 100vh;
       display: flex;
       flex-direction: column;
       background: #EAEBEC;
        >main{
          flex-grow: 1;
        }
        >main{
          border: 1px solid #f60;
          min-width: 1024px;
          max-width: 1440px;
          margin-top: 16px;
          margin-bottom: 16px;
          padding: 0 16px;
          display: flex;
          justify-content: space-between;
          width: 100%; /* 试试不加这句会怎样 */
          align-self: center;
        }
   }

   #resumeEditor{
     width: 35%;
     background: #777;
   }
   #resumePreview{
     width: 61.66667%;
     flex-grow: 1;
     background: #ffffff;
     margin-left: 16px;
   }

   svg.icon {
      height: 1em;
      width: 1em;
      fill: currentColor;
      vertival-align: -0.1em;
      font-size: 16px;
    }
</style>
