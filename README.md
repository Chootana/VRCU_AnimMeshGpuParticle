# VRCU_AnimMeshGpuParticle
### アニメーションや頂点メッシュに合わせて動くGPU Particle


AnimatorやSkinned Mesh Rendererを使用せず，
shader側でアニメーション再生することで低負荷・大量描画できます．

![anim_mesh_gpu_particle_main](https://user-images.githubusercontent.com/44863813/144735700-c170dcdf-be27-4133-9927-96afc5c1d26b.gif)

![anim_mesh_gpu_particle_packs](https://user-images.githubusercontent.com/44863813/144736641-03ef88ff-2838-4fdf-88d8-430149cad387.gif)


このプロジェクトはβ版であり，今後継続開発予定です!

shaderの中身の勉強に利用したり，サンプルのそのまま利用することをおすすめします．

# Features 
- アバター[P-V5](https://protoco.booth.pm/items/2987721)にのみ対応（今後対応予定）
    - 好きなアニメーションを使用したい場合は[P-V5](https://protoco.booth.pm/items/2987721)を合わせてご購入ください

- アニメーションによっては対応しない可能性あります（今後対応予定）．あらかじめご了承ください．


# How To Use 
- VRCSDK3-WORLDとUdonSharpをインポートした後，
AnimMeshGpuParticle.unitypackageをインポートしてください．
- Particle Sceneに設定済みのprefabがあるのでご参考ください.

### Ex.1 Packs
- [Vket2021ブース](https://vrchat.com/home/world/wrld_d8eb97ca-9635-42b9-9290-f69fd1ed7bb1)で使用したアニメーション詰め合わせ
- Assets/AnimMeshGpuParticle/Textures/MotionPacks/にあるMemory_pos p5 Pack.matのパラメータを操作することでアニメーションやパーティクルの動きを変更できます．

    ![image](https://user-images.githubusercontent.com/44863813/144735960-42b8092c-3c52-492d-b571-15fad3bdd244.png)

1. Animationの切り替え

    Start Frame, Frame Countの値を変更するとアニメーションが切り替わります．下の画像のXがStartFrame，YがFrame Countです．
     1. Cheering (1, 57)
     2. Cheering2 (58, 87)
     3. Salsa Dancing (145, 68)
     4. Sitting Clap (213, 125)
     5. Standing Thumbs Up (338, 125)
     6. Victory Idle (463, 50)
     7. HipHop Dancing (513, 134)
     8. Boxing (647, 52)
     9. Boxing2 (699, 66)
     10. Bboy HipHop (765, 66)
     11. Idle (831, 250)
     12. Agura (1081, 326)

    ![image](https://user-images.githubusercontent.com/44863813/144736017-053e0dee-3bad-400c-a273-bf618dd7ae50.png)

    

2. Gravityの変更

    GravityYを変更するとパーティクルに加わる重力方向が変更されます



### Ex.2 Dance
- ShaderFes2021で展示予定．


### 用意したアニメーションに変更したい
- まずは用意したアバターのメッシュ情報とアニメーション情報からAnimation Textureを作成する必要があります．詳しい変換方法は[Animation GPU Instancing](https://github.com/Chootana/VRCU_GpuAnimationInstancing)をご参考ください．

- 以下で簡単な説明をします
    1. [P-V5](https://protoco.booth.pm/items/2987721)を用意して，いつも通りAnimatorを追加して好きなAnimationをセットする
    2. [Animation GPU Instancing](https://github.com/Chootana/VRCU_GpuAnimationInstancing)の変換ツールを使用する．
    3. 2.で作成されたフォルダ内のTexturesフォルダにAnimTex_###.assetというテクスチャが生成されます(イメージ下図)
    
        ![image](https://user-images.githubusercontent.com/44863813/144736376-800296bb-6805-4043-a4fa-94c5489f4a90.png)

    4. Assets/AnimMeshGpuParticle/Textures/MotionPacks/にあるMemory_###.matのマテリアルのAnimation Textureを3.で作成したものに変更します．

    
        ![image](https://user-images.githubusercontent.com/44863813/144735960-42b8092c-3c52-492d-b571-15fad3bdd244.png)


# Requirement
- Unity: 2019.4.31
- VRCSDK3: 2021.09.30.16.18
- UdonSharp: 0.20.3

# Author 
chootana (ちゅーたな)

twitter: [@choo_zap](https://twitter.com/choo_zap)

# License 
 
Anim Mesh Gpu Particle is under [MIT license](https://en.wikipedia.org/wiki/MIT_License).
