# Ruby on Rails環境をDockerで作成


## Nokogiriのインストールで失敗

rubyのDockerImageは初期の状態ではiconvがインストールされていないためか、Nokogiriのインストールで下記のエラーが発生します。

```
invalid gem: package is corrupt, exception while verifying: undefined method `size' for nil:NilClass (NoMethodError) in /usr/local/bundle/cache/nokogiri-1.10.3.gem
```

そのため、事前に下記のライブラリをインストールすることで回避することが出来ます。
```
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
```

参考：[Dockerを使ってRuby on Rails環境の構築をしてみる](https://qiita.com/me-654393/items/d11b871ce8d76e153b21)

## 参考
- [Dockerを使ってRuby on Rails環境の構築をしてみる](https://qiita.com/me-654393/items/d11b871ce8d76e153b21)