原文: [Creating a Hangeul font](https://glyphsapp.com/learn/creating-a-hangeul-font)
# ハングルフォントの作り方

チュートリアル

[ 言語 ](https://glyphsapp.com/learn?q=languages)

Minjoo Ham & Aaron Bell著

[ en ](https://glyphsapp.com/learn/creating-a-hangeul-font) [ zh ](https://glyphsapp.com/zh/learn/creating-a-hangeul-font)

2022年7月26日 2018年11月19日公開

膨大な文字セットを持つ新しい韓国語フォントの作成は、どこから手をつけていいか分からない、 daunting な作業に思えるかもしれません。このチュートリアルでは、韓国語を始めるためのすべてのツールを提供し、Glyphsで新しい韓国語フォントを作成する基本を説明します。

すでに韓国語に精通している方は、遠慮なく先に進んでください。

## 字母アルファベット

韓国語の文字は*ハングル*（または*Hangul*）と呼ばれ、*字母*と呼ばれる構成要素からなる音節でできています。*字母*には3つのカテゴリーがあります。*初声*（音節の初めの子音）、*中声*（音節の中間の母音）、そして*終声*（音節の最後の子音）です。

現代韓国語で可能なすべての*字母*は以下の通りです。

*   *初声*（初頭）：`ᄀᄁᄂᄃᄄᄅᄆᄇᄈᄉᄊᄋᄌᄍᄎᄏᄐᄑᄒ`
*   *中声*（中間）：`ㅏㅑㅓㅕㅗㅛㅜㅠㅡㅣㅐㅒㅔㅖㅘㅙㅚㅝㅞㅟㅢ`
*   *終声*（末尾）：`ㄱㄲㄳㄴㄵㄶㄷㄹㄺㄻㄼㄽㄾㄿㅀㅁㅂㅄㅅㅆㅇㅈㅊㅋㅌㅍㅎ`

これらの*字母*、その発音、ハングルに関するその他の情報については、[wikipediaの記事](https://en.wikipedia.org/wiki/Hangul#Letters)を参照してください。

## 音節の構成

*ハングル*の音節は、音節内で使われる母音（*中声*）に応じて、6つの方法のいずれかで*字母*から構成されます。

![](images/hangul-generic2.png)

白は初頭の*初声*、黄色は中間の*中声*、濃い灰色は末尾の*終声*です。

これらの*6つ*の異なる音節は、その構造に基づいて名付けられています。

1.  水平の組み合わせ（*初頭子音と縦母音*）。
2.  垂直の組み合わせ（*初頭子音と横母音*）。
3.  混合の組み合わせ（*初頭子音と混合母音*）。
4.  末尾子音付きの水平の組み合わせ。
5.  末尾子音付きの垂直の組み合わせ。
6.  末尾子音付きの混合の組み合わせ。

いくつかの音節の例を見てみましょう。

![](images/hangul-character.png)

### ヒント

ワークフローの早い段階で、これら6つの音節のバリエーションを*少なくとも1つずつ*手作業でデザインすることをお勧めします。そうすることで、ガイド、配置、文字のサイズを素早く決定するのに役立ちます。

*終声*の追加に関わらず、*初声*と*中声*の相対的な位置は同じままであることに注意してください。

さて、韓国語の基本を理解したところで、始めましょう！

## 韓国語とUnicode

Glyphsを使えば、プロジェクトに必要なすべての*ハングル*のUnicode文字を簡単に追加できます。サイドバーの*言語 > 韓国語*セクションには、さまざまなサブカテゴリがあります。

*   **Jamo Compatibility：** これは、独立した形で*字母*を表すために使用されるUnicodeブロックです。
*   **Choseong：** これらは、初頭の位置にある子音の*字母*です。
*   **Jungseong：** これらは、中間の位置にある母音の*字母*です。
*   **Jongseong：** これらは、末尾の位置にある子音の*字母*です。

![](images/sidebar.png)

### プロのヒント

Glyphsの重要な機能の一つは、*ハングル*音節を自動的に生成する技術が含まれていることです。この技術は、*初声 / 中声 / 終声*のUnicodeブロックの使用を必要とします。音節を個別に手作業で作成する予定がある場合は、これらのUnicodeスロットの使用は必要ありません。

*ハングル*の音節は、それぞれ独自のUnicodeスロットで表されます。考慮すべき2つのサブカテゴリがあります。

*   **基本音節：** これらは、KS X 1001標準とAdobe-KR標準に基づいた、核となる2,780の*ハングル*音節です。現代韓国語の組版にはこれで十分であり、おそらくあなたのフォントにもこれらを入れたいと思うでしょう。信じてください。
*   **すべての音節：** これらは、これまでに発生しうるすべての音節（11,172）の完全なセットです。

他に注目すべきサブカテゴリ：

*   **Codepages > Adobe-KR：** これらのエントリは、韓国語フォントを作成するために使用されるさまざまなAdobe-KR標準をカバーしています。多くの主要なタイプファウンドリがこれらのフォントに使用しています。
*   **Codepages > KS X 1001 (Hanja)：** このカテゴリは、韓国語のテキストに使用される漢字をカバーしています。これらの文字は現代韓国語ではあまり使われません。

これらのサブカテゴリをフォントに追加するには、それぞれを右クリックしてすべての欠落しているグリフをリスト表示し、Cmd-Aを押してすべてを選択し、*生成*をクリックします。

![](images/sidebar-addglyphs.png)

## 基本的な音節の作成

さて、描画に取り掛かりましょう！この例では、グリフ밈`mim-ko`、つまり終声を持つ混合組み合わせの音節に焦点を当てます。この音節を作成するには、4つのグリフが必要です—3つの*字母*と完全な音節です。

    mieumCho-ko
    iJung-ko
    mieumJong-ko
    mim-ko

フォントにこれらのグリフがまだない場合は、左サイドバーの*言語 > 韓国語*から追加するか、トップメニューから*グリフ > グリフを追加…*（Cmd-Shift-G）を選択し、上記の名前をボックスに貼り付けます。ダイアログを確定すると、ほら、必要なすべてのグリフがフォントに追加されます。

> **ヒント：** Glyphsでは、すべての韓国語グリフに接尾辞`-ko`が付いています。さらに、音節の初め、中間、終わりにどの*字母*があるかを区別するために、グリフ名に`Cho`（*初声*）、`Jung`（*中声*）、`Jong`（*終声*）の略語が使われます。例えば、母音*yi*を示す`yiJung-ko`や、子音*mieum*の初頭バージョンを示す`mieumCho-ko`などです。

`mieumCho-ko`グリフを開いてください。

![](images/emptymieum.png)

韓国語フォント開発に別のプログラムを使ったことがあるか、Glyphsでラテン文字フォントを作成したことがあるなら、メトリクスボックスが韓国語の文字では異なって見えることに気づくかもしれません。標準のベースライン、xハイト、キャップハイト、アセンダーの値の代わりに、CJKグリフはemスクエアを使って表示され、emスクエアの中間点とフォントのベースラインもマークされています。これにより、不要なメトリクスに気を取られることなく、他のスクリプトとの位置合わせを考慮することができます。

### プロのヒント

Glyphsには、カスタムグリッドを追加できる非常に便利な機能*CJK Grid*が含まれています。*ファイル > フォント情報 > マスター*に行き、*カスタムパラメータ*フィールドでプラスをクリックして*CJK Grid*を追加します。次に、その値を希望する列と行の数に設定します。*ハングル*開発には8を使用することをお勧めします。

`mieumCho-ko`グリフを次のように描いてみましょう。

![](images/miem_2.png)

この例では、*字母*の配置に注意してください。この音節には終声があるので、最初の consonants を高く、左に配置します。これにより、自動配置中に異なる*字母*が互いに重ならないようになります。

次に、`iJung-ko`グリフをダブルクリックし、基本的なㅣの形を描きます。

![](images/ijung_2.png)

再び、この*字母*の配置に注意してください—前のものの右側にあります。

最後に、`mieumJong-ko`グリフをダブルクリックします。これは`mieumCho-ko`と同じ*字母*なので、ここで描いたアウトラインを自由にコピー＆ペーストしてください。次に、それを下方にシフトさせ、描いた`iJung-ko`の*字母*の下の位置に置きます。

![](images/miemjong_2.png)

次に`mim-ko`に行くと、空のグリフが表示されます。

![](images/mim_2.png)

ここで魔法が起こります。Glyphsは`mim-ko`が`mieumCho-ko`、`iJung-ko`、`mieumJong-ko`からできていることを知っているので、自動的に音節を構築できます。*グリフ > コンポジットを作成*（Ctrl-Cmd-C）を選択すると、ドーンと。

![](images/mim_component_2.png)

### プロのヒント

特定の音節にどの*字母*が使われているか疑問に思う場合は、*ウィンドウ > グリフ情報*で構成をプレビューし、[独自のGlyph Data XMLを作成する](roll-your-own-glyph-data.md)ことでデフォルトを独自の構成で上書きできます。

このプロセスを*初声*、*中声*、*終声*リストのすべての*字母*に対して繰り返せば、Glyphsは*すべての音節*セットにある11,000以上の*ハングル*音節をすべて構築することさえできます。わあ！あなたは最初の*ハングル*フォントを作成しました！

このスタイルの*ハングル*フォントは、通常「アウト・オブ・フレーム・スタイル」（別名「デフレーム」または「デ・スクエアード」）と呼ばれ、ディスプレイタイポグラフィで最もよく使用される、かなり現代的な*ハングル*デザインのアプローチです。

## 字母のバリエーション

*基本音節*セクションでは、構造に関わらず、すべての音節で同じ*初声*、*中声*、*終声*の*字母*が使用されます。しかし、デザインが同じ音節内の他の*字母*によって*字母*の形を変える必要がある場合はどうでしょうか？

下の例では、どの末尾の*字母*が使われるかによって、ㅁ（*mieum*、青でマーク）の形が変わります。

![](images/inframe_2.png)

これら2つの音節例を見ると、最初の音節のㄴ（*nieun*）は、2番目の音節のㄹ（*rieul*）よりもㅁ（*mieum*）により多くの垂直スペースを与えていることがわかります。ご想像の通り、すべての音節は異なるため、突然各*字母*のバージョンが5、10、さらには20個も出てくるかもしれません！怖く思えるかもしれませんが、このバリエーションは、テキストタイポグラフィの適切なバランスと比率を達成するために絶対に重要です。

このスタイルの*ハングル*は、通常「インフレーム・スタイル」（または単に「フレーム」または「スクエアード」）と呼ばれ、最も一般的な*ハングル*のスタイルです。

## 高度な音節の作成

*字母*のバリエーションを使ってみましょう。この例では、`man-ko` 만 に焦点を当てます。フォントに次のグリフを追加してください。

    man-ko
    mieumCho-ko
    aJung-ko
    nieunJong-ko

また、2つのバリエーションを作成します。

    mieumCho-ko.man
    aJung-ko.man

今回は、`mieumCho-ko`と`aJung-ko`を描くとき、文字마`ma-ko`をデザインしているかのように、全高で描きます。まず、`mieum-ko`からです。

![](images/mieum_draw.png)

`aJung-ko`でも同じことをします。

![](images/ajung-draw.png)

`nieunJong-ko`については、ボックスの下部にこのように描きます。

![](images/nieun-draw.png)

さて、`man-ko`に行き、*グリフ > コンポジットを作成*（Ctrl-Cmd-C）を押すと、かなり不快な結果が得られます。

![](images/manbefore.png)

なんてことだ！すべてが重なっています！しかし、解決策があります。作成した2つのバリアントグリフを覚えていますか？`mieumCho-ko`から`mieumCho-ko.man`にアウトラインをコピーし（または*グリフ > グリフを複製*でグリフを複製し、新しいグリフを適切にリネームします）、ㄴ（*nieun*）の上部とㅁ（*mieum*）の下部の間にスペースができるように*字母*の下部を上げます。

![](images/shiftedmieum.png)

### プロのヒント

[スマートコンポーネント](learn/smart-components)を使えば、シェイプの再利用と調整がずっと簡単になります。スマートコンポーネントの作成には少し時間がかかりますが、それだけの価値はあります。そうでなければ、あらゆる種類のバリエーションでシェイプを繰り返すのに多くの時間を費やすことになります。

完了したら、`man-ko`に戻り、`mieumCho-ko`コンポーネントを選択し、下の灰色の情報ボックスにある*mieumCho-ko*という名前をクリックします…

![](images/select-mieum2.png)

…そしてコンポーネントを選択するためのウィンドウがポップアップします。`mieumCho-ko.man`を検索して選択します。

![](images/mieumcho.png)

これにより、選択されたコンポーネントが`.man`バリアントに置き換えられます。ジャジャーン！`.man`バリアントで、重なりの問題を解決し、*初声*と*終声*の間のバランスをより良く達成しました！

さて、もう何をすべきかはお分かりでしょう。`aJung-ko`コンポーネントを選択します。

![](images/selecta.png)

`aJung-ko`に対しても同じ手順に従うと、最終的な結果は次のようになります。

![](images/manafter.png)

いいですね。今こそ、自分を褒めてあげましょう。この例では、幸運にも`nieunJong-ko`に何の変更も加える必要はありませんでしたが、他の音節ではこの*字母*の代替バージョンに交換する必要があるでしょう。

### ヒント

コンポーネントの元のグリフを編集するには、単に（灰色の）コンポーネントをダブルクリックするだけで、Glyphsは編集ビューに元のグリフを挿入し、すぐに編集できるようにアクティブ化さえします。この方法で、`.man`グリフを調整し、`man-ko`音節ですぐに組み合わせた結果を見ることができます。

おめでとうございます！あなたは最初の「インフレーム・スタイル」の*ハングル*音節を作成しました！さあ、このプロセスを2,780の基本的な*ハングル*音節すべてに対して繰り返すだけで、完了です。簡単でしょう？

## 近日公開：ハングルの構成

幸いなことに、Glyphsには*ハングル*音節を作成するための高度な機能が含まれています。*ハングル構成*エンジンを使えば、グリフのバリエーションをグループにまとめ、どの*字母*をどこで使うべきかを決定するルールを確立できます。完了すれば、エンジンが音節のデータベース全体を自動的に管理してくれます！しかし、それは次の韓国語チュートリアルでのお話です。

楽しんで、乞うご期待！

ゲストチュートリアル by [Minjoo Ham](http://www.minjooham.com) and [Aaron Bell](http://www.sajatypeworks.com)。
フィードバックをくれたEunyou Noh、Daekwon Kim、Yanghee Rueに感謝します。
サンプルフォント：GEOJANG AND HAHMLET BY MINJOO HAM。

---

更新履歴 2019-02-12: スクリーンショットを修正・復元。

更新履歴 2020-11-13: Glyphs 3ウェブサイトの更新。

更新履歴 2022-16-08: タイトル、関連記事、軽微なフォーマットを更新。

## 関連記事

[すべてのチュートリアルを見る →](https://glyphsapp.com/learn)

*   ### [シェイプの再利用：スマートコンポーネント](smart-components.md)

チュートリアル

[ シェイプの再利用 ](https://glyphsapp.com/learn?q=reusing+shapes)

*   ### [シェイプの再利用：コーナーコンポーネント](reusing-shapes-corner-components.md)

チュートリアル

[ シェイプの再利用 ](https://glyphsapp.com/learn?q=reusing+shapes)