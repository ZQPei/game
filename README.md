# 游戏目录

[打开游戏目录](https://zqpei.github.io/game/)

本仓库维护目录页和 GitHub Pages 部署流程。24 层魔塔的源码在 [ZQPei/mota](https://github.com/ZQPei/mota)，发布到 [游戏页面](https://zqpei.github.io/game/mota/)。

[Saltline](https://zqpei.github.io/game/saltline/) 是 Felix Rieseberg 用 Claude Fable 5.2 制作的游戏。发布流程使用 [第三方源码镜像](https://github.com/realcodebear/saltline-fable-5.2) 的固定提交。原作的开源授权尚未确认。 [原作页面](https://claude.ai/artifact/BGY1SztrAYcJQHSsnHHGmp)

更新 24 层魔塔后，在本仓库的 GitHub Actions 中运行 **Deploy game catalog**，工作流会取魔塔仓库的最新 `main` 并重新发布。更新 Saltline 时，在发布工作流中修改镜像的提交哈希。推送本仓库的 `main` 也会触发发布。

新增游戏时，在独立仓库准备带有 `index.html` 的静态文件，在 [发布工作流](.github/workflows/pages.yml) 中将这些文件放到 `public/<游戏名>/`，再给目录页添加指向该目录的相对链接。
