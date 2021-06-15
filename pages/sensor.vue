<template>
    <div>
        <!-- <nuxt-link :to="/">Topへ戻る</nuxt-link> -->
        <h1>sensorページだよ</h1>
        <h2>aX:{{ aX }}</h2>
        <h2>aY:{{ aY }}</h2>
        <h2>aZ:{{ aZ }}</h2>
        <template v-if="aX == 0">
            <h2>aXのあたい取れてないよ</h2>
        </template>
        {{ test }}
    </div>
</template>

<script>
export default{
    data:()=>({
        aX:0,
        aY:0,
        aZ:0,
        test:0
        }
    ),
    created(){
        // setInterval(() => {
        //     // 処理
        //     if (process.browser) {
        //         window.addEventListener("devicemotion", (event) => {
        //             var x1 = event.accelerationIncludingGravity.x;    // x軸の重力加速度（Android と iOSでは正負が逆）
        //             var y1 = event.accelerationIncludingGravity.y;    // y軸の重力加速度（Android と iOSでは正負が逆）
        //             var z1 = event.accelerationIncludingGravity.z;    // z軸の重力加速度（Android と iOSでは正負が逆）

        //             var xa = event.acceleration.x;
        //             var ya = event.acceleration.y;
        //             var za = event.acceleration.z;
        //             // this.aX = x1;
        //             // this.aY = y1;
        //             // this.aX = z1;
        //             this.aX = xa;
        //             this.aY = ya;
        //             this.aX = za;

        //             console.log(xa,ya,za)
        //             console.log(x1,y1,z1)
        //         },false);
        //     this.test += 1
        // }}, 1000)
    },
    mounted(){
         if (process.browser) {
            window.addEventListener("devicemotion", (event) => {
                var x1 = event.accelerationIncludingGravity.x;    // x軸の重力加速度（Android と iOSでは正負が逆）
                var y1 = event.accelerationIncludingGravity.y;    // y軸の重力加速度（Android と iOSでは正負が逆）
                var z1 = event.accelerationIncludingGravity.z;    // z軸の重力加速度（Android と iOSでは正負が逆）

                var xa = event.acceleration.x;
                var ya = event.acceleration.y;
                var za = event.acceleration.z;
                // this.aX = x1;
                // this.aY = y1;
                // this.aZ = z1;
                this.aX = xa;
                this.aY = ya;
                this.aZ = za;

                console.log(xa,ya,za)
                console.log(x1,y1,z1)
            },false);
         }
    },
    destroyed(){
        window.removeEventListener('devicemotion',(event)=>{
                var x1 = event.accelerationIncludingGravity.x;    // x軸の重力加速度（Android と iOSでは正負が逆）
                var y1 = event.accelerationIncludingGravity.y;    // y軸の重力加速度（Android と iOSでは正負が逆）
                var z1 = event.accelerationIncludingGravity.z;    // z軸の重力加速度（Android と iOSでは正負が逆）

                var xa = event.acceleration.x;
                var ya = event.acceleration.y;
                var za = event.acceleration.z;
                // this.aX = x1;
                // this.aY = y1;
                // this.aZ = z1;
                this.aX = xa;
                this.aY = ya;
                this.aZ = za;

                console.log(xa,ya,za)
                console.log(x1,y1,z1)
        },false)
    },
    updated(){
    },
    methods: {
        // getSensorData(){
        //     // ここに window とか document を使った処理
        //     if (process.browser) {
        //         window.addEventListener("devicemotion", (dat) => {
        //             var x1 = dat.accelerationIncludingGravity.x;    // x軸の重力加速度（Android と iOSでは正負が逆）
        //             var y1 = dat.accelerationIncludingGravity.y;    // y軸の重力加速度（Android と iOSでは正負が逆）
        //             var z1 = dat.accelerationIncludingGravity.z;    // z軸の重力加速度（Android と iOSでは正負が逆）
        //             var xa = dat.acceleration.x;
        //             var ya = dat.acceleration.y;
        //             var za = dat.acceleration.z;
        //             // this.aX = x1;
        //             // this.aY = y1;
        //             // this.aX = z1;
        //             // this.aX = xa;
        //             // this.aY = ya;
        //             // this.aX = za;

        //             console.log(xa,ya,za)
        //             console.log(x1,y1,z1)
        //         });
        //         window.addEventListener("deviceorientation", function(e){
        //             // alpha, beta, gammaの値を取得
        //             let alpha = e.alpha;
        //             let beta = e.beta;
        //             let gamma = e.gamma;
        //             this.aX = alpha;
        //             this.aY = beta;
        //             this.aX = gamma;

        //         }, false);
        //     }
        //     console.log(this.aX, this.aY, this.aZ);
        // }
    }
}

</script>
