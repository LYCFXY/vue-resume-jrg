<template>
    <div id="resumePreview">
        {{ resume }}
    </div>
</template>

<script type="text/javascript">
    export default {
        name: 'ResumePreview',
        data() {
            return {

            }
        },
        computed: {
            resume () {
                return this.$store.state.resume
            }
        }
    }
</script>

<style lang="scss">
    #resumePreview {
        display: flex;
        background:#ffffff;
        box-shadow:0 1px 3px 0 rgba(0,0,0,0.25);
        padding: 2em;
        color: #333;
        line-height: 1.2;
        overflow: auto;
        * {
            box-sizing: border-box;
            font-variant: normal;
            font-weight: normal;
        }
        ol {
            list-style: none;
        }
        section + section {
            margin-top: 2em;
        }
        p {
            /* 去除一行文本中的空格，但是保留一行的换行符，作用是防止用户在输入框输入空格而产生对用户不友好显示效果 */
            white-space: pre-line;
        }
        section {
            > h2:first-child  {
                background: #ddd;
                display: inline-block;
                padding: .2em;
            }
        }

        section[data-name="profile"] {
            > h1{
                margin: .1em 0;
                font-size: 4em;
            }
        }

        section[data-name="awards"],
        section[data-name="projects"],
        section[data-name="wordHistory"] {
            li + li { margin-top: 1em; }
            li {
                h3 {
                    border-bottom: 1px solid #999;
                    padding-bottom: .3em;
                    margin-bottom: .3em;
                    margin-botom: .3em;
                }
            }
        }

        section[data-name="educatiion"] {
            li {
                line-height: 1.5;
            }
        }
        section[data-name="contacts"] {
            td:first-child {
                padding-right: 1em;
            }
        }
    }
</style>