<template>
    <div id="resumePreview">
        <section data-name="profile" v-show="resume.profile">
            <h1>
                {{ resume.profile.name }}
            </h1>
            <h2>{{ resume.profile.title }}</h2>
            <p>
                <samll>{{ resume.profile.city }}</samll>
                <samll>{{ resume.profile.birthday }}</samll>
            </p>
        </section>

        <section data-name="education" v-show="resume.workHistory">
            <h2>工作经历</h2>
            <ol>
                <li v-for=" item in resume.workHistory">
                    <h3>{{ item.company }}</h3>
                    <p v-show="item.content">{{ item.content }}</p>
                </li>
            </ol>
        </section>

        <section data-name="education" v-show="resume.education">
            <h2>毕业院校</h2>
            <ol>
                <li v-for="item in resume.education">
                    <h3>{{ item.school }}
                        <span v-show="item.content"> - {{ item.content }}</span>
                    </h3>
                </li>
            </ol>
        </section>
    </div>
</template>

<script type="text/javascript">
    export default {
        name: 'ResumePreview',
        computed: {
            resume () {
                return this.$store.state.resume
            }
        },
        created () {
            console.log(this.resume)
        }
    }
</script>

<style type="text/css">
    #resumePreview{
        background:#ffffff;
        box-shadow:0 1px 3px 0 rgba(0,0,0,0.25);
    }
</style>