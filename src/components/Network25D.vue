<template>
    <div id="network25d">
        <div id="div_2_2_2_1"></div>
    </div>
</template>
<script>
import * as THREE from 'three';
import { OrbitControls } from 'three/addons/controls/OrbitControls.js';
import { Line2 } from 'three/examples/jsm/lines/Line2'
import { LineGeometry } from 'three/examples/jsm/lines/LineGeometry'
import { LineMaterial } from 'three/examples/jsm/lines/LineMaterial'

export default {
    data() {
        return {

        }
    },
    mounted() {
        this.draw_my_25dnetwork();
    },
    computed: {

    },
    methods: {
        draw_my_25dnetwork() {
            let scene = new THREE.Scene();
            // 创建相机（透视相机）
            let camera = new THREE.PerspectiveCamera(
                45,
                window.innerWidth / window.innerHeight,
                1, 1000);

            // 在场景中添加相机
            scene.add(camera);
            // 设置相机的位置
            camera.position.set(50, 2, 30);
            // 设置相机镜头中心点
            camera.lookAt(scene.position);

            //创建光源
            // let light = new THREE.AmbientLight(0x404040);
            // scene.add(light);
            // var light = new THREE.PointLight(0xffffff);
            let light = new THREE.DirectionalLight(0xffffff, 1);
            light.position.set(400, 400, 400); //光源位置

            let light2 = new THREE.AmbientLight(0xffffff, 0.5);
            scene.add(light);
            scene.add(light2);

            // 获取展示的div，然后获取高宽
            let my_div = document.getElementById("div_2_2_2_1");
            let my_width = my_div.clientWidth;
            let my_height = my_div.clientHeight;

            // 创建渲染器
            let renderer = new THREE.WebGLRenderer();
            // 设置背景颜色
            renderer.setClearColor(0xffffff);
            // 渲染尺寸
            renderer.setSize(my_width, my_height);
            // 将渲染器表示为一个元素加入到div_3_1中
            my_div.appendChild(renderer.domElement);

            //OrbitControls 这个用来增加旋转，缩放效果
            let controls = new OrbitControls(camera, renderer.domElement);

            //////////////////////////////////////////////////////////////////////////
            //创建平面网格1      以下的网格平面统一设成50x50的大小，分别在y=10,0,-10的层次上
            let groundGeometry1 = new THREE.PlaneGeometry(50, 50, 32);
            // console.log(typeof Math.PI);
            groundGeometry1.rotateX(Math.PI * 0.5);
            groundGeometry1.translate(0, 15, 0);
            let groundMaterial1 = new THREE.MeshLambertMaterial({
                color: 0xFF99CCFF,
                side: THREE.DoubleSide
            });
            // 在0.0 - 1.0的范围内的浮点数，表明材质的透明度。值0.0表示完全透明，1.0表示完全不透明。
            // 如果材质的transparent属性未设置为true，则材质将保持完全不透明，此值仅影响其颜色。 默认值为1.0。
            groundMaterial1.transparent = true;
            groundMaterial1.opacity = 0.2;
            // groundGeometry.rotateX(Math.Pi*0.5);
            let ground1 = new THREE.Mesh(groundGeometry1, groundMaterial1)
            // ground.rotateX(Math.Pi*0.5);
            // console.log()
            scene.add(ground1);

            ///////////////////////////////////////////////
            //创建平面网格2
            let groundGeometry2 = new THREE.PlaneGeometry(50, 50, 32);
            groundGeometry2.rotateX(Math.PI * 0.5);
            groundGeometry2.translate(0, 0, 0);
            let groundMaterial2 = new THREE.MeshLambertMaterial({
                color: 0xFF99CCFF,
                side: THREE.DoubleSide
            });
            groundMaterial2.transparent = true;
            groundMaterial2.opacity = 0.2;

            let ground2 = new THREE.Mesh(groundGeometry2, groundMaterial2)
            scene.add(ground2);

            /////////////////////////////////////////////////////////////////
            //创建平面网格3
            let groundGeometry3 = new THREE.PlaneGeometry(50, 50, 32);
            groundGeometry3.rotateX(Math.PI * 0.5);
            groundGeometry3.translate(0, -15, 0);
            let groundMaterial3 = new THREE.MeshLambertMaterial({
                color: 0xFF99CCFF,
                side: THREE.DoubleSide
            });
            groundMaterial3.transparent = true;
            groundMaterial3.opacity = 0.2;

            let ground3 = new THREE.Mesh(groundGeometry3, groundMaterial3)
            scene.add(ground3);

            /////////////////////////////////////////////////////////////////////////
            //创建测试线条，这个是只能满足普通的，不能设置线条宽度
            // let points = [];
            // let material_line = new THREE.LineBasicMaterial({
            //     color: 0xFF99CC33,
            //     // linewidth:10   //线条宽度暂时起不了作用
            // });
            // let source_vector3 = new THREE.Vector3(0,0,0);
            // let target_vector3 = new THREE.Vector3(15,10,10)
            // points.push(source_vector3);
            // points.push(target_vector3);
            // let geometry_line = new THREE.BufferGeometry().setFromPoints(points);
            // let line_test = new THREE.Line(geometry_line, material_line);
            // scene.add(line_test);
            //////////////////////////////////////////////////////////////////////////
            //测试3D样条曲线    CatmullRomCurve3
            // let curve_geometry = new THREE.BufferGeometry();
            //Vector3(x,y,z)

            ////////////////////////////////////////////////////////////////////////////////////////////////////////
            for (let ii = 0; ii < 10; ii++) {

                //随机出x,z位置
                let temx1 = Math.floor(Math.random() * 10); //获取0到25的整数
                let temz1 = Math.floor(Math.random() * 10);

                let temx2 = Math.floor(Math.random() * 10); //获取0到25的整数
                let temz2 = Math.floor(Math.random() * 10);
                let my_curve_object = this.create_curve(temx1, temz1, temx2, temz2);

                scene.add(my_curve_object);
                //添加球体
                let my_sphere_object1 = this.create_sphere(temx1, 15, temz1);
                let my_sphere_object2 = this.create_sphere(temx2, 0, temz2);
                scene.add(my_sphere_object1);
                scene.add(my_sphere_object2);

            }
            // let my_curve_object = create_curve();
            // scene.add(my_curve_object);
            ////////////////////////////////////////////////////////////////////////////////////////////////////////////
            //下面是循环刷新


            function update() {

                //这里测试一下，applyLocalForce是施加外力，参数1 代表力向量，参数2代表作用点
                // sphereBody.applyLocalForce(new CANNON.Vec3(10,0,0),sphereBody.position);

                // world.step(1 / 60);
                //three.js 的 render
                renderer.render(scene, camera);
            }
            var animate = function () {
                update();
                requestAnimationFrame(animate);
            };
            animate();
        },
        create_curve(x1, z1, x2, z2) {
            //下面是借助line2才能实现线条宽度的实现，参照网址  https://blog.csdn.net/u014291990/article/details/91521311?spm=1001.2101.3001.6650.4&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-4-91521311-blog-102942314.pc_relevant_3mothn_strategy_and_data_recovery&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-4-91521311-blog-102942314.pc_relevant_3mothn_strategy_and_data_recovery&utm_relevant_index=7
            //并且需要另外引入库文件


            //随机出x,z位置
            // let temx1 = Math.floor(Math.random() * 25); //获取0到25的整数
            // let temz1 = Math.floor(Math.random() * 25);

            // let temx2 = Math.floor(Math.random() * 25); //获取0到25的整数
            // let temz2 = Math.floor(Math.random() * 25);


            // let my_curve = new THREE.CatmullRomCurve3([
            //     new THREE.Vector3(x1, 10, z1),
            //     new THREE.Vector3(5, 5.5, 5),
            //     new THREE.Vector3(5, 4.5, 5),
            //     new THREE.Vector3(x2, 0, z2)
            // ]);
            let my_curve = new THREE.CubicBezierCurve3(
                new THREE.Vector3(x1, 15, z1),
                new THREE.Vector3(5, 9, 5),
                new THREE.Vector3(5, 5, 5),
                new THREE.Vector3(x2, 0, z2)
            );

            let tem_curve_points = my_curve.getPoints(50);
            // let my_curve_geometry = new THREE.BufferGeometry().setFromPoints( tem_curve_points );
            //这里需要转换格式
            let my_curve_points = []
            tem_curve_points.map(function (value, index) {
                my_curve_points.push(value.x);
                my_curve_points.push(value.y);
                my_curve_points.push(value.z);
            })
            let my_curve_geometry = new LineGeometry();
            my_curve_geometry.setPositions(my_curve_points);
            let material_line = new LineMaterial({
                color: 0xFFA4D1FF,
                linewidth: 5
            });
            let my_curve_object = new Line2(my_curve_geometry, material_line);
            // 把渲染窗口尺寸分辨率传值给材质LineMaterial的resolution属性
            // resolution属性值会在着色器代码中参与计算
            let my_div = document.getElementById("div_3_2");
            material_line.resolution.set(my_div.clientWidth, my_div.clientHeight);
            return my_curve_object;
        },
        create_sphere(my_x, my_y, my_z) {
            let sphereGeometry = new THREE.SphereGeometry(0.7, 32, 32);
            let sphereMaterial = new THREE.MeshStandardMaterial({
                color: 0xFF9FD8E2 // 0xFF1E90FF  0xFFFF0000
            });
            let sphere = new THREE.Mesh(sphereGeometry, sphereMaterial);
            sphere.position.set(my_x, my_y, my_z); //设置球的位置
            return sphere;
        }
    },
    components: {

    }
}
</script>
<style>
#network25d{
    width: 100%;
    height: 100%;
}
#div_2_2_2_1{
    height: 100%;
    width: 100%;
}
</style>