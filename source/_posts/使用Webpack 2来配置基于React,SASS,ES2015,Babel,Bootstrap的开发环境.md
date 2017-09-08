---

title: 使用Webpack 2来搭建基于React,SASS,ES2015,Babel,Bootstrap的开发框架

date: 2017-09-08 03:46:27

tags:
     - 转载
     - 翻译
     - webpack
---

> 原文链接：[使用Webpack 2来搭建基于React,SASS,ES2015,Babel,Bootstrap的开发框架](https://medium.com/@srinisoundar/setting-up-environment-for-react-sass-es2015-babel-bootstrap-with-webpack-2-d48181658b94)
>
> 作者：[srinivasan](https://medium.com/@srinisoundar)
>
> 译者：[Scar9k](scar9k.github.io)
>
> 转载请注明出处。
# 使用Webpack 2来配置基于React,SASS,ES2015,Babel,Bootstrap的开发环境

![1 -8pPP-F3plVmB2xlxET8uA.jpeg](https://i.loli.net/2017/09/08/59b18d25db745.jpeg)
>提示：如果想使用Webpack来搭建一个开发框架推荐参靠我之前发表的[**文章**](https://medium.com/@srinisoundar/setting-up-environment-for-react-sass-es2015-babel-with-webpack-2f77445129)
而本文我们将了解如何将其从**Webpack v1**移植至**Webpack v2**

<font size=6>**Webpack Config**</font>
<font size=5>**Webpack module.loaders 现在由 module.rules替代**</font>

Loaders 仍然可以有效地被使用，但新的命名规则更容易理解。

<font size=5>**自动加载-loader模块的拓展名的功能被移除**</font>

当我们引用loaders时我们现在不能再省略```-loader```的拓展名了。

<font size=5>**关联 loaders**</font>

在使用 **webpack 1** 时，我们使用```!```来关联它们，但是在 **webpack 2** 中我们使用```use```来配置一组**loaders**


    const {resolve} = require('path');
    const webpack = require('webpack');
    const ExtractTextPlugin = require('extract-text-webpack-plugin');
    module.exports = {
        context: resolve(__dirname, 'src'),
        entry: [
            './scripts/main.js'
            // app的入口
        ],
        output: {
            filename: 'main.js',
        },
        devtool: 'source-map',
        module: {
            rules: [
                {
                    test: /\.jsx?$/,
                    use: ['babel-loader',],
                    exclude: /node_modules/
                },
                {
                    test: /\.scss$/,
                    use: ['css-hot-loader'].concat(ExtractTextPlugin.extract({
                            use: [
                                {
                                    loader: "css-loader" // 将CSS载入CommonJS
                                },
                                {
                                    loader: "sass-loader" // 将Sass编译成CSS
                                }
                            ],
                            fallback: "style-loader" // 假如CSS没有被提取到时运行
                        }
                    ))
                },
                {
                    test: /\.woff($|\?)|\.woff2($|\?)|\.ttf($|\?)|\.eot($|\?)|\.svg($|\?)/,
                    use: 'url-loader'
                },
            ]
        },
        plugins: [
            new webpack.NamedModulesPlugin(),
            // 当HMR有更新时在浏览器控制台调用更多可读模块名
            // prints more  in the browser console on HMR updates

            new ExtractTextPlugin({filename: 'styles.css', allChunks: true})
        ],
    };


<font size=5>**css-hot-loader**</font>

从css被关联到index文件之后，使用css-hot-loader来重新加载样式的变动。

你可以在github上找到整个搭建完成的[react-webpack-kit](https://github.com/srinisoundar/react-webpack-babel-kit)


如果有什么想法或者观点请反馈给原作者。
