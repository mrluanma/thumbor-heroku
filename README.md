Thumbor on Heroku
=================

[Thumbor](https://github.com/thumbor/thumbor) 是一個動態縮圖服務。

簡單來說, 可以及即時直接讀取原圖然後輸出你要的縮圖, 可以自定大小。

你可能會想說這效能到底行不行阿? 其實你前面擋個 CDN 就好了, 小海嚴選就是這麼做的, 1 Heroku dyno + Cloudflare. Perfect!

OK, 這個 repo 就是為了簡化所有流程而做的, 你只需要遵照以下幾個步驟, 就可以在五分鐘內開始擁有你自己的動態縮圖服務。

安裝流程
--------

[![Heroku Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/mrluanma/thumbor-heroku)

```bash
$ heroku create
$ heroku buildpacks:set heroku/python
$ heroku buildpacks:add heroku-community/nginx
$ git push heroku master
$ heroku open
```

接著然後輸入你要的縮圖圖片網址, 便可以動態產生縮圖, 這裡以寬高 300x300 為例子。

```
http://<your-herokuapp.com>/unsafe/400x400/raw.githubusercontent.com/mrluanma/thumbor-heroku/master/docs/screenshot.png
```

這裡便是我要的 300x300 的縮圖

![](https://raw.githubusercontent.com/mrluanma/thumbor-heroku/master/docs/screenshot.png)

沒錯, 不到五分鐘! 要是超過 5 分鐘, 一定是你網路太慢, 或是 Heroku 太慢, 絕對不是我的問題。

更多詳細功能請見 [Thumbor](https://github.com/thumbor/thumbor)
