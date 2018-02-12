<template>
    <my-page title="题目助手 - 选择题录入工具">
        <ui-row gutter>
            <ui-col width="100" tablet="100" desktop="70">
                <textarea class="input" v-model="text"></textarea>
                <ui-article>
                    <h2>题目材料类型</h2>
                    <p>一行一题</p>
                    <p>两行一题</p>
                </ui-article>
            </ui-col>
            <ui-col width="100" tablet="100" desktop="30">
                <ui-raised-button label="解析" primary @click="parse" />
                <br>
                <h2>解析结果</h2>
                <div v-if="result">
                    <ul>
                        <li v-for="question in result">
                            题目：{{ question.content }}
                            <br>
                        </li>
                    </ul>
                </div>
                <textarea class="input2" v-model="result"></textarea>
            </ui-col>
        </ui-row>
    </my-page>
</template>

<script>
    /* eslint-disable */
    export default {
        data () {
            return {
                text: `1、“变脸 ”是哪个剧种的绝活？（ C ）
A、京剧 B、豫剧 C、川剧
2、甲骨文是写在哪上面的？（ A ）
A、龟骨 B、石头 C、树木 D、贝壳
3、五岳中的中岳是（ B ）。
A、华山 B、嵩山 C、恒山
4、古时，指南针为什么不叫 “指北针 ”？（ B ）
A、面北为尊，面南为卑 B、面南为尊，面北为卑
5、张家界风景区位于我国的哪一个省份？（ B ）
A、湖北 B、湖南 C、山东
6、欧洲最大的半岛在（ B ）。
A、东欧 B、北欧
7、将断丝的白炽灯泡重新搭上后 ,灯光与灯丝未断前相比（ B ）。
A、要暗些 B、要亮些 C、一样亮
8、国际奥林匹克集邮联合会在哪一国家成立？（ B ）
A、瑞士 B、中国 C、美国 D、德国
9、小鸡是由鸡蛋的（ B ）。
A、蛋青发育来的 B、蛋黄发育来的 C、蛋青和蛋黄混合后发育而来
10、蟋蟀是靠什么发出鸣叫声的？（ C ）
A、口腔 B、头顶 C、翅膀 D、尾巴
11、喝白酒时，最好（ A ）。
A、加热喝 B、直接喝 C、和可乐一起喝
12、 IMF 国际组织的简称（ A ）。
A、国际货币基金组织 B、国际经济贸易组织 C、国际原子能组织
13、著名的哈雷彗星命名源于（ B ）。
A、地名 B、人名 C、公司名字
14、一般而言，将戒指戴在中指上表示（ C ）
A、以经结婚 B、已经订婚 C、只是恋爱中 D、可代表任何含义
15、中国第一部彩色故事片是（ V ）
A、《霍元甲》 B、《祝福》 C、《一双绣花鞋》 D、《黄丝带》
16、使用液化石油气应该（ A ）
A、先点火后给气 B、先给气后点火 C、先关火后关气
17、屈原是春秋时代哪国人？（ B ）
A、齐国 B、楚国 C、燕国 D、赵国
18、中国最早的叙事诗是（ A ）。
A、《孔雀东南飞》 B、《木兰辞》 C、《老残游记》
19、在九大行星中，被称为最冷的行星是哪一颗？（ C ）
A、木星 B、水星 C、冥王星 D、海王星
20、人脑中控制人平衡力的是（ B ）。
A、大脑 B、小脑 C、脑神经 D、下丘脑
21、世界上第一部成文宪法是（ A ）。
A、美国宪法 B、英国宪法 C、联合国宪法 D、法国宪章`,
                result: null,
                type: 2
            }
        },
        mounted() {
            this.parse()
        },
        methods: {
            parse() {
                let text = this.text
                let lines = text.split('\n')
                console.log(lines)
                for (let i = 0; i < lines.length; i++) {
                    let line = lines[i]
                    if (type === 2) {
                        if (i % 2 === 0) {

                        } else {
                            let content = line.split('、')[1]
                            console.log(content)
                        }
                    }

                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    .input {
        width: 800px;
        max-width: 100%;
        height: 500px;
    }
    .input2 {
        width: 300px;
        height: 500px;
    }
</style>
