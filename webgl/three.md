    1. three.js是右手坐标系,如下图,原点在屏幕的中心

    // 正方体质心是原点
    //     y
    //     |
    //     v6--------v7
    //    /|        /|
    //   v3--------v0|
    //   | |       | |
    //   | v5------|-v4--x
    //   |/        |/
    //   v2-------v1
    //  /
    // z

    2. three.js绘制一个几何体,首先通过创建一个Geometry类,在Geometry类上设置顶点vertices,再根据顶点vertices的索引创建一个个三角面,由这些三角面构成了空心几何体

    3. obj文件定义了一个模型的几何形状和组成模块,里面有各个组成模块的顶点坐标和三角面等几何信息,通过模块的名字和mtl文件对应起来,mtl是定义了模型各个组成模块的材质(通过各种光照效果参数实现),还可以使用贴图
