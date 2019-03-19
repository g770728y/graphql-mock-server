## 简介

适合: 作为中小型`graphql`应用的 mock server\
不适合正式项目(因为目录结构基本是按 `mock` 数据要求而规划的)

## 为什么不直接使用 apollo server 的 mock ?

生成的数据是随机数, 太过简单\
数据之间缺乏关联, 不仅难以验证逻辑, 而且关联数据的缺失, 还会导致前端报错\
**最好的 mock 数据, 是与后台真实数据结构相同, 并且相互关联的真实数据**

> 其它选择: 如果你不使用 subscription, 并且没有复杂的关联数据, 推荐: `https://github.com/marmelab/json-graphql-server`

## 包含哪些内容

1. `graphql server`, 未整合 express
2. `token`认证(使用 `uuid` 作为 `token`, 可以很容易地抽换为 `jwt` )
3. 合理的目录规划(注意这个目录规划仅适合用于 mock-server, 如果是正式项目, 需要大幅改动)
4. 演示`grapqhql`的用法, 包含 `subscription`

## 快速上手(作为 mock server)

假设你的前端项目名为: front_project, 那么:
第一步: 启动 mock

    cd front_project
    git clone https://github.com/g770728y/graphql-mock-server $your-mock-server-name

    cd $your-mock-server-name
    yarn
    yarn dev

第二步: 连接到 client

    cd front_project
    将 `uri` 改成 http://localhost:3999/graphql

第三步: 参照 `src/desk` 等目录, 编写自己的 `mock` 数据
