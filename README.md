# \<mt-entries-list\>

iron-ajax を使って DataAPI で取得した記事一覧を ul > li で出力するカスタムタグ。

注意: 単なるサンプルなので、実用性はありません。

## 使い方

```html
<mt-entries-list
  base-url="/mt/mt-data-api.cgi"
  version="v3"
  site-id="1"
  params='{"sortOrder":"ascend"}'
></mt-entries-list>
```

上記が下記に展開されます。

```html
<ul>
  <li><a href="[[entry.permalink]]" title="[[entry.excerpt]]">[[entry.title]]</a></li>
  <!-- 取得した記事の数だけ上記をリピート -->
</ul>
```

## スタイリング

下記のカスタム CSS mixin を通して、ul, li, a のそれぞれのスタイルを指定します。

注意: ほとんどの環境では polyfill が必要になります。

```css
<style>
mt-entries-list {
  --mt-entries-list: {
    /* ul のスタイル */
  };
  --mt-entries-list-item: {
    /* li のスタイル */
  };
  --mt-entries-list-item-anchor-link: {
    /* a:link のスタイル */
  };
  --mt-entries-list-item-anchor-visited: {
    /* a:visited のスタイル */
  };
  --mt-entries-list-item-anchor-hover: {
    /* a:hover のスタイル */
  };
  --mt-entries-list-item-anchor-active: {
    /* a:active のスタイル */
  };
}
</style>
```
