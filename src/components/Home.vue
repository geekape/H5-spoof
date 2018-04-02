<template>
  <div class="container">
    <header>
        <video :src="movie" v-if="isMovie" autoplay="autoplay" controls="controls" v-on:click="ToggleShare()"></video>
    </header>
    <main v-show="isMovie">
        <img src="../assets/cd.png" />
    </main>
    <footer>
        <div class="cd_arce" v-on:click="Toggle()">
            <div class="circle"  v-show="!isMovie"></div>
        </div>
        <div class="footer-bottom"  v-show="!isMovie">
            <div class="finger"></div>
            <span>点击选择CD</span>
        </div>
    </footer>
    <div class="layer-container" v-show="layer" v-on:click="Toggle()">
        <ul>
            <li @click="seeMovie('http://downloadb.dewmobile.net/Activity/yurenjie/video/xiyouji.mp4')"><img src="../assets/video1.png" alt="">
                <p>が兄嫂に口す中ぐ出てき</p>
                <p>.avi</p>
            </li>
            <li @click="seeMovie('http://downloadb.dewmobile.net/Activity/yurenjie/video/quanyecha.mp4')"><img src="../assets/video2.png" alt="">
                <p>が兄嫂に口す中ぐ出てき</p>
                <p>.avi</p>
            </li>
            <li @click="seeMovie('http://downloadb.dewmobile.net/Activity/yurenjie/video/liangjian.mp4')"><img src="../assets/video3.png" alt="">
                <p>为保基友周全</p>
                <p>竟奉献新婚娇妻</p>
            </li>
            <li @click="seeMovie('http://downloadb.dewmobile.net/Activity/yurenjie/video/huluwa.mp4')"><img src="../assets/video4.png" alt="">
                <p>他们打了她的老公</p>
                <p>还强压了她</p>
            </li>
            <li @click="seeMovie('http://downloadb.dewmobile.net/Activity/yurenjie/video/huanzhugege.mp4')"><img src="../assets/video5.png" alt="">
                <p>疯丫头胡乱认爹</p>
                <p>险与亲哥。。。</p>
            </li>
        </ul>
    </div>
    <div class="share-containet" v-show="share" v-on:click="ToggleShare()">
        <div class="share-head">
            <p>哈哈哈！想歪了吧！</p>
            <p>快去调戏Ta们吧！</p>
        </div>
        <div class="share-btn">
            <div class="button active" v-on:click="ToggleShare2()">整蛊好友</div>
            <div class="button"><a href="http://www.zcbboke.com/liuyan.html">联系作者</a></div>
        </div>
    </div>
    <div class="external_share_container" v-show="share2" v-on:click="ToggleShare2()">
        <p>右上角分享</p>
        <div></div>
    </div>
  </div>
</template>


<script>
    export default {
        name: 'Home',
        data: function() {
            return {
                layer: false,
                isMovie: false,
                movie: '',
                share: false,
                share2: false,
            }
        },
        methods: {

            Toggle() {
                if (this.layer) {
                    this.layer = false;
                } else {
                    this.layer = true;
                    this.isMovie = false;
                }
            },
            seeMovie(attr) {
                this.movie = attr;
                this.isMovie = true;
            },
            ToggleShare() {
                if (this.share) {
                    this.share = false;

                } else {
                    this.share = true;
                    this.isMovie = false;
                }
            },
            ToggleShare2() {
                if (this.share2) {
                    this.share2 = false;

                } else {
                    this.share2 = true;
                }
            },


        }

    }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" src="../assets/style.less">

</style>