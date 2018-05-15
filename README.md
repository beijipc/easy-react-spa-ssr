# 项目说明
这是一个使用easywebpack-cli 3.11.1创建的spa react ssr项目，用于测试antd的自定义主题less modifyVars

# 修改如下
- 安装了less相关
  ```
  npm install less less-loader --save-dev
  ```
- package.json 增加了theme字段
  ```
  "theme": {
    "primary-color": "#d9534f"
  }
  ```
- webpack.config.js 增加less，使用modifyVars
  ```
  loaders: {
    less: {
      options: {
        modifyVars: theme
      }
    }
  },
  ```
- .babelrc style改成true就会报错
  ```
  ["import", { libraryName: "antd", style: true }]
  ```
- home.js 引入Button
  ```
  import {Button} from 'antd'
  <Button type="primary" onClick={() => add(item)}>Add</Button>
  // line: 81
  ```